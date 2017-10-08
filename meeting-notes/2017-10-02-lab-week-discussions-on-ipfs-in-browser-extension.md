# Roadblocks for IPFS in Browser Extension

This memo is a summary of various conversations we had during
Lab Week for Q4 2017, starting with unconf session on Monday.

> **TL;DR**
> - Right now, [ipfs-companion](https://github.com/ipfs/ipfs-companion) requires external daemon and _just pretends_ to support `ipfs://`, `dweb:` protocols,
> - we've identified Three Problems that need to be solved to have IPFS running natively in browser extension,
> - creation of [Programmable Protocol Handler API](#new-native-programmable-protocol-handler-api-for-webextensions) would solve all of them.

# Identified Problems

## Problem #1: Inability to Inject HTTP Responses by WebExtension

It is possible to run js-ipfs node in extensions background page, but when it
comes to major players in browser space we are missing WebExtension API that
"enables the extension to satisfy hijacked HTTP request by injecting response read by js-ipfs".

As of now (2017) [`browser.webRequest`][2] API makes it possible to:

- cancel the request in `onBeforeRequest`, `onBeforeSendHeaders` and `onAuthRequired`
- redirect the request in `onBeforeRequest`, `onHeadersReceived`
- modify request headers in `onBeforeSendHeaders`
- modify response headers in `onHeadersReceived`
- supply authentication credentials in `onAuthRequired`

What is missing are means of providing response payload instead of redirection
in `onBeforeRequest` step of request life cycle.


## Problem #2: Inability to Control How Origin Is Calculated

Web security model relies on [Same-origin policy][3].

This introduces two major inconveniences for websites loaded via IPFS2HTTP gateways (serving content from `/ipfs/` and `/ipns/` paths):

- every IPFS gateway has different Origin, making it impossible for a user to persist state while switching gateways
- an Origin of a single gateway is shared by all sites loaded from it, making it impossible to write secure web apps

Some people solve this by creating artificial subdomains that have URL-safe CID
in them (`$cid.ipfs.dweb.link`). A subdomain provides separate Origin and
creates an isolated security context.

Unfortunately, this is not possible for a gateway running on `127.0.0.1`.


## Problem #3: Inability to Control Address in Location Bar

This is a major UX issue.

We should  have:

```
dweb:/ipfs/QmbWqxBEKC3P8tqsKc98xmWNzrzDtRLMiMPL8wBuTGsMnR
```

instead of:

```
http://127.0.0.1:8080/ipfs/QmbWqxBEKC3P8tqsKc98xmWNzrzDtRLMiMPL8wBuTGsMnR
```


# Possible Solutions

## Temporary Hacks and Partial Workarounds

[Problem #1](#problem-1-inability-to-inject-http-responses-by-webextension) might be (partially) solved with:

### Creative Use of Service Worker

We could have js-ipfs running inside of a Service Worker acting as a 'proxy'
for  HTTP requests to the public gateway.

See demo and PoC at [IPFS runs as a Service Worker][6].

  - Good:
    - service worker can inject responses for a host it was installed from
    - if we provide Service Worker for the public gateway, and browser
      extension redirects everything to public gateway, then we are able to handle all IPFS requests
    - transparent for the end user
  - Bad
    - a user needs to visit regular HTTP site to install Service Worker
        - Really bad: [service worker must be refreshed/downloaded every 24h][7]
    - if we want to solve [#2](#problem-2-inability-to-control-how-origin-is-calculated) we need to have separate service worker for every gateway/root CID
    - no connection closing + global Service Worker = memory leaks
    - does not address [#3](#problem-3-inability-to-control-address-in-location-bar)

### Extending `webRequest` API to Support Response Injection

In theory, extending existing `browser.webRequest` APIs to support response
generation (e.g. from within `onBeforeRequest` hook) would enable us to hijack
requests and respond with data read via js-ipfs.

There is a very low probability that such API change will happen, these APIs were designed this way with certain security constraints in mind.

Even if it would happen, it would not address problems [#2](#problem-2-inability-to-control-how-origin-is-calculated) and [#3](#problem-3-inability-to-control-address-in-location-bar).

## New, Native, Programmable Protocol Handler API for WebExtensions

What we really need is a new WebExtension API that lets us define a programmable protocol
handler.

Such API should enable browser extension to do three things:

1. Respond to `dweb:` requests with actual payload (no redirect to HTTP).

   To be more specific, WebExtension should be able to provide function that
   takes a URI and returns `new Response(data, headers)`

2. Control how _Origin_ is calculated.

   In case of `/ipfs/$cid`, every CID would have its own Origin.

3. Display and support use of `dweb:` address in GUI (location bar, bookmarks, etc)

   This would not only improve user experience but also enable us to use `dweb:` links by default.

The good news is that creation of such API was already proposed in [Bug 1271553: Add ability to implement programmable custom protocol handler][4].

The bad news is that it won't happen this year, as most of the engineering efforts at Mozilla are focused on [Firefox Quantum][5] release.

Still, this is the best way to solve our Three Problems.

We should advocate creation of such API, as it would not only enable us to do
great things with IPFS browser extension, but could enable Firefox to become an
application platform.


[1]: https://github.com/ipfs/js-ipfs
[2]: https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/WebRequest
[3]: https://en.wikipedia.org/wiki/Same-origin_policy
[4]: https://bugzilla.mozilla.org/show_bug.cgi?id=1271553
[5]: https://www.mozilla.org/en-US/firefox/quantum/
[6]: https://github.com/ipfs/in-web-browsers/issues/55
[7]: https://github.com/w3c/ServiceWorker/issues/514

