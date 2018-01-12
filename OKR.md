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

- Improve UX for Desktop & Companion ([ipfs-companion/#324](https://github.com/ipfs-shipyard/ipfs-companion/issues/324), [ipfs-companion/#342](https://github.com/ipfs/ipfs-companion/issues/342))
- Publish a ui-style-guide repo to define the design language of IPFS apps
- Implement the style guide UI recommendations in Companion & Desktop
- Improve test coverage for Desktop & Companion
- Implement CI process for Companion ([ipfs-companion/#145](https://github.com/ipfs/ipfs-companion/issues/145))
- Jenkins jobs build Desktop installers and Companion bundles for all supported platforms
- Publish signed releases of Desktop
- Update the _"Getting started"_ section of https://ipfs.io to recommend Desktop
- Publish welcoming, up-to-date documentation for Companion & Desktop
- Companion uses a `js-ipfs` node used when a system IPFS daemon is not available.
- Companion exposes IPFS Core API as `window.ipfs`  ([in-web-browsers/#42](https://github.com/ipfs/in-web-browsers/issues/42), [ipfs-compaion/#330](https://github.com/ipfs-shipyard/ipfs-companion/issues/330))
- Update PeerPad to use the `window.ipfs` if available.
- Provide a step-by-step guide for developers to create apps that use `window.ipfs`, using PeerPad as the example.
- [Brave](https://brave.com) supports IPFS out-of-the-box
- [Brave](https://brave.com) supports `ipfs://` and `dweb:/ipfs` address schemes in Location Bar and DOM elements (`href`, `src`)
- `ipfs-dashboard` is built as a reusable replacement for `ipfs-web-ui`
- Update `ipfs-dashboard` to use `window.ipfs` if available.
- Companion can start and stop the Desktop IPFS node ([in-web-browsers/#12](https://github.com/ipfs/in-web-browsers/issues/12))
- Maintain a 5 star rating for Companion in the Chrome Web Store and the Firefox Add on store
- Create logos for Desktop and Companion to give each an identity that shows they separate parts that work together ([pm-ipfs-gui#24](https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/24))
