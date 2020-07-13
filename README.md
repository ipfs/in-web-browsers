# The IPFS web browsers integration group
*Half of the IPFS Web Browsers & [GUI](https://github.com/ipfs/ipfs-gui) Working Group*

[![Made by icon.](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat)](https://protocol.ai/)
[![Project icon.](https://img.shields.io/badge/project-IPFS-blue.svg?style=flat)](http://ipfs.io/)
[![#ipfs](https://img.shields.io/badge/irc-%23ipfs-brightgreen.svg)](https://webchat.freenode.net/?channels=ipfs) [![#ipfs-in-web-browsers](https://img.shields.io/badge/irc-%23ipfs--in--web--browsers-brightgreen.svg)](https://webchat.freenode.net/?channels=ipfs-in-web-browsers)

Our goal is to **facilitate native support for IPFS and other decentralized protocols in web browsers in order to benefit ...**. 

- **Browser users**: Browser extensions and native-included IPFS alike expose IPFS features in a robust and intuitive way
- **Web developers**: Web developers can enjoy a smooth experience working with IPFS in browser contexts
- **Browser vendors**: Browser developers are empowered to meet the requirements of the distributed web

## Current projects

### IPFS Companion

[IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion#ipfs-companion) is a browser extension that simplifies access to IPFS resources and adds browser support for the IPFS protocol.  
It runs in <img src="https://unpkg.com/@browser-logos/firefox@2.0.0/firefox_16x16.png" width="16" height="16">Firefox (desktop and Android)
and Chromium-based browsers including
<img src="https://unpkg.com/@browser-logos/chrome@1.0.4/chrome_16x16.png" width="16" height="16">Chrome or
<img src="https://unpkg.com/@browser-logos/brave@3.0.0/brave_16x16.png" width="16" height="16">Brave.  
Check out all of [IPFS Companion's features](https://github.com/ipfs-shipyard/ipfs-companion#ipfs-companion-features) and [**install it**](https://github.com/ipfs-shipyard/ipfs-companion#install) today!


| <img src="https://unpkg.com/@browser-logos/firefox@2.0.0/firefox_16x16.png" width="16" height="16"> [Firefox](https://www.mozilla.org/firefox/new/) / [Firefox for Android](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | <img src="https://unpkg.com/@browser-logos/chrome@1.0.4/chrome_16x16.png" width="16" height="16"> [Chrome](https://www.google.com/chrome/) / <img src="https://unpkg.com/@browser-logos/brave@3.0.0/brave_16x16.png" width="16" height="16"> [Brave](https://brave.com/)
|------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [![Install From AMO](https://ipfs.io/ipfs/QmSX44XockQifmxE8Wdevkaa6vaqTXtGdH9t9aHWXZkuJq)](https://addons.mozilla.org/firefox/addon/ipfs-companion/) | [![Install from Chrome Store](https://ipfs.io/ipfs/QmPinSJKFYCMuTDh484dLk5Av4HpZRzBRR1KPv7TM7CBVF)](https://chrome.google.com/webstore/detail/ipfs-companion/nibjojkomfdiaoajekhjakgkdhaomnch) |

#### Other web extension experiments
- Exposing the IPFS API via [`window.ipfs`](https://docs.ipfs.io/how-to/companion-window-ipfs/)
- Mozilla hosts a community effort called [`libdweb`](https://github.com/mozilla/libdweb/) to implement experimental APIs for Firefox WebExtensions, with a goal of enabling dweb protocols in Firefox through browser add-ons:
  - IPFS [libdweb experiments](https://github.com/ipfs-shipyard/ipfs-companion/blob/libdweb/docs/libdweb.md), including a [native protocol handler](https://github.com/ipfs-shipyard/ipfs-companion/pull/533), [local DNS-SD discovery and TCP transport](https://github.com/ipfs-shipyard/ipfs-companion/pull/553)
  - The long-term goal of this project is to integrate these APIs into the WebExtensions ecosystem
- Support for [`chrome.sockets.*` APIs](https://github.com/ipfs-shipyard/ipfs-companion/issues/664) in Chromium browsers

### IPFS and the JavaScript ecosystem
At present, in order to run IPFS in a web browser, you must either bundle [`js-ipfs`](https://github.com/ipfs/js-ipfs) (a full IPFS node in JavaScript) with your client-side application, or use the [`js-ipfs-http-client`](https://github.com/ipfs/js-ipfs-http-client) HTTP API client library to connect to an external daemon running on a local or remote machine. To learn more, make sure to check `/examples` in both of those repos.

#### ... in service workers

- Tracking related work: [#55](https://github.com/ipfs/in-web-browsers/issues/55)
  - Highlight: IPFS gateway fully running on a service worker [service-worker-gateway](https://github.com/ipfs-shipyard/service-worker-gateway)

### Accessing the IPFS HTTP API

The standalone IPFS daemon (either `go-ipfs` or `js-ipfs` in Node) exposes the API at `/api/v0/`. It is an RPC-style API over HTTP POST.

- [API reference](https://docs.ipfs.io/reference/http/api/)
- [Client libraries in various languages](https://github.com/ipfs/ipfs#http-client-libraries)


### IPFS addressing in web browsers

See [this memo](ADDRESSING.md) for the current set of URL conventions for the IPFS community. We invite everyone to submit questions and suggestions for improvements via issues/PR.

#### DNSLink

[DNSLink](https://dnslink.io) enables you to map a domain name to an IPFS address by means of a DNS TXT record. 

- Read the [DNSLink guide](https://docs.ipfs.io/concepts/dnslink/) for details, including how to set it up on your own website 
- See details on [DNSLink in IPFS Companion](https://docs.ipfs.io/how-to/dnslink-companion/) to see additional benefits of using IPFS Companion with DNSLink support

### Signed HTTP Exchanges and WebPackage

[Signed HTTP Exchanges (SXG)](https://github.com/ipfs/in-web-browsers/issues/121) are an experimental spec proposed by Google to decouple the origin of the content from who distributes it. The IPFS gateway at ipfs.io participates in [Origin Trial for Signed HTTP Exchange (SXG)](https://developers.google.com/web/updates/2018/11/signed-exchanges), starting with Google Chrome 71. This means [anyone can publish SXG](https://developers.google.com/web/updates/2018/11/signed-exchanges#creating_your_sxg) on IPFS, and regular Chrome can load it from the ipfs.io gateway without any additional setup on the user's side.

## Q3 2020 update

### Now half of the Web Browsers & GUI Working Group!

The IPFS core team has re-activated the **Web Browsers & GUI Working Group** as a combined team of this group and the [IPFS GUI group](https://github.com/ipfs/ipfs-gui). This larger working group operates with a focus on furthering browser adoption and integration, as well as improving the functionality and usability of our GUI-based tools as a whole, with a particular focus on benefiting the onboarding of new IPFS developers and users.

### Q3 2020 OKRs (WG-wide)

As with every team within IPFS, the Web Browsers & GUI Working Group sets and adheres to quarterly OKRs (Objectives and Key Results) in order to guide our work. (You can see [all of the IPFS Project's quarterly OKRs here](https://docs.google.com/spreadsheets/d/1KVe3JCsfB-l47-DE5gvk7bT0Yly_EAPrHCi-8kCthy4/edit#gid=2125992746).)

1. Remote (third-party) pinning services are easy to use
    - Generic pinning service API spec finalized
    - `go-ipfs`/`js-ipfs`/http-client support remote pins via HTTP API
    - User flows resulting from API are understood and implemented in IPFS Companion and IPFS Desktop/Web UI
    - 2+ collabs implement API and are included in Desktop/Web UI's pinning service settings
    - Desktop/Web UI is capable of importing a 4GB file on low-memory devices
2. Maintain and improve GUI tools as a whole (as bandwidth permits in a quarter focused on Filecoin enablement)
    - Grow IPFS usage through onboarding improvements
    - Ship libs for sharing IPFS nodes across browsing contexts (tabs) on same origin
    - Understand sharing an IPFS node across different origins
    - Understand ways of leveraging IPFS Desktop when present
3. Ongoing browser collabs and grants are supported
    - Brave integration of embedded `go-ipfs` and native URIs
    - Igalia’s work on `navigator.registerProtocolHandler` and browser extension APIs
    - Kiwix is able to host ZIM on IPFS

## Get involved!

### Join a meeting

We'd love to meet you in person at one of our open Web Browsers & GUI Working Group meetings. They're a great way to get quickly up to speed on our work, including latest developments and awesome demos.

- **When:** Every other Tuesday at 16:30 UTC (check the [IPFS Calendar](https://calendar.google.com/calendar/embed?src=ipfs.io_eal36ugu5e75s207gfjcu0ae84@group.calendar.google.com&ctz=UTC) to see exact dates!)
- **Where:** https://protocol.zoom.us/j/833247793
- **Agenda**: https://hackmd.io/QaxiCU8BQqOuK8B8Tdi36g

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

- [IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion) - A WebExtension to give your browser super powers.
- [IPFS Web UI](https://github.com/ipfs-shipyard/ipfs-webui) - The IPFS Dashboard shipped with daemon, desktop app or browser extension
- [js-ipfs](https://github.com/ipfs/js-ipfs) - IPFS implementation in JavaScript
- [HTTP API Documentation](https://docs.ipfs.io/reference/api/http/) - When an IPFS node (go-ipfs or js-ipfs) is running as a daemon, it exposes an HTTP API that allows you to control the node and run the same commands you can from the command line.
    - [js-ipfs-http-client](https://github.com/ipfs/js-ipfs-http-client) - A client library for the IPFS HTTP API, implemented in JavaScript
- [IPFS GUI Working Group](https://github.com/ipfs-shipyard/pm-ipfs-gui) - Unifying and leveling up IPFS interfaces and the user journey into the Distributed Web
- [Dynamic Data and Capabilities in IPFS Working Group](https://github.com/ipfs/dynamic-data-and-capabilities) -  building blocks that enable collaborative applications, providing solutions for security, identity, access control, concurrency, synchronization, offline and near-real-time collaboration on top of IPFS
