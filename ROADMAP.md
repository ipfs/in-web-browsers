# Roadmap for IPFS in Web Browsers

> This page provides the community with a high level overview of our current priorities and ongoing endevours.

### Table of Contents

* [Roadmap](#roadmap)
    * [Goals](#goals)
    * [Prerequisites](#prerequisites)
    * [Long Game](#long-game)
* [Quarterly Objectives and Key Results](#quarterly-objectives-and-key-results)
    * [Q3 2018](#q1-2018)
        * [Browser developers are addressing requirements of the distributed web](#browser-developers-are-addressing-requirements-of-the-decentralized-web)
        * [Ensure smooth experience for web developers in browser contexts](#ensure-smooth-experience-for-web-developers-in-browser-contexts)
        * [Browser extension exposes IPFS features in a robust and intuitive form](#browser-extension-exposes-ipfs-features-in-a-robust-and-intuitive-form)
    * [Q2 2018](#q2-2018)
    * [Q1 2018](#q1-2018)

# Roadmap

### Goals
- **Native support in the Browsers:** protocol handlers for decentralized web protocols, especially IPFS and IPLD, bundled natively in web browsers.
- **Dapps are just.. apps:** creating web applications with IPFS is a viable alternative to HTTP-based stack.

### Prerequisites
- *DONE:* Implement [js-ipfs](https://github.com/ipfs/js-ipfs) and [js-ipfs-api](https://github.com/ipfs/js-ipfs-api)
- *DONE:* Create browser extension ([ipfs-companion](https://github.com/ipfs-shipyard/ipfs-companion)) that detects IPFS resources and redirects requests to local gateway.

### Long Game
- *IN PROGRESS:* Make [js-ipfs](https://github.com/ipfs/js-ipfs) and [go-ipfs](https://github.com/ipfs/go-ipfs) interoperate seamlessly
- *IN PROGRESS:* Improve extension so it handles distributed protocols natively without need for third party software.
- *IN PROGRESS:* Define the APIs, address schemes, security models, etc.
- *IN PROGRESS:* Make the case for IPFS & Decentralized Web Protocols in Web Browsers with Use Cases, Sample Applications, Demos and Delightful Documentation
- *IN PROGRESS:* Work with browser vendors on adding missing APIs and solving discovered problems.

# Quarterly Objectives and Key Results

We try to frame our ongoing work using a process based on quarterly Objectives and Key Results (OKRs).
Objectives reflect outcomes that are challenging, but realistic. Results are tangible and measurable.

## Q3 2018

This is a markdown version of [2018 Q3 IPFS OKRs Spreadsheet](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/#gid=755202447).    
Is is provided here as-is, see original document for priorities, assignments and progress.

### Browser developers are addressing **requirements of the decentralized web**

_Support the conversation with browser vendors. Make it as easy as possible for them to see where we are at, what's needed and why._

- Finished switch to base32 CIDv1 as the default across entire IPFS ecosystem [#](https://github.com/ipfs/ipfs/issues/337)
- Created at least three IPFS demos using experimental WebExtension APIs from mozilla/libdweb [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/343)
- IPFS Companion with embedded go-ipfs ships with Chromium-based Brave by default [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/312#issuecomment-385017637)
- Published final draft of “Addressing on the Decentralized Web” and found a champion to take it further [#](https://github.com/lidel/specs/tree/dweb-addressing/dweb-addressing) / [#](https://github.com/ipfs/in-web-browsers/pull/92)

### Ensure **smooth experience for web developers** in browser contexts

_Improve DX of existing features. Make it easy to start playing with IPFS in the browser today._

- Browser-focused checks exist for js-ipfs(-api) and are part of CI. Build fails if tests don't pass when bundled by all the bundlers or run over maximum bundle sizes
- IPFS in Firefox and Chrome supports upload of 5GB file without crashing or slowing down the UI (via Companion / window.ipfs / HTTP API)


### Browser extension exposes IPFS features in a **robust and intuitive form**

_Improve user experience. Make it easy to perform common operations without commandline._

- There is a smooth 3-step user onboarding flow (offer, install, welcome) for Companion and Desktop (OKR from GUI WG) [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/324)
- Companion reuses file sharing, browsing and ipld exploring flows from Web UI (OKR from GUI WG) [#](https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/35), [#](https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/34)
- New WebUI ships inside of Companion bundle and is re-used for sharing/uploads, file management, exploring peer info and config editor [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/514)
- User is able to define multiple API backends and switch between them via browser menu [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/491)
- Preferences, ACL and Upload screens follow visual language established by WebUI and ipfs-css [#](https://github.com/ipfs/ipfs-gui/issues/7)
- Performance impact of content script that injects `window.ipfs` decreases by at least 50% [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/460)
- One click to add a snapshot/screenshot of current web page to IPFS [#](https://github.com/ipfs-shipyard/ipfs-companion/issues/91#issuecomment-191220446)

## Q2 2018

Moved to [2018 Q2 IPFS OKRs Spreadsheet](https://docs.google.com/spreadsheets/d/1xIhKROxFlsY9M9on37D5rkbSsm4YtjRQvG2unHScApA/#gid=755202447).

## Q1 2018

Moved to [2018 Q1 IPFS OKRs Spreadsheet](https://docs.google.com/spreadsheets/d/1clB-W489rJpbOEs2Q7Q2Jf1WMXHQxXgccBcUJS9QTiI/#gid=1872064387).
