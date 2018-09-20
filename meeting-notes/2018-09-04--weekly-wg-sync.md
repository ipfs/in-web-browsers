# GUI & In Web Browsers Weekly Sync 2018-09-04

- **Lead:** @lidel
- **Notetaker:** @olizilla
- **Attendees:**
    - @hacdias
    - @fsdiogo
    - @lidel
    - @olizilla 

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

### Added

- Lets try video call once again! (post link on irc)
- @lidel: Translation Project
    - moving to Transifex?
    - how to handle i18next translations? (https://github.com/ipfs-shipyard/ipfs-webui/pull/772#issuecomment-418106980)
- @hacdias: new hour for our sync
- {?}

## Notes

### Team Updates

- @lidel
    - Done:
        - [Researched and added some notes on crowdsourcing translations of our GUI apps](https://github.com/ipfs/ipfs-gui/issues/50)
        - [Released IPFS Companion v2.4.4.10960 (Beta)](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.4.4.10960)
            - Simplified language around DNSLink and enabled it by default in best-effort mode
        - [Created a small test suite for checking if there are any known regressions at our public gateway](https://github.com/ipfs/infrastructure/pull/430)
        - [PR with a fix for 'invalid Read on closed Body' in files.add under Chrome](https://github.com/ipfs-shipyard/ipfs-companion/pull/562)
        - [PR for js-ipfs to add  `X-Ipfs-Path`, `Etag`, `Cache-Control`, `Suborigin` headers](https://github.com/ipfs/js-ipfs/pull/1537)
  - Next:
      - Release of IPFS Companion (Stable)
      - Move companion to Transifex, create PoC CI setup
      - Go over pending PRs

- @hacdias
    - Done:
        - WebUI: [Finished the Status Page](https://github.com/ipfs-shipyard/ipfs-webui/pull/766)
        - WebUI: [Simplified the file adding process (props to @lidel)](https://github.com/ipfs-shipyard/ipfs-webui/pull/769)
        - WebUI: [Started working on i18n](https://github.com/ipfs-shipyard/ipfs-webui/pull/772)
        - Desktop: [Remove Pinning and Add By Path (not merged yet)](https://github.com/ipfs-shipyard/ipfs-desktop/pull/655)
    - Next:
        - Integrate file-share-app with WebUI (w/ @fsdiogo)
        - Finish i18n for WebUI
        - Translate Web UI to PT (?)
        - Expand graphs on status page

- @fsdiogo
    - Done:
        - Finished download flow
        - Refactored share link logic to lower its workload 
        - Added loading component when fetching the file tree
        - [Opened an issue in ipfs/infrastructure to create the share.ipfs.io domain](https://github.com/ipfs/infrastructure/issues/429)
    - Next:
        - Deploy IPFS Share Files
        - Work on the landing pages for Companion

- @olizilla
  - Done:
    - re-use ipld explorer as git submodule
    - wip on re-use as a module (create module and webapp in same project)
  - Next:
    - webui node connection provider info
    - [handle ipfs connection errors](https://github.com/ipfs-shipyard/ipfs-webui/issues/773)
    - [publish webui to webui.ipfs.io](https://github.com/ipfs-shipyard/ipfs-webui/issues/775)
    - Decide on i18n format.

### Discussion Highlights

#### Notes about i18n

Background: https://github.com/ipfs/ipfs-gui/issues/50

- i18next
    - Can also support ICU format (https://react.i18next.com/misc/using-with-icu-format)
    - **Pros**
        - Easy to use.
    - **Cons**
        - Not supported on transifex without a third-party plugin.
- React Intl
    - **Pros**
        - Maybe more future proof
        - Supported on transifex
    - **Cons**
        - Is it activelly maintained (https://github.com/yahoo/react-intl/issues/1160)?
        - Default props have to go in the component calls directly??? Like `<FormattedMessage id='key' defaultMessage='Hello' />` (there might be workarounds)
        - Too many components
