# Implementation Notes for Browsers and URI parsers

Below is the suggested heuristic for detecting content-addressed resources
on the web, and presenting additional user interface for interacting with them.

TBD if this document  will live in this repo, https://docs.ipfs.tech or become part of https://github.com/ipfs/specs/

## Detecting IPFS Resources and Hints

```mermaid
graph TD
    Start[Top-level navigation event]
    IsGateway{Is it a Gateway URL?<br/>foo.tld/ip?s/id/..<br/>id.ns.foo.com/..}

    Start -->|new URL in address bar| IsGateway
    IsGateway ==>|YES| IsPathOrSubdomain
    IsPathOrSubdomain -->|Path Gateway| ExtractFromPath
    IsPathOrSubdomain -->|Subdomain Gateway| ExtractFromSubdomain

    subgraph GwURLToPath [Convert Gateway URL to a Content Path]
        IsPathOrSubdomain{Is the Gateway URL 'path' <br/> or 'subdomain' based?}
        ExtractFromPath[Extract URL.pathname]
        ExtractFromSubdomain[Read namespace and identifier from <br/> URL.hostname and  prepend to URL.pathname. <br/> E.g., turn id.ns.foo.com/pathname <br/> into /ns/id/pathname]
    end

    PotentialContentPath[Found a Potential Content Path]

    ExtractFromPath --> PotentialContentPath
    ExtractFromSubdomain --> PotentialContentPath
    PotentialContentPath -->|/ipxs/id/sub/path..| IsIpfsOrIpns

    subgraph PathValidation [Is the Content Path valid?]
        IsIpfsOrIpns{Is it /ipfs/ or /ipns/?}
        ValidateRootCID{Is 'id' is a valid CID?}
        ValidateIPNSKey{Is 'id' is a valid CID <br/> with libp2p-key codec?}
        ValidateDNSLink{Is 'id' a DNSLink name <br/>  with TXT record? <br/> dnslink=/ipfs/<br/>  or =/ipns/}

        IsIpfsOrIpns --->|/ipfs/id/..| ValidateRootCID
        IsIpfsOrIpns -->|/ipns/id/..| ValidateIPNSKey
        ValidateIPNSKey -->|NO| ValidateDNSLink
    end

    subgraph FoundValidIPFSContent [Confirmed we've found a Valid IPFS Resource]
        ValidIPFSCID[Valid /ipfs/cid/.. Content Path]
        ValidIPNSKey[Valid /ipns/key/.. Content Path]
        ValidDNSLink[Valid /ipns/dnslink/.. Content Path]

        ValidateRootCID ===>|YES, /ipfs/cid/..| ValidIPFSCID
        ValidateIPNSKey ===>|YES, /ipns/key/..| ValidIPNSKey
        ValidateDNSLink ===>|YES, /ipfs/dnslink/..| ValidDNSLink
    end

    subgraph NonGwURLToPath [See if non-Gateway URL has a Content Path]
        IsCachedDNSLink{Does URL.hostname <br/> match a cached <br/> DNSLink domain?}
        IsHeaderPresent{Is X-Ipfs-Path <br/> header present?}
        IsError{Did request fail? <br/> HTTP error>500 <br/> or network error}
        IsDNSLinkAtHostname{Does DNSLink exists <br/> at URL.hostname?<br/>/ipns/example.com}
        PathFromHeader[Read value from X-Ipfs-Path]
    end

    IsGateway -->|NO| IsCachedDNSLink
    IsCachedDNSLink ==>|YES| ValidDNSLink
    IsCachedDNSLink -->|NO| IsHeaderPresent
    IsHeaderPresent ==>|YES| IsDNSLinkAtHostname
    IsHeaderPresent -->|NO| IsError
    IsError ==>|YES| IsDNSLinkAtHostname
    IsDNSLinkAtHostname ==>|YES| ValidDNSLink
    IsDNSLinkAtHostname -->|NO| PathFromHeader
    PathFromHeader --> PotentialContentPath
```

## What to do with detected Content Paths?

### Immutable `/ipfs/cid/..`

- Display "Open via IPFS" button in UI
  - Clicking it should open `ipfs://cid/path?query#hash` (preserving any `?query` or `#hash` from the original HTTP URL)
- If IPFS Gateway Redirect is enabled, and the HTTP URL was a gateway one, redirect automatically to `ipns://dnslink/path?query#hash`

### Mutable `/ipns/key/..`
- Display "Open via IPFS" button in UI
  - Clicking it should open `ipns://key/path?query#hash` (preserving any `?query` or `#hash` from the original HTTP URL)
- If IPFS Gateway Redirect is enabled, and the original HTTP URL was a gateway one, redirect automatically to `ipns://dnslink/path?query#hash`

### Mutable `/ipns/dnslink/..`

- Display "Open via IPFS" button in UI
  - Clicking it should open `ipns://dnslink/path?query#hash` (preserving `?query` or `#hash` from the original HTTP URL)
- If DNSLink Website redirect is enabled, redirect automatically to `ipns://dnslink/path?query#hash`
- It is a good practice to internally cache the fact that domain has a valid DNSLink.
  - TTL from TXT record can be used as a hint when to expire cache entry.
  - Performance can be improved further by using cached flag and revalidating it asynchronously, without blocking browser navigation.
