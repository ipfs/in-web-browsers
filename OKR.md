# Objectives and Key Results

Quarterly statement of OKRs (Objectives and Key Results) for the "IPFS in Web Browsers" effort.

## Q1 2018 (WORK IN  PROGRESS)

- **Note:** This is work-in-progress document, not yet finalized. Please create PR against it with your own goals/proposals.
- **TODO:** Add your goals/proposals to the section below, as PRs :-)

**[IPFS Companion](https://github.com/ipfs/ipfs-companion) is a solid foundation for browser integration(s) going forward:**

- Single codebase is running on all browsers (no forks, browser-specific modules are used instead)
- Robust CI/QA practices are established, improve test coverage ([ipfs-companion/#145](https://github.com/ipfs/ipfs-companion/issues/145))
- Up-to-date developer documentation exists
- IPFS is embeded into every browser page through `window.ipfs` ([ipfs-compaion/#330](https://github.com/ipfs-shipyard/ipfs-companion/issues/330))
    * The feature is a setting that can be toggled on and off
    * `window.ipfs` is a proxy over `window.postMessage` to communicate with a running IPFS node exposed by the extension ([ipfs-postmsg-proxy](https://github.com/tableflip/ipfs-postmsg-proxy))
    * Access controls prevent web pages from performing actions without prior user approval
        * Access control is fine grained, it requires permission to be granted to each IPFS function prior to usage, with option to allow access to all
        * Granted permissions are scoped to the origin (site) on which they are granted and persist until the browser process exits. When granting permission, the user is given the option for the grant to be "remembered" for a given origin so that it persists across browser restarts
        * Settings allow the user to revoke "remembered" privileges given to origins
    * Streaming APIs operate correctly (do not buffer content into memory) ([ipfs-postmsg-proxy/#2](https://github.com/tableflip/ipfs-postmsg-proxy/issues/2))
- Get one IPFS Web Application to learn how to use the IPFS Companion IPFS node if it is available (i.e PeerPad). Document the process..

**Improved initial experience for non-technical users of mainstream browsers:**

- Continuous presence in browser extension stores (pass/address reviews on time)
- Catering to less-technical users of Firefox or Chrome
  - Simplified and improved UX  ([ipfs-companion/#324](https://github.com/ipfs-shipyard/ipfs-companion/issues/342) etc)
  - Display a Landing Page (user-focused primer on distributed web) after initial install ([ipfs-companion/#324](https://github.com/ipfs/ipfs-companion/issues/324))
  - UX without local go-ipfs node is improved under Firefox (eg. embedded js-ipfs is used for uploads, public gateway for downloads)

**[Brave](https://brave.com) is the first browser with "native" IPFS support:**

- IPFS connectivity working out-of-the-box in Brave
  - Embedded js-ipfs runs in Brave without installing external daemon
  - User experience is the same as in Firefox when running external node
- Support for native protocols in Location Bar and DOM elements (`href`, `src`)

**Structure documentation and discussion around the primary Browser vendor concerns:**

- `dweb:` proposal is documented
- `Ways to deal/support the Content Origin Policy for IPFS links` are documented
