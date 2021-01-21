# The IPFS web browsers integration group
*Half of the IPFS Web Browsers & [GUI](https://github.com/ipfs/ipfs-gui) Working Group*

[![Made by icon.](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat)](https://protocol.ai/)
[![Project icon.](https://img.shields.io/badge/project-IPFS-blue.svg?style=flat)](http://ipfs.io/)
[![#ipfs](https://img.shields.io/badge/irc-%23ipfs-brightgreen.svg)](https://webchat.freenode.net/?channels=ipfs) [![#ipfs-in-web-browsers](https://img.shields.io/badge/irc-%23ipfs--in--web--browsers-brightgreen.svg)](https://webchat.freenode.net/?channels=ipfs-in-web-browsers)

Our goal is to **facilitate native support for IPFS and other decentralized protocols in web browsers in order to benefit ...**. 

- **Browser users**: Browser extensions and native-included IPFS alike expose IPFS features in a robust and intuitive way
- **Web developers**: Web developers can enjoy a smooth experience working with IPFS in browser contexts
- **Browser vendors**: Browser developers are empowered to meet the requirements of the distributed web

## Contents

- [Current projects](#current-projects)
   - [IPFS Companion browser extension](#ipfs-companion-browser-extension)
   - [IPFS and the JavaScript ecosystem](#ipfs-and-the-javascript-ecosystem)
   - [Accessing the IPFS HTTP API](#accessing-the-ipfs-http-api)
   - [How to address IPFS on the web](#how-to-address-ipfs-on-the-web)
   - [DNSLink](#dnslink)
   - [Collaborations](#collaborations)
     - [IPFS and Igalia collaborate on dweb in browsers](#ipfs-and-igalia-collaborate-on-dweb-in-browsers)
     - [Brave](#brave)
     - [Opera](#opera)
- [WG status](#wg-status)
- [Get involved!](#get-involved) 
- [Resources](#resources)

## Current projects

### IPFS Companion browser extension

[IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion#ipfs-companion) is a browser extension that simplifies access to IPFS resources and adds browser support for the IPFS protocol. It runs in <img src="https://unpkg.com/@browser-logos/firefox@2.0.0/firefox_16x16.png" width="16" height="16">Firefox (desktop and Android) and Chromium-based browsers including
<img src="https://unpkg.com/@browser-logos/chrome@1.0.4/chrome_16x16.png" width="16" height="16">Chrome or
<img src="https://unpkg.com/@browser-logos/brave@3.0.0/brave_16x16.png" width="16" height="16">Brave. Check out all of [IPFS Companion's features](https://github.com/ipfs-shipyard/ipfs-companion#ipfs-companion-features) and [**install it**](https://github.com/ipfs-shipyard/ipfs-companion#install) today!


| <img src="https://unpkg.com/@browser-logos/firefox@2.0.0/firefox_16x16.png" width="16" height="16"> [Firefox](https://www.mozilla.org/firefox/new/) / [Firefox for Android](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | <img src="https://unpkg.com/@browser-logos/chrome@1.0.4/chrome_16x16.png" width="16" height="16"> [Chrome](https://www.google.com/chrome/) / <img src="https://unpkg.com/@browser-logos/brave@3.0.0/brave_16x16.png" width="16" height="16"> [Brave](https://brave.com/)
|------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [![Install From AMO](https://ipfs.io/ipfs/QmSX44XockQifmxE8Wdevkaa6vaqTXtGdH9t9aHWXZkuJq)](https://addons.mozilla.org/firefox/addon/ipfs-companion/) | [![Install from Chrome Store](https://ipfs.io/ipfs/QmPinSJKFYCMuTDh484dLk5Av4HpZRzBRR1KPv7TM7CBVF)](https://chrome.google.com/webstore/detail/ipfs-companion/nibjojkomfdiaoajekhjakgkdhaomnch) |

#### Past web extension experiments
- Mozilla hosted a community effort called [`libdweb`](https://github.com/mozilla/libdweb/) to implement experimental APIs for Firefox WebExtensions, with a goal of enabling dweb protocols in Firefox through browser add-ons:
  - IPFS [libdweb experiments](https://github.com/ipfs-shipyard/ipfs-companion/blob/libdweb/docs/libdweb.md), including a [native protocol handler](https://github.com/ipfs-shipyard/ipfs-companion/pull/533), [local DNS-SD discovery and TCP transport](https://github.com/ipfs-shipyard/ipfs-companion/pull/553)
  - The long-term goal of this project was to integrate these APIs into the WebExtensions ecosystem, but as of Q3 2020 it is not yet in Firefox Nightly
- Exposing the IPFS API via [`window.ipfs`](https://docs.ipfs.io/how-to/companion-window-ipfs/) (experiment ended in 2020)
- Support for [`chrome.sockets.*` APIs](https://github.com/ipfs-shipyard/ipfs-companion/issues/664) in Chromium browsers (deprioritized due to [EOL 2022](https://9to5google.com/2020/01/15/google-killing-chrome-apps/))

### IPFS and the JavaScript ecosystem
At present, in order to run IPFS in a web browser, you must either bundle [`js-ipfs`](https://github.com/ipfs/js-ipfs/tree/master/packages/ipfs) (a full IPFS node in JavaScript) with your client-side application, or use the [`js-ipfs-http-client`](https://github.com/ipfs/js-ipfs/tree/master/packages/ipfs-http-client) HTTP API client library to connect to an external daemon running on a local or remote machine. 

- To learn more, make sure to check the `browser-*` examples at [`js-ipfs/examples`](https://github.com/ipfs/js-ipfs/tree/master/examples)
  - Highlight: an advanced, end-to-end example of using js-ipfs node in `SharedWorker` from `ServiceWorker` can be found at [`ipfs/js-ipfs/examples/browser-service-worker`](https://github.com/ipfs/js-ipfs/tree/master/examples/browser-service-worker)

### Accessing the IPFS HTTP API

The standalone IPFS daemon (either `go-ipfs` or `js-ipfs` in Node) exposes the API at `/api/v0/`. It is an RPC-style API over HTTP POST.

- [API reference](https://docs.ipfs.io/reference/http/api/)
- [Client libraries in various languages](https://github.com/ipfs/ipfs#http-client-libraries)


### How to address IPFS on the web

- For regular users, see this [guide to how to address IPFS content paths on the web](https://docs.ipfs.io/how-to/address-ipfs-on-web/)
- For browser vendors and user agent developers, see this [memo](ADDRESSING.md) for the current set of URL conventions for the IPFS community; we invite everyone to submit questions and suggestions for improvements via issues/PRs

#### DNSLink

[DNSLink](https://dnslink.io) enables you to map a domain name to an IPFS address by means of a DNS TXT record. 

- Read the [DNSLink guide](https://docs.ipfs.io/concepts/dnslink/) for details, including how to set it up on your own website 
- See details on [DNSLink in IPFS Companion](https://docs.ipfs.io/how-to/dnslink-companion/) to see additional benefits of using IPFS Companion with DNSLink support

### Collaborations

#### IPFS and Igalia collaborate on dweb in browsers

In 2020 IPFS and Igalia started a collaboration that will continue during 2021.  
Read more: https://blog.ipfs.io/2021-01-15-ipfs-and-igalia-collaborate-on-dweb-in-browsers/  

The most notable highlights at the beginning of 2021:

* IPFS and [Igalia](https://www.igalia.com/) started a collaboration that will continue during 2021.
* [Distributed web schemes have been safelisted in Chrome 86](https://www.chromestatus.com/feature/4776602869170176)’s implementation of [custom handlers](https://html.spec.whatwg.org/multipage/system-state.html#custom-handlers) and [registered at IANA](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml).
* Chrome 89 will allow browser extensions to register cross-origin handlers or handlers for schemes with prefix `ext+`. Refinement is pending for the [permission UI](https://bugs.chromium.org/p/chromium/issues/detail?id=1079333).
* Firefox 84 marks `http://*.localhost/` URLs as [secure context](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts), which means websites loaded from local [subdomain gateway](https://docs.ipfs.io/how-to/address-ipfs-on-web/#subdomain-gateway) will have access to the same Web APIs as HTTPS version.
* Firefox 84 has improved support for [loading locally delivered mixed-resources](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content#Loading_locally_delivered_mixed-resources). Patches have also been submitted to WebKit but are pending on reviews and discussions.
* Work is in progress to improve Chromium’s consistency and specification compliance regarding the notion of [secure contexts](https://w3c.github.io/webappsec-secure-contexts/), including removing non-standard [localhost](https://chromestatus.com/feature/5698580851458048) [names](https://chromestatus.com/feature/5668106045227008).
* Miscellaneous other fixes have landed for the Firefox and Chromium’s implementations of custom handlers.

#### Brave

[Brave v1.19 has integrated IPFS into their desktop web browser](https://brave.com/brave-integrates-ipfs/) for Windows, macOS and Linux. When Brave detects an address which is an HTTP gateway URL to IPFS content or a native IPFS address such as `ipfs://` or `ipns://` it will prompt the user to install and enable the native IPFS node, or to use an HTTP gateway. 
Diagnostic UI can be found at `brave://ipfs`, we suggest enabling IPFS Companion for the best experience

TLDR integration status:

- Initial release (v1.19) is focused on daemon orchestration and on URI support (read [blogs and press](https://github.com/ipfs/in-web-browsers/issues/64#issuecomment-763016248))
- Demo: Opening `ipfs://{cid}` will trigger install prompt for go-ipfs managed by Brave itself.
- For the best experience enable IPFS Companion and switch it to IPFS Node Type ["Provided by Brave"](https://docs.ipfs.io/how-to/companion-node-types/#provided-by-brave). 
  When Companion is enabled all IPFS resources will be resolved by the local node.

#### Opera

Opera for Android 57 introduced support for resolving `ipfs://` or `ipns://` via a customizable gateway.  
Read more: https://blog.ipfs.io/2020-03-30-ipfs-in-opera-for-android/

## WG status

### Now half of the Web Browsers & GUI Working Group!

The IPFS core team has re-activated the **Web Browsers & GUI Working Group** as a combined team of this group and the [IPFS GUI group](https://github.com/ipfs/ipfs-gui). This larger working group operates with a focus on furthering browser adoption and integration, as well as improving the functionality and usability of our GUI-based tools as a whole, with a particular focus on benefiting the onboarding of new IPFS developers and users.

## Get involved!

### Join a meeting

We'd love to meet you in person at one of our open Web Browsers & GUI Working Group meetings. They're a great way to get quickly up to speed on our work, including latest developments and awesome demos. 

- Meeting details at https://github.com/ipfs/team-mgmt/issues/790

You can also explore [recordings](https://www.youtube.com/playlist?list=PLuhRWgmPaHtRIXVTy_ngBwvsXvWw10mR8) and [notes](https://github.com/ipfs/team-mgmt/tree/master/meeting-notes) from past meetings any time.

### Contribute to an issue

Contributions to our work are more than welcome! Every IPFS Project repo makes use of the project-wide [global issue labeling scheme](https://github.com/ipfs/community/blob/master/ISSUE_LABELS.md). Good labels to look for are ...
- `help wanted`
- `good first issue`
- and there are even occasional `bounty` labels for issues with rewards as part of the [IPFS Bounty Board](https://github.com/ipfs/devgrants/projects/1)!

If you see an issue that catches your eye, leave a comment so we know you're interested, and we'll go from there!

We're an open project and a friendly group, so please be nice and **read the [contributing guidelines](https://github.com/ipfs/community/blob/master/CONTRIBUTING_JS.md)** when you're ready to jump in.

### Discuss in GitHub or IRC

We do hang out on IRC — see the [#ipfs](https://www.irccloud.com/invite?channel=%23ipfs&amp;hostname=irc.freenode.net&amp;port=6697&amp;ssl=1") and [#ipfs-in-web-browsers](https://www.irccloud.com/invite?channel=%23ipfs-in-web-browsers&amp;hostname=irc.freenode.net&amp;port=6697&amp;ssl=1") channels on irc.freenode.net — but for the sake of async communication, archiving, and searchability, we encourage discussions to happen in the context of GitHub issue comments whenever practical.

## Resources

If you're looking for endeavors related to IPFS browser integration work, these resources may be helpful.

- [IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion): Harness the power of your local or `js-ipfs` node directly inside your favorite Chromium or Firefox browser, enabling support for ipfs:// addresses, automatic IPFS gateway loading of websites and file paths, easy IPFS file import and sharing, and more
- [IPFS Web UI](https://github.com/ipfs-shipyard/ipfs-webui): The IPFS dashboard shipped with the IPFS daemon or IPFS Desktop
- [js-ipfs](https://www.npmjs.com/package/ipfs): IPFS implementation in JavaScript
- [HTTP API documentation](https://docs.ipfs.io/reference/http/api/): Guide to the HTTP API exposed when an IPFS node (`go-ipfs` or `js-ipfs`) is running as a daemon; allows you to control the node and run the same commands you can from the command line
    - [js-ipfs-http-client](https://www.npmjs.com/package/ipfs-http-client): Client library for the IPFS HTTP API implemented in JavaScript
- [IPFS GUI group](https://github.com/ipfs-shipyard/pm-ipfs-gui) - The other half of the IPFS Web Browsers & GUI Working Group, dedicated to creating and implementing standards and patterns for IPFS that are simple, accessible, reusable, and beautiful
