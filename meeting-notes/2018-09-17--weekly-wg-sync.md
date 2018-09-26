# GUI & In Web Browsers Weekly Sync 2018-09-17

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @fsdiogo
    - @lidel
    - @olizilla
    - @alanshaw

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

- @lidel: Async Retrospective of the Q3  ([context&template](https://github.com/ipfs/pm/issues/698#issue-360560672))
    - Should we have separate docs for both WG? (@lidel: I think yes? It will make it easier to link/report on 26th)
- Schedule Q4 OKR Planning Call this week
- @lidel: PSA: feel free to add i18n tips and best practices to JavaScript section in  https://github.com/ipfs/i18n

## Notes

### Team Updates

- @lidel
    - Done:
        - IPFS Translation Project (https://www.transifex.com/ipfs/public/)
            - Some PMing, reviewing i18 PRs to WebUI, adding new language coordinators etc
            - WIP: adding Memory Groups to share translations across all projects
            - Moved various notes to a dedicated repo: https://github.com/ipfs/i18n
        - IPFS Companion
            - New beta: [v2.5.0.11250](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.5.0.11250)
            - Reported&fixed [regression](https://github.com/mozilla/libdweb/issues/82) in libdweb branch with latest Firefox Nightly
                - we may have more problems like this in future, Mozilla is doing cleanup of old/unused APIs
            - Filled [Chromium bug: _Extensions API should implement manifest.json/protocol_handlers_](https://crbug.com/883274) to address UX issues from [arewedistributedyet/issues/23](https://github.com/arewedistributedyet/arewedistributedyet/issues/23#issuecomment-412892777). 
                - This is an additional task on top of  _safelisting DWeb protocols_, which is tracked in https://crbug.com/651311.
            - Investigation of [poor performance of files.add over window.ipfs in Firefox](https://github.com/ipfs-shipyard/ipfs-companion/issues/485), which manifests heavily when adding 2MB+ files with the latest WebUI. The issue is not present in Chrome, so far it looks like some events are fired twice in Firefox. 
    - Next:
        - Merge Landing Page to Companion
        - Work on OKRs (Facilitate Q3 Retrospective, Planning Q4)
        - Investigate regression found in [js-ipfs-http-response/pull/9](https://github.com/ipfs/js-ipfs-http-response/pull/9) with latest js-ipfs
        - Prepare for bundling WebUI and share app with Companion (includes looking into [files.add over window.ipfs](https://github.com/ipfs-shipyard/ipfs-companion/issues/485))

- @hacdias
    - Done
        - Reviewed some PRs
        - Been working on a new IPFS Redux Bundle version:
            - https://github.com/ipfs-shipyard/ipfs-webui/pull/792
            - https://github.com/ipfs-shipyard/ipfs-redux-bundle/pull/5
        - Tweaks on Share Files app:
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/26
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/27
    - Next:
        - Tweak last things on WebUI
        - Start revamping Desktop (?)
    - **Info** this will be my first week of classes so I'm not sure how much available I'll be yet.

- @olizilla
  - Done
      - Web UI polishing for launch
        - Tidy up UI for peers page - https://github.com/ipfs-shipyard/ipfs-webui/pull/793
        - Disable bandwidth per peer & Tidy up UI for status page - https://github.com/ipfs-shipyard/ipfs-webui/pull/789
        - Release IPLD Explorer with i18n magic and 5 locales 
          - https://github.com/ipfs-shipyard/ipld-explorer-components/pull/1
          - https://github.com/ipfs-shipyard/ipfs-webui/pull/788
        - Fix i18n local loading to use relative paths
        - PR infra for webui.ipfs.io (blocked on merge and deploy) - https://github.com/protocol/infra/pull/346
        - IPFS React UI components library alpha - https://github.com/olizilla/ipfs-react

  - Next
      - use new ipfs-redux-bundle and update ipfs provider info on status page
      - fix multiaddr parsing in ipfs-redux-bundle
      - Add js-ipfs fallback to webui
      - Move webui reavamp to master branch
      - Add docs and user test plan
      - Release webui to webui.ipfs.io and announce!
      - PR go-ipfs
      - Add Locale selector
      - IPFS UI components library

- @fsdiogo
    - Done:
        - Companion welcome page
        - Welcome page i18n
        - IPFS Share Files bugs
        - Helped with js.ipfs.io
    - Next:
        - i18n to IPFS Share Files
        - Add postcss and css-modules demo to IPFS UI Components


### Discussion Highlights

- Preparation for end of Q3 and Q4
- Last mile for WebUI 2.0
- @lidel's uplink dropped and we've lost the video :-(

### Action Items

- @lidel+@olizilla: Schedule Q4 OKR Planning Call this week
- @lidel+@alanshaw: sync about [files.add over window.ipfs](https://github.com/ipfs-shipyard/ipfs-companion/issues/485)
- @all: do async retrospective of Q3 ([links in this comment](https://github.com/ipfs/in-web-browsers/issues/110#issuecomment-421971836))
