# Objectives and Key Results

Quarterly statement of OKRs (Objectives and Key Results) for the "IPFS in Web Browsers" effort.


## Q1 2018 (WORK IN  PROGRESS)

**Note:** This is work-in-progress document, not yet finalized. Please create PR against it with your own goals/proposals.

 - **TODO:** Add your goals/proposals to the section below, as PRs :-)

### OKR Proposals


#### @lidel's focus/goals/proposals

- **[IPFS Companion](https://github.com/ipfs/ipfs-companion) is a solid foundation for browser integration(s) going forward**
  - [ ] Single codebase is running on all browsers (no forks, browser-specific modules are used instead)
  - [ ] Robust CI/QA practices are established, improve test coverage ([ipfs-companion/#145](https://github.com/ipfs/ipfs-companion/issues/145))
  - [ ] Up-to-date developer documentation exists
- **Improved initial experience for non-technical users of mainstream browsers**
  - Continuous presence in browser extension stores (pass/address reviews on time)
  - Catering to less-technical users of Firefox or Chrome
    - Simplified and improved UX  ([ipfs-companion/#324](https://github.com/ipfs-shipyard/ipfs-companion/issues/342) etc)
    - Display a Landing Page (user-focused primer on distributed web) after initial install ([ipfs-companion/#324](https://github.com/ipfs/ipfs-companion/issues/324))
    - UX without local go-ipfs node is improved under Firefox (eg. embedded js-ipfs is used for uploads, public gateway for downloads)
- **[Brave](https://brave.com) is the first browser with "native" IPFS support**
  - IPFS connectivity working out-of-the-box in Brave
      - Embedded js-ipfs runs in Brave without installing external daemon
      - User experience is the same as in Firefox when running external node
  - Support for native protocols in Location Bar and DOM elements (`href`, `src`)

