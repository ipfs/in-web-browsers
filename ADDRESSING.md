# IPFS Addressing in Web Browsers



> ### Status of This Memo
>
> This living document specifies current set of conventions for the IPFS community,
> and requests discussion and suggestions for improvements via PR.

## Table of Contents

- [**TL;DR**](#tldr)
- [Addressing with `http://`](#addressing-with-http-url)
- [Addressing with `ipfs://` and `ipns://`](#addressing-with-native-url)
- [References](#references)
- [Appendices](#appendices)
  - On [`http://`](#notes-on-addressing-with-http) 
  - On [`ipfs://`](#notes-on-addressing-with-ipfs) 
  - Future: addressing with shared [`dweb`](#future-addressing-with-shared-dweb-namespace) namespace

## TL;DR

If no native protocol handler is available, redirect to path-based IPFS address at a gateway. The implementation should detect if a local IPFS node is available. In web browser contexts where a local IPFS node is present, use [subdomain gateway](https://docs.ipfs.io/how-to/address-ipfs-on-web/#subdomain-gateway) at `localhost`. If not, use public one such as `dweb.link`. 

In both cases point at IPFS path first, to ensure gateway takes care of CID normalization into a DNS-safe form:

```bash
ipfs://{cid}          → https://dweb.link/ipfs/{cid}        → HTTP301 → https://{dns-safe-cid}.ipfs.dweb.link
ipns://{libp2p-key}   → https://dweb.link/ipns/{libp2p-key} → HTTP301 → https://{dns-safe-cid}.ipns.dweb.link
```

When DNSLink hostname is used, redirect to subdomain only with `localhost`, use original HTTP URL otherwise:

```
ipns://{fqdn}         → https://localhost/ipns/{fqdn}       → HTTP301 → https://{fqdn}.ipns.localhost
                      → https://{fqdn} (if no local node)
```

With native protocol handlers, follow below:

```bash
ipfs://{cidv1base32}
ipfs://{cidv0} → redirect → ipfs://{cidv1base32} # CIDv0 is case-sensitive Base58, does not work as Origin authority

ipns://{libp2p-key-in-cidv1base32}
ipns://{libp2p-key-in-base58} → redirect → ipns://{libp2p-key-in-cidv1}  # Base58, does not work as Origin authority

ipns://{fqdn-with-dnslink}
ipfs://{fqdn-with-dnslink} → redirect → ipns://{fqdn-with-dnslink} # just to improve UX :-)
```

## Addressing with HTTP URL

### Subdomains

When [origin-based security](https://en.wikipedia.org/wiki/Same-origin_policy) perimeter is needed, [CIDv1](https://github.com/ipld/cid#cidv1) in Base32 ([RFC4648](https://tools.ietf.org/html/rfc4648#section-6), no padding) should be used in subdomain:

    https://<cid>.ipfs.<gateway-host>.tld/path/to/resource
    https://<libp2p-key-cid>.ipns.<gateway-host>.tld/path/to/resource

Example:

    https://bafybeiemxf5abjwjbikoz4mc3a3dla6ual3jsgpdr4cjr3oz3evfyavhwq.ipfs.dweb.link/wiki/

Subdomain gateway feature in go-ipfs takes care of necessary CID conversion when IPFS path is requested:

```
https://dweb.link/ipfs/QmT5NvUtoM5nWFfrQdVrFtvGfKFmG7AHE8P34isapyhCxX/wiki/Mars.html → HTTP 301 
  → https://bafybeicgmdpvw4duutrmdxl4a7gc52sxyuk7nz5gby77afwdteh3jc5bqa.ipfs.dweb.link/wiki/Mars.html
```

Read more: [notes on addressing with HTTP](#notes-on-addressing-with-http).

### Paths

When site isolation does not matter gateway can expose IPFS namespaces as regular URL paths:

    https://<gateway-host>.tld/ipfs/<cid>/path/to/resource
    https://<gateway-host>.tld/ipns/<keyid_or_fqdn>/path/to/resource

Examples:

    https://gateway.ipfs.io/ipfs/bafybeiemxf5abjwjbikoz4mc3a3dla6ual3jsgpdr4cjr3oz3evfyavhwq/wiki/Vincent_van_Gogh.html
    https://gateway.ipfs.io/ipfs/QmT5NvUtoM5nWFfrQdVrFtvGfKFmG7AHE8P34isapyhCxX/wiki/Mars.html
    https://gateway.ipfs.io/ipns/tr.wikipedia-on-ipfs.org/wiki/Anasayfa.html

## Addressing with Native URL

Where possible, subdomain convention should be replaced with native handler that provides the same origin-based guarantees:

    ipfs://{cidv1b32}/path/to/resource

Example:

    ipfs://bafybeiemxf5abjwjbikoz4mc3a3dla6ual3jsgpdr4cjr3oz3evfyavhwq/wiki/Vincent_van_Gogh.html

Read more: [notes on addressing with ipfs://](#notes-on-addressing-with-ipfs).

## References
- [The four stages of the upgrade path for path addressing](https://github.com/ipfs/specs/pull/152#issuecomment-284628862)
- [CID as a Subdomain](https://github.com/ipfs/in-web-browsers/issues/89)
- [IPFS: Migration to CIDv1 (default base32)](https://github.com/ipfs/ipfs/issues/337)
- [Support Custom Protocols in WebExtension](https://github.com/lidel/ipfs-firefox-addon/issues/164)
- [mozilla/libdweb experiment: ipfs:// protocol handler](https://github.com/ipfs-shipyard/ipfs-companion/pull/533)

## Appendices

### Notes on addressing with `http://`

The first stage on the upgrade path are HTTP gateways.

Gateways are provided strictly for convenience to help tools that speak HTTP
but do not speak distributed protocols such as IPFS.  This approach has been
working well since 2015 but comes with a significant set of limitations related
to the centralized nature of HTTP and some of its semantics.  Location-based
addressing of a gateway depends on both DNS and HTTPS/TLS, which relies on the trust in
Certificate Authorities and PKI.  In the long term these issues SHOULD be
mitigated by use of opportunistic protocol upgrade schemes.

#### Opportunistic Protocol Upgrade

Tools and [browser extensions](https://github.com/ipfs-shipyard/ipfs-companion) SHOULD detect valid IPFS paths and resolve them
directly over IPFS protocol and use HTTP gateway ONLY as a fallback when no
native implementation is available to ensure a smooth, backward-compatible
transition.


#### Gateway Semantics


In the most basic scheme an URL path used for content addressing is effectively a
resource name without a canonical location.  HTTP Gateway provides the location
part, which makes it possible for browsers to interpret content path as
relative to the current server and just work without a need for any conversion.

HTTP gateway SHOULD:
- Take advantage of existing caching primitives, namely:
    - Set `Etag` HTTP header to the canonical CID of returned payload
    - Set `Cache-Control: public,max-age=29030400,immutable` if resource
      belongs to immutable namespace (eg. `/ipfs/*`)
- set `Suborigin` header based on the hash of the root of current content tree
- provide a meaningful directory index for root resources representing file
  system trees

HTTP gateway MAY:
- Customize style of directory index.
- Return a custom payload along with error responses (HTTP 400 etc).
- Provide a writable (`POST`, `PUT`) access to exposed namespaces.   


##### Origin Workaround #1: Subdomains

Gateway operator MAY work around single Origin limitation by creating artificial
subdomains based on URL-safe version of root content identifier (eg.
`<cidv1b32>.ipfs.foo.tld`).  Each subdomain provides separate Origin and creates an
isolated security context at a cost of obfuscating path-based addressing.

Benefits of this approach:

- The ability to do proper security origins without introducing any changes to
  preeexisting HTTP stack.
- Root path of content-addressed namespace becomes the root of URL path, which
  makes asset adressing compatible with existing web browsers: `<img
  src="/rootimg.jpg">`
- Opens up the ability for [HTTP Host
  header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host) and
  [TLS SNI](https://en.wikipedia.org/wiki/Server_Name_Indication) parsing,
  which is a prerequisite for fully automated deployment of TLS via Let's Encrypt.

According to [RFC 1035](http://tools.ietf.org/html/rfc1035) subdomains (aka
"labels", hostnames) are case-insensitive, which severly constraints the number
of content addressing identifier types that can be used without need for an
additional conversion step.

Due to this IPFS community [decided](https://github.com/ipfs/ipfs/issues/337) to use lowercased base32
([RFC4648](https://tools.ietf.org/html/rfc4648#section-6) - no padding - highest letter)
as the default base encoding of [CIDv1](https://github.com/ipld/cid#cidv1) (our binary identifiers).


##### Origin Workaround #2: Suborigin

Suborigins are a
[work-in-progress](https://w3c.github.io/webappsec-suborigins/) standard to
provide a new mechanism for allowing sites to separate their content by
creating synthetic origins while serving content from a single physical origin.

A [`suborigin` header](https://w3c.github.io/webappsec-suborigins/#the-suborigin-header)
SHOULD be returned by HTTP gateway and contain a value
unique to the current content addressing root.

Unfortunately due to limited adoption suborigin have no practical use.


### Notes on addressing with `ipfs://`

The `ipfs://` protocol scheme follows the same requirement of CIDv1 in Base32 as [subdomains](#origin-workaround-1-subdomains).
It does not retain original path, but instead requires a conversion step to/from URI:
> `ipfs://{immutable-root}/path/to/resourceA` → `/ipfs/{immutable-root}/path/to/resourceA`  
> `ipns://{mutable-root}/path/to/resourceB` → `/ipns/{mutable-root}/path/to/resourceB`  

The first element after double slash is an opaque identifier representing
the content root.  It is interpreted as an authority component used for Origin
calculation, which provides necessary isolation between security contexts of diferent content trees.

### Future: addressing with shared `dweb` namespace

We are exploring the idea of a shared `dweb` namespace to remove the complexity of adressing IPFS and other content-addressed protocols. More details can be found at:
- (A) the `dweb://` protocol handler ([arewedistributedyet/issues/28](https://github.com/arewedistributedyet/arewedistributedyet/issues/28))
- (B) the `.dweb` special-use top-level domain name ([arewedistributedyet/issues/34](https://github.com/arewedistributedyet/arewedistributedyet/issues/34))
