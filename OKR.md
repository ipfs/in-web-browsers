# Objectives and Key Results for Q1 2018

Quarterly statement of OKRs (Objectives and Key Results) for the "IPFS in Web Browsers" effort.

## OKR-2018-Q1-1

#### Objective

- **[IPFS Companion](https://github.com/ipfs/ipfs-companion) is a solid foundation for browser integration(s) going forward**

#### Key Results

- Single codebase is running on all browsers (no forks, browser-specific modules are used instead)
- QA practices are established, test coverage at 80%+ ([ipfs-companion/#145](https://github.com/ipfs/ipfs-companion/issues/145))
- Up-to-date developer documentation exists

## OKR-2018-Q1-2

#### Objective

- **Improved initial experience for non-technical users of mainstream browsers**

#### Key Results

- Continuous presence in browser extension stores (pass/address reviews on time)
- Catering to less-technical users of Firefox or Chrome
  - Simplified UI
  - Display user-focused primer on distributed web after initial install ([ipfs-companion/#324](https://github.com/ipfs/ipfs-companion/issues/324))
  - UX without local go-ipfs node is improved (eg. embedded js-ipfs is used for uploads, public gateway for downloads)

## OKR-2018-Q1-3

#### Objective

- **[Brave](https://brave.com) is the first browser with "native" IPFS support**

#### Key Results

- IPFS connectivity working out-of-the-box in Brave
    - Embedded js-ipfs runs in Brave without installing external daemon
    - User experience is the same as in Firefox when running external node
- Support for native protocols in Location Bar and DOM elements (`href`, `src`)

