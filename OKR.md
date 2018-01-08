# Objectives and Key Results

Quarterly statement of OKRs (Objectives and Key Results) for the "IPFS in Web Browsers" effort.

## Q1 2018 (WORK IN  PROGRESS)

- **Note:** This is work-in-progress document, not yet finalized. Please create PR against it with your own goals/proposals.
- **TODO:** Add your goals/proposals to the section below, as PRs :-)

**[IPFS Companion](https://github.com/ipfs/ipfs-companion) is a solid foundation for browser integration(s) going forward:**

- Single codebase is running on all browsers (no forks, browser-specific modules are used instead)
- Robust CI/QA practices are established, improve test coverage ([ipfs-companion/#145](https://github.com/ipfs/ipfs-companion/issues/145))
- A welcoming, up-to-date developer documentation exists
- IPFS is embeded into every browser page through `window.ipfs` ([ipfs-compaion/#330](https://github.com/ipfs-shipyard/ipfs-companion/issues/330))
  - Opt-in or access controls exist to prevent web pages from performing actions without prior user approval
  - `window.ipfs` is a proxy over `window.postMessage` to communicate with a running IPFS node exposed by the extension ([ipfs-postmsg-proxy](https://github.com/tableflip/ipfs-postmsg-proxy))
  - Get one IPFS Web Application to learn how to use the IPFS Companion IPFS node if it is available (i.e PeerPad). Document the process..

**Improved initial experience for non-technical users of mainstream browsers:**

- Continuous presence in browser extension stores (pass/address reviews on time)
- Catering to less-technical users of Firefox or Chrome
  - Simplified and improved UX  ([ipfs-companion/#324](https://github.com/ipfs-shipyard/ipfs-companion/issues/342) etc)
  - Display a Landing Page (user-focused primer on distributed web) after initial install ([ipfs-companion/#324](https://github.com/ipfs/ipfs-companion/issues/324))
  - UX without local go-ipfs node is improved under Firefox (eg. embedded js-ipfs is used for uploads, public gateway for downloads)
- Publish IPFS UI Style Guide
  - Create a ui-style-guide repo as a guide to the design language of ipfs apps.
  - Support UI experimentation, but retain a coherent feel across apps by providing a reusable color palette, type-scale, font-familiy, and spacing, as drop-in, atomic, css rules.
  - Provide brief explanations of how, why and where to use them.
  - Document how to add new elemements. This project should expand to include reusable components and ui patterns as we create them.

**[Brave](https://brave.com) is the first browser with "native" IPFS support:**

- IPFS connectivity working out-of-the-box in Brave
  - Embedded js-ipfs runs in Brave without installing external daemon
  - User experience is the same as in Firefox when running external node
- Support for native protocols in Location Bar and DOM elements (`href`, `src`)

**Structure documentation and discussion around the primary Browser vendor concerns:**

- Create specs for addressing on the Decentralized Web
  - `dweb:` proposal is documented
  - `ipfs://` (URL-based solution) is documented
  - `Ways to deal/support the Content Origin Policy for IPFS links` are documented
  - published at https://github.com/ipfs/specs/tree/master/dweb-addressing
- Set up `arewedistributedyet.com` (domain TBC) as a communal call to action. ([in-web-browsers/#24](https://github.com/ipfs/in-web-browsers/issues/24))
  - Publish the list of apis needed, with a tests where possible, a short summary on what it would allow, and a list of p2p projects that want it.    
