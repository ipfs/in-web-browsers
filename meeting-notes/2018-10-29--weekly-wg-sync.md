# GUI & In Web Browsers Weekly Sync 2018-10-29

- **Lead:** @olizlla
- **Notetaker:** @lidel
- **Attendees:**
    - @fsdiogo
    - @olizilla
    - @alanshaw
    - @hacdias
    - @lidel

## Goals

- [Web Browsers WG](https://github.com/ipfs/in-web-browsers)
    - Browser developers are addressing requirements of the distributed web
    - Ensure smooth experience for web developers in browser contexts
    - Browser extension exposes IPFS features in a robust and intuitive form
- [GUI WG](https://github.com/ipfs/ipfs-gui)
    - Core IPFS features are intuitive and accessible to all
    - Everyone is empowered to make great new IPFS user interfaces
    - The GUIs push forward understanding and adoption of IPFS

## Agenda

### Before the Sync

- Write down your updates
    - What have you accomplished since the last Weekly?
    - Were there any blockers? If so, which ones? Is it still blocked? Why?
    - What is the next important thing you should focus on?
- Read updates of others
    - Any there any questions, requests to communicate?


### Regular

- Ask everyone to put their name into the list of attendees
- Go over everyone's updates and ask if there are any questions or things to discuss
- Everyone can demo something!
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?

## Notes

### Team Updates

@lidel

- Done
    - Researched and documented strategies for: [What happens when i18n efforts grow bigger and cover more than IPFS?](https://github.com/ipfs/i18n/issues/3)
    - Shared some context on preload nodes with @kyledrake and @eefahy. [Expired cert is fixed](https://github.com/ipfs/infrastructure/issues/443), FYSA Kyle is planning to move preload nodes to own infrastructure, where the cert will auto-update, preventing this in the future.
    - Documented known issues and ways of improving UX of [`ipfs files write`](https://github.com/ipfs/interface-ipfs-core/blob/e5d90e29cab9735f12bbca225b76ba8273e3b9d8/SPEC/FILES.md#fileswrite) (trickle-dag) vs. [`ipfs files add`](https://github.com/ipfs/interface-ipfs-core/blob/e5d90e29cab9735f12bbca225b76ba8273e3b9d8/SPEC/FILES.md#filesadd) (default, merkle-dag) if we decide to [revamp IPFS Files API (hackpad by @olizilla)](https://hackmd.io/MzxjQdwfRWSj6bdbfk7p4g?view)
    - [WIP] Researched design decisions and low level discussions related to `window.ethereum`, added more notes to [our issue](https://github.com/ipfs-shipyard/ipfs-companion/issues/589)
- Blocked
    - Need PR Review: [js-ipfs-api/pull/875](https://github.com/ipfs/js-ipfs-api/pull/875)
- Next
    - new beta ipfs-companion
    - continue `window.ipfs 2.0`

@alanshaw

* Done
    * Released `jsipfs@0.33.0-rc.2`
        * Update to Web UI 2.1.1 [#1653](https://github.com/ipfs/js-ipfs/pull/1653)
        * Remove Hapi `maxBytes` restriction allowing large file uploads from the browser [#1645](https://github.com/ipfs/js-ipfs/pull/1645)
    * Released `jsipfs@0.33.0-rc.3`
        * Allows the Web UI to detect and connect to origin without the user having to configure the API multiaddr [#1660](https://github.com/ipfs/js-ipfs/pull/1660)
    * Attempted release 0.33, and delayed due to:
        * Running tests for [orbitdb/ipfs-log](https://github.com/orbitdb/ipfs-log) failed with [#1615](https://github.com/ipfs/js-ipfs/issues/1615), now fixed by [#1617](https://github.com/ipfs/js-ipfs/pull/1617)
        * `js-unixfs-engine` upgraded to `js-ipld@0.18` (a breaking change), causing 2 versions of `ipld` to be included in `js-ipfs`. Resolution is to also bring this breaking change into `js-ipfs@0.33`. PR open to resolve [#1668](https://github.com/ipfs/js-ipfs/pull/1668)
    * Created **Awesome Endeavour: Async Iterators** [#1670](https://github.com/ipfs/js-ipfs/issues/1670)
        * Converted `js-libp2p-crypto` and `js-libp2p-crypto-secp256k1` to use async/await over the weekend ([#131](https://github.com/libp2p/js-libp2p-crypto/pull/131) and [#9](https://github.com/libp2p/js-libp2p-crypto-secp256k1/pull/9))
        * It faster! https://github.com/libp2p/js-libp2p-crypto/pull/131#issue-226279844
    * PR open to AEgir for prereleases support [#289](https://github.com/ipfs/aegir/pull/289)
* Blocked
    * `n/a`
* Next
    * [Many PRs to review, merge and release for IPLD breaking change](https://github.com/ipfs/js-ipfs/pull/1668#issuecomment-433074668)
    * Release `js-ipfs@0.33`
    * Work on `--cid-base` option

- @hacdias
  - Done:
    - Kept working on desktop with Oli's new designs: https://github.com/ipfs-shipyard/ipfs-desktop/pull/662
  - Next:
    - (this will be a *huge* week for me at uni so I won't be as available as usual)
    - Keep working on Desktop
    - Take a look at https://github.com/ipfs/js-ipfs/issues/1670

- @fsdiogo
    - Done:
        - Week off
    - Next:
        - Finish pending PRs in the Web UI

- @olizlla
    - Done:
      - IPFS Desktop design research and proposal https://github.com/ipfs/ipfs-gui/issues/44#issuecomment-432998304
      - Make IPFS Web UI work out of the box with js-ipfs https://github.com/tableflip/uri-to-multiaddr/commit/82540e7edd6e182807142c36681eb3bcd1c4627f
      - Fix https://libp2p.io/media/ layout https://github.com/libp2p/website/pull/85
      - IPFS Roadmap refinements https://docs.google.com/document/d/13_4_23Jrth7HBZ1QD6ezJaLRYCHN32xJLA5c0z3IOkc/edit?ts=5bd2ee0d#
    - Next:
        - IPFS Roadmap wrangling
        - Desktop project management
        - I18n lang selector issues
        - Get share app ready to integrate with webui 
        - Upgrade ipld explorer and webui with latest IPLD breaking changes.

### Discussion Highlights

- @olizilla presented some mockups of simplified ipfs-desktop UI based on menu from ipfs-webui – [ipfs-gui/issues/44](https://github.com/ipfs/ipfs-gui/issues/44#issuecomment-432998304)
  - @hacdias implemented a poc in [ipfs-desktop/pull/662](https://github.com/ipfs-shipyard/ipfs-desktop/pull/662#issuecomment-433200688) :))
- ipfs-webui is being announced by js-ipfs daemon and is able to automagically discover its API port \o/
- IPFS Roadmap for 2019: we should start thinking how our WGs fit within the bigger picture 
- "window.ipfs 2.0" update by @lidel
  - tl;dr we may not be able to avoid having 1 bit of fingerprinting surface due to UX, so we could just go with thin `window.ipfs` that returns full API after `window.ipfs.enable(<capabilities>)` call.
  - feedback & details in [ipfs-companion/issues/589](https://github.com/ipfs-shipyard/ipfs-companion/issues/589)
 - UX discussion around manual Language selector in ipfs-webui – [ipfs-webui/pull/866](https://github.com/ipfs-shipyard/ipfs-webui/pull/866/)
 - Awesome Endeavour: Moving to Async Iterators in all JS libraries – [js-ipfs/issues/1670](https://github.com/ipfs/js-ipfs/issues/1670)
 - Quick chat about decentralized annotations – [ipfs-shipyard/discussify-browser-extension](https://github.com/ipfs-shipyard/discussify-browser-extension)

### Action Items

- @all: read, comment and contribute to [IPFS Project Roadmap Doc](https://docs.google.com/document/d/13_4_23Jrth7HBZ1QD6ezJaLRYCHN32xJLA5c0z3IOkc/)
