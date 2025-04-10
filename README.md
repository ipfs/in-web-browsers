# The IPFS web browsers integration group
*Informal group working on improving IPFS presence in web browsers*

[![Made by icon.](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat)](https://protocol.ai/)
[![Project icon.](https://img.shields.io/badge/project-IPFS-blue.svg?style=flat)](https://ipfs.tech/)
[![](https://img.shields.io/badge/matrix%20chat-%23lobby:ipfs.io-blue.svg?style=flat-square)](https://matrix.to/#/#lobby:ipfs.io)
[![](https://img.shields.io/badge/forums-discuss.ipfs.io-blue.svg?style=flat-square)](https://discuss.ipfs.tech)

Our goal is to **facilitate native support for IPFS and other decentralized protocols in web browsers in order to benefit ...**. 

- **Browser users**: Browser extensions and native-included IPFS alike expose IPFS features in a robust and intuitive way
- **Web developers**: Web developers can enjoy a smooth experience working with IPFS in browser contexts
- **Browser vendors**: Browser developers are empowered to meet the requirements of the distributed web

## Contents

- [Current projects](#current-projects)
   - [IPFS Companion browser extension](#ipfs-companion-browser-extension)
   - [IPFS and the JavaScript ecosystem](#ipfs-and-the-javascript-ecosystem)
      - [Helia](#helia)
   - [How to address IPFS on the web](#how-to-address-ipfs-on-the-web)
   - [How to run own HTTP Gateway](#how-to-run-own-http-gateway)
   - [How to implement HTTP Gateway](#how-to-implement-http-gateway)
   - [DNSLink](#dnslink)
   - [Collaborations](#collaborations)
     - [W3C](#w3c)
     - [IPFS and Igalia collaborate on dweb in browsers](#ipfs-and-igalia-collaborate-on-dweb-in-browsers)
     - [Brave](#brave)
     - [IPFS in Chromium](#ipfs-chromium)
     - [Opera](#opera)
- [Get involved!](#get-involved) 
- [Resources](#resources)

## Current projects

### IPFS Companion browser extension

[IPFS Companion](https://github.com/ipfs/ipfs-companion#ipfs-companion) is a browser extension that simplifies access to IPFS resources and adds browser support for the IPFS protocol. It runs in <img src="https://unpkg.com/@browser-logos/firefox@2.0.0/firefox_16x16.png" width="16" height="16">Firefox (desktop and Android) and Chromium-based browsers including
<img src="https://unpkg.com/@browser-logos/chrome@1.0.4/chrome_16x16.png" width="16" height="16">Chrome or
<img src="https://unpkg.com/@browser-logos/brave@3.0.0/brave_16x16.png" width="16" height="16">Brave. Check out all of [IPFS Companion's features](https://github.com/ipfs/ipfs-companion#ipfs-companion-features) and [**install it**](https://github.com/ipfs/ipfs-companion#install) today!




| <img src="https://unpkg.com/@browser-logos/firefox/firefox_16x16.png" width="16" height="16"> [Firefox](https://www.mozilla.org/firefox/new/) \| [Firefox for Android](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | <img src="https://unpkg.com/@browser-logos/chrome/chrome_16x16.png" width="16" height="16"> [Chrome](https://www.google.com/chrome/) \| <img src="https://unpkg.com/@browser-logos/brave/brave_16x16.png" width="16" height="16"> [Brave](https://brave.com/) \| <img src="https://unpkg.com/@browser-logos/opera/opera_16x16.png" width="16" height="16"> [Opera](https://www.opera.com/)  \| <img src="https://unpkg.com/@browser-logos/edge/edge_16x16.png" width="16" height="16"> [Edge](https://www.microsoftedgeinsider.com/)
|------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [![Install From AMO](https://ipfs.io/ipfs/QmWNa64XjA78QvK3zG2593bSMizkDXXcubDHjnRDYUivqt)<br>![](https://img.shields.io/amo/users/ipfs-companion?label=AMO%20users&style=social)](https://addons.mozilla.org/firefox/addon/ipfs-companion/) | [![Install from Chrome Store](https://ipfs.io/ipfs/QmU4Qm5YEKy5yHmdAgU2fD7PjZLgrYTUUbxTydqG2QK3TT)<br>![](https://img.shields.io/chrome-web-store/users/nibjojkomfdiaoajekhjakgkdhaomnch?label=Chrome%20Web%20Store%20users&style=social)](https://chrome.google.com/webstore/detail/ipfs-companion/nibjojkomfdiaoajekhjakgkdhaomnch) |

#### Notable past web extension experiments
- Mozilla hosted a community effort called [`libdweb`](https://github.com/mozilla/libdweb/) to implement experimental APIs for Firefox WebExtensions, with a goal of enabling dweb protocols in Firefox through browser add-ons:
  - IPFS [libdweb experiments](https://github.com/ipfs-shipyard/ipfs-companion/blob/libdweb/docs/libdweb.md), including a [native protocol handler](https://github.com/ipfs-shipyard/ipfs-companion/pull/533), [local DNS-SD discovery and TCP transport](https://github.com/ipfs-shipyard/ipfs-companion/pull/553)
  - The long-term goal of this project was to integrate these APIs into the WebExtensions ecosystem, but as of Q3 2020 it is not yet in Firefox Nightly
- Exposing the IPFS API via [`window.ipfs`](https://docs.ipfs.io/how-to/companion-window-ipfs/) (experiment ended in 2020)
- Support for [`chrome.sockets.*` APIs](https://github.com/ipfs-shipyard/ipfs-companion/issues/664) in Chromium browsers (ended due to [EOL 2022](https://9to5google.com/2020/01/15/google-killing-chrome-apps/))

### IPFS and the JavaScript ecosystem

#### Helia 

[Helia](https://github.com/ipfs/helia) is a lean, modular, and modern TypeScript implementation of IPFS for the prolific JS and browser environments.

See the [Manifesto](https://github.com/ipfs/helia/wiki/Manifesto), the [FAQ](https://github.com/ipfs/helia/wiki/FAQ), and the [State of IPFS in JS blog post from October 2022](https://blog.ipfs.tech/state-of-ipfs-in-js/) for more info.

Usage examples:
- [examples at `ipfs/helia`](https://github.com/ipfs/helia?tab=readme-ov-file#-usage)
- an advanced, end-to-end example of using [`@helia/verified-fetch`](https://www.npmjs.com/package/@helia/verified-fetch) node in `ServiceWorker` can be found at <https://inbrowser.link> ([sources](https://github.com/ipfs/service-worker-gateway/))

#### Legacy JS-IPFS

The `js-ipfs` / `ipfs-core` is is no longer maintained.
See [State of IPFS in JS blog post from October 2022](https://blog.ipfs.tech/state-of-ipfs-in-js/) for rationale.

### How to address IPFS on the web

- For regular users, see
  - this [guide to how to address IPFS content paths on the web](https://docs.ipfs.io/how-to/address-ipfs-on-web/)
  - this [reference about HTTP Gateway API](https://docs.ipfs.tech/reference/http/gateway/)
- For browser vendors and user agent developers, see this [memo](ADDRESSING.md) for the current set of URL conventions for the IPFS community; we invite everyone to submit questions and suggestions for improvements via issues/PRs

### How to run own HTTP Gateway

- If you are a desktop user, try [IPFS Desktop](https://docs.ipfs.tech/install/ipfs-desktop/)
- If you only want to run a Gateway as a public HTTP server, and the data is provided by separate IPFS nodes, use the latest [Rainbow](https://github.com/ipfs/rainbow/), which is a specialized gateway daemon.
- If you want to host your own data and prefer to work with command-line, use the latest [Kubo daemon](https://github.com/ipfs/kubo) and follow [gateway recipes](https://github.com/ipfs/kubo/blob/master/docs/config.md#gateway-recipes).
- If you have a lot of data, consider running Kubo with [IPFS Cluster](https://ipfscluster.io/).

### How to implement HTTP Gateway

See specification and implementer notes at <https://specs.ipfs.tech/http-gateways/>.

#### DNSLink

[DNSLink](https://dnslink.dev) enables you to map a domain name to an IPFS address (CID or IPNS libp2p-key) by means of a DNS TXT record. 

- Read the [DNSLink guide](https://docs.ipfs.tech/concepts/dnslink/) for details, including how to set it up on your own website 
- See details on [DNSLink in IPFS Companion](https://docs.ipfs.tech/how-to/dnslink-companion/) to see additional benefits of using IPFS Companion with DNSLink support

### Collaborations

#### W3C

Protocol Labs is a [W3C Member](https://www.w3.org/Consortium/Member/List). 
Current focus is to watch, learn, and participate in [WebExtensions Community Group](https://www.w3.org/community/webextensions/).

- 2023-Q3: [ServiceWorker-like protocol handlers for WebExtensions](https://github.com/ipfs/in-web-browsers/issues/212) mentioned during [WECG TPAC 2023 (notes)](https://github.com/w3c/webextensions/blob/main/_minutes/2023-09-11-wecg-tpac.md)

#### IPFS and Igalia collaborate on dweb in browsers

In 2020 IPFS and Igalia started a collaboration that continues to this day. 
Read more: https://blog.ipfs.tech/2021-01-15-ipfs-and-igalia-collaborate-on-dweb-in-browsers/  

The most notable highlights (chronological order):

* IPFS and [Igalia](https://www.igalia.com/) started a collaboration that will continue beyond 2021+
* [Distributed web schemes have been safelisted in Chrome 86](https://www.chromestatus.com/feature/4776602869170176)’s implementation of [custom handlers](https://html.spec.whatwg.org/multipage/system-state.html#custom-handlers) and [registered at IANA](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml).
* Chrome 89 will allow browser extensions to register cross-origin handlers or handlers for schemes with prefix `ext+`. Refinement is pending for the [permission UI](https://bugs.chromium.org/p/chromium/issues/detail?id=1079333).
* Firefox 84 marks `http://*.localhost/` URLs as [secure context](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts), which means websites loaded from local [subdomain gateway](https://docs.ipfs.tech/how-to/address-ipfs-on-web/#subdomain-gateway) will have access to the same Web APIs as HTTPS version.
* Firefox 84 has improved support for [loading locally delivered mixed-resources](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content#Loading_locally_delivered_mixed-resources). Patches have also been submitted to WebKit but are pending on reviews and discussions.
* Work is in progress to improve Chromium’s consistency and specification compliance regarding the notion of [secure contexts](https://w3c.github.io/webappsec-secure-contexts/), including removing non-standard [localhost](https://chromestatus.com/feature/5698580851458048) [names](https://chromestatus.com/feature/5668106045227008).
* Miscellaneous other fixes have landed for the Firefox and Chromium’s implementations of custom handlers.
* WIP refactor to make it easier to register custom protocol handlers ([example](https://chromium-review.googlesource.com/c/chromium/src/+/2992306), related talk: [Integrating New Protocol Handlers into Chrome [BlinkOn 15]](https://www.youtube.com/watch?v=kHIN6FkLAS8))
* 2022-05-10: HTML spec PR: [add IPFS and IPNS as safelisted schemes for `registerProtocolHandler()`](https://github.com/whatwg/html/pull/7911)
* 2022-05-18: Chromium status update: [New Custom Handlers Component (BlinkOn 16)](https://youtu.be/o1pJJuQiCmQ?t=2771)
* 2022-06-28: [Explainer: Predefined Custom Handlers](https://github.com/Igalia/explainers/tree/main/custom-protocol-handlers/PredefinedHandlers) + [Chromium discussion thread](https://groups.google.com/a/chromium.org/g/content-owners/c/KIFf1EdM-4c/m/7tGJmPiaAAAJ)
* 2022-07-20: Chromium SchemeRegistry patch MERGED: [New list in SchemeRegistry to manage schemes with predefined handlers](https://chromium-review.googlesource.com/c/chromium/src/+/3652049/) 
* 2022-08-03: After refactors, adding predefined, redirect-based handlers is 2 LOC – demo [Implement Predefined Handlers for IPFS schemes using the SchemeRegistry](https://chromium-review.googlesource.com/c/chromium/src/+/3650554)
* 2022-08-01: Blogpost: [New Custom Handlers component for Chrome](https://blogs.igalia.com/jfernandez/2022/08/10/new-custom-handlers-component-for-chrome/)
* 2022-09-28: [Intent to Prototype: Curve25519 in Web Cryptography](https://groups.google.com/a/chromium.org/g/blink-dev/c/n0uKIqfypW0/m/xu5UBbaBAwAJ)
* 2023-Q3: Kick-off work with Igalia on prototyping [ServiceWorker-like protocol handlers for WebExtensions](https://github.com/ipfs/in-web-browsers/issues/212)
* 2024-Q3: Curve25519 in Web APIs is implemented in Chromium and WebKit behind a runtime flag [#](https://github.com/ipfs/in-web-browsers/issues/204#issuecomment-1735833247), remaining work is around WPT and specification details.
* 2025-Q1: Prototyping [New WebExtension API to register `protocol_handlers` in Chromium](https://chromium-review.googlesource.com/c/chromium/src/+/5518971)
* 2025-Q1: [blogpost: Can I use Secure Curves in the Web Platform?](https://blogs.igalia.com/jfernandez/2025/02/28/can-i-use-secure-curves-in-the-web-platform/), [chromium: Ship the Ed25519 WebCrypto agorithm](https://chromium-review.googlesource.com/c/chromium/src/+/6440173)

#### Brave

- 2021: [Brave v1.19 has integrated IPFS into their desktop web browser](https://brave.com/brave-integrates-ipfs/) for Windows, macOS and Linux. 
  - When Brave detected an address which is an HTTP gateway URL to IPFS content or a native IPFS address such as `ipfs://` or `ipns://` it prompted the user to install and enable the native IPFS node (Kubo), or to use an HTTP gateway.  
  - Initial release (v1.19) was focused on daemon orchestration and on URI support (read [blogs and press](https://github.com/ipfs/in-web-browsers/issues/64#issuecomment-763016248))
- 2024: After over three years, the Brave team decided to remove support for running IPFS node as we could not find a mutually agreeable set of terms to make this integration sustainable.
  - Users can retain their PeerID and onboarded data by switching to IPFS Desktop + Companion extension. More details at [Migrating from Brave to IPFS Desktop](https://blog.ipfs.tech/2024-brave-migration-guide/).

#### ipfs-chromium

* 2023-Q3: Project introduction blogpost at [IPFS Multi-Gateway Experiment in Chromium](https://blog.ipfs.tech/2023-05-multigateway-chromium-client/)
* 2023-Q3: [ipfs-chromium](https://github.com/little-bear-labs/ipfs-chromium) project ships first builds
* 2023-08-30: [Intent to Experiment: Verifying IPFS client via HTTP APIs](https://chromestatus.com/feature/5105580464668672)

#### Opera

Opera for Android 57 introduced support for resolving `ipfs://` or `ipns://` via a customizable gateway.  
Read more: https://blog.ipfs.tech/2020-03-30-ipfs-in-opera-for-android/

## Get involved!

<!-- TODO: well, maybe we can bring this back one day...

### Join a meeting

We'd love to meet you in person at one of our open Web Browsers & GUI Working Group meetings. They're a great way to get quickly up to speed on our work, including latest developments and awesome demos. 

- Meeting details at https://github.com/ipfs/team-mgmt/issues/790

You can also explore [recordings](https://www.youtube.com/playlist?list=PLuhRWgmPaHtRIXVTy_ngBwvsXvWw10mR8) and [notes](https://github.com/ipfs/team-mgmt/tree/master/meeting-notes) from past meetings any time.

-->

### Contribute to an issue

Contributions to our work are more than welcome! Every IPFS Project repo makes use of the project-wide [global issue labeling scheme](https://github.com/ipfs/community/blob/master/ISSUE_LABELS.md). Good labels to look for are ...
- `help wanted`
- `good first issue`
- and there are even occasional `bounty` labels for issues with rewards as part of the [IPFS Bounty Board](https://github.com/ipfs/devgrants/projects/1)!

If you see an issue that catches your eye, leave a comment so we know you're interested, and we'll go from there!

We're an open project and a friendly group, so please be nice and **read the [contributing guidelines](https://github.com/ipfs/community/blob/master/CONTRIBUTING_JS.md)** when you're ready to jump in.

### Discuss

For the sake of async communication, archiving, and searchability, we encourage browser-related technical discussions to happen in the context of GitHub issue comments whenever practical.

If you want to ask support question, or just chat informally to learn and brainstorm, feel free to join [chat community](https://docs.ipfs.tech/community/#chat) or discussion forum at https://discuss.ipfs.tech 


### Improve docs

https://docs.ipfs.tech is backed by the repo at https://github.com/ipfs/ipfs-docs – any help in improving docs related to browsers (or not) is appreciated!


### Improve specs

Proof-read [ipfs/specs](https://github.com/ipfs/specs/)  and fill an issue for: (1) outdated specs (2) missing specs (3) bits that are confusing and need to be clarified.

## Resources

If you're looking for endeavors related to IPFS browser integration work, these resources may be helpful.

- [IPFS in Brave Browser](https://brave.com/ipfs-support/): TLDR explanation how Brave supports IPFS out of the box (either as local node, or by delegating to a public gateway of user's choice)
- [IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion): Harness the power of your local IPFS daemon directly inside your favorite Chromium or Firefox browser, enabling support for ipfs:// addresses, automatic IPFS gateway loading of websites and file paths, easy IPFS file import and sharing, and more
- [IPFS Web UI](https://github.com/ipfs-shipyard/ipfs-webui): The IPFS dashboard shipped with the IPFS daemon or IPFS Desktop
- [js-ipfs-core](https://www.npmjs.com/package/ipfs-core): Core IPFS implementation in JavaScript for use in browser (without Nodejs daemon parts)
- [HTTP Gateway API docs](https://docs.ipfs.tech/reference/http/gateway/) - implementation-agnostic interface for trusted and trustless data retrieval
- [HTTP RPC API docs](https://docs.ipfs.tech/reference/kubo/rpc/): Guide to the RPC over HTTP API exposed when a Kubo IPFS node (go-ipfs) is running as a daemon; allows you to control the node and run the same commands you can from the command line
  - For up-to-date info about which JS client to use, see https://github.com/ipfs/kubo/issues/9125
- [IPFS GUI group](https://github.com/ipfs-shipyard/pm-ipfs-gui) - The other half of the IPFS Web Browsers & GUI Working Group, dedicated to creating and implementing standards and patterns for IPFS that are simple, accessible, reusable, and beautiful
