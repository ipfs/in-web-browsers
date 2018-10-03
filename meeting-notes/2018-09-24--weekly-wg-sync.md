# GUI & In Web Browsers Weekly Sync 2018-09-24

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @fsdiogo
    - @alanshaw
    - @olizilla
    - @hacdias

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

- Finalize OKRs for Q4 so we can get some feedback from Matt
- What is left for WebUI before big ship?

## Notes

### Team Updates

- @lidel
    - Done:
        - Squashed some bugs
        - Added some docs to https://github.com/ipfs/i18n
        - Researched ways to [improve context menus in Companion](https://github.com/ipfs-shipyard/ipfs-companion/pull/585#issuecomment-422999186)
        - [Initial stab at shipping WebUI with Companion](https://github.com/ipfs-shipyard/ipfs-companion/pull/590)
        - [Added support for CIDv1 and Base32 to js-ipfs-http-response](https://github.com/ipfs/js-ipfs-http-response/pull/9)
          (the lib is re-used in libdweb branch of Companion)
    - Next:
        - Finalize OKRs, prepare for OKR call on 26th
        - Release Companion Beta with WebUI?
        
- @fsdiogo
    - Done:
        - Shipped Companion welcome page \o/
            - https://github.com/ipfs-shipyard/ipfs-companion/pull/565
        - Fixed routing on Share Files
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/29
        - Added i18n to Share Files
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/30
        - Added copy to Share Files
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/32
    - Next:
        - Add loading states before download starts
        - Complete the README on Share Files
        - Add postcss and css-modules demo to IPFS UI Components

- @olizilla
  - Done: 
    - Cleared the (known) backlog of issues for launching Web UI
    - Make peers page fast - https://github.com/ipfs-shipyard/ipfs-webui/pull/801
    - Gracefully handle ipfs connection failures https://github.com/ipfs-shipyard/ipfs-webui/pull/802
    - Wire up ipfs provider info. Add links to ipfs impl and release notes where possible - https://github.com/ipfs-shipyard/ipfs-webui/pull/802
    - Lazy load `ipld`. It's large, and only used if you start exploring ipld, so we only load it if you use it. https://github.com/ipfs-shipyard/ipfs-webui/pull/804
  - Next: 
    - Move webui revamp to master branch
    - Release webui to webui.ipfs.io and announce!
    - Define Q4 OKRs and present to Lab.
    - IPFS WebUI user testing plan
    - WebUI in IPFS Desktop first iteration

- @hacdias
  - Done:
    - Improved IPFS Redux Bundle
    - Reviewed some PRs
    - Started researching for the new IPFS Desktop (https://github.com/ipfs-shipyard/ipfs-desktop/issues/661)
  - Next:
    - IPFS Desktop plan
    - Start Working on IPFS Desktop

- @alanshaw
    - Done:
        - Released new ipfs-postmsg-proxy
            - Fixes window.ipfs slow buffer serialization in Firefox (https://github.com/tableflip/ipfs-postmsg-proxy/pull/35)
            - Adds some unimplemented APIs (https://github.com/tableflip/ipfs-postmsg-proxy/commit/1e7919891bfd928976f974fd99e35a1cd6435a73)
        - Almost finished work on `--cid-base` option for js-ipfs
    - Next:
        - OKRs
        - Finish `--cid-base`
        - On holiday 1st - 5th Oct
      
### Discussion Highlights

- `window.ipfs` is now fast in Firefox, the [fix](https://github.com/tableflip/ipfs-postmsg-proxy/pull/35) shipped with latest Companion
- WebUI is close to being released, we are doing final polish before v2.0
- Translation project has a new home:  https://github.com/ipfs/i18n
- Share app is coming together nicely!
- OKR draft will happen this week, tracked in [#110](https://github.com/ipfs/in-web-browsers/issues/110)

### Action Items

- @all: work on OKRs
- @all: go over webui PRs and provide feedback
- @olizilla: review copy and suggest improvements for [Share app](https://github.com/ipfs-shipyard/ipfs-share-files)
