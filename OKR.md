# IPFS in web browsers: Objectives and Key Results - Q1 2018

**WORK IN PROGRESS. This document will change.**


## We have a shared understanding of how IPFS _should work_ in web browsers

_Focus on people. What are the user journeys; what are their goals. How will IPFS improve a web users day?_

### Key results

- Create **the** reference document for what users goals are when using IPFS as part of their daily web browsing.
- Document user journeys that capture an ideal UX for achieving those goals.
- Document how dat and beaker are being used for this today.
- Start a regular distributed web meetup in London.


## Browser developers understand the requirements of the decentralized web.

_Support the conversation with browser vendors. Make it as easy as possible for them to see where we are at, what's needed and why._

### Key results

- **Publish `arewedistributedyet.com` as a communal call to action.**
  - Collate the initial list of apis needed [in-web-browsers/#35](https://github.com/ipfs/in-web-browsers/issues/35)
  - Publish the list, with a tests where possible, a short summary on what it would allow, and a list of p2p projects that want it. ([in-web-browsers/#24](https://github.com/ipfs/in-web-browsers/issues/24))
- **Create a final draft spec for [addressing on the Decentralized Web](https://github.com/ipfs/specs/tree/master/dweb-addressing)**


## Lower the barrier to entry for casual users

_Improve the onboarding experience. Make it easy to use IPFS in the browser today._

### Key results

- **IPFS Desktop replaces go-ipfs as the recommended starting point for new users**
  - **TBC!** _what are the plans for ipfs-desktop?_
  - Update _"getting started"_ section of https://ipfs.io
  - `ipfs-dashboard` is built as a reusable replacement for `ipfs-web-ui`
  - Update `ipfs-dashboard` to use `window.ipfs` if available
  - Create a ui-style-guide repo as a guide to the design language of IPFS apps, and share look and feel with `ipfs-companion`, `ipfs-desktop` and `ipfs-dashboard`
  - A logo for dashboard, desktop and companion to give each an identity that shows they separate parts that work together?
- **[IPFS Companion](https://github.com/ipfs/ipfs-companion) is the reference implementation of IPFS in the browser**
  - Simplified and improved UX  ([ipfs-companion/#324](https://github.com/ipfs-shipyard/ipfs-companion/issues/324) [ipfs-companion/#342](https://github.com/ipfs/ipfs-companion/issues/342))
  - Welcoming, up-to-date developer documentation exists
  - Retain positive presence in browser extension stores
  - Robust CI/QA practices are established, improve test coverage ([ipfs-companion/#145](https://github.com/ipfs/ipfs-companion/issues/145))
  - Detect [IPFS Desktop](https://github.com/ipfs-shipyard/ipfs-desktop) and provide additional controls ([ipfs-companion/#350](https://github.com/ipfs-shipyard/ipfs-companion/issues/350))
  - Embedded `js-ipfs` node used when a system ipfs daemon is not availble.
  - IPFS api is available via `window.ipfs` ([ipfs-compaion/#330](https://github.com/ipfs-shipyard/ipfs-companion/issues/330))
  - Update PeerPad to use the `window.ipfs` if it is available
  - Provide a step by step guide for devs to create apps that use `window.ipfs`, using PeerPad as the example.
- **Get the [Brave](https://brave.com) integration released**
  - IPFS companion working out-of-the-box in Brave
  - Support for `ipfs://` and `dweb:/ipfs` address schemes in Location Bar and DOM elements (`href`, `src`)

