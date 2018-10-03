# GUI & In Web Browsers Weekly Sync 2018-10-01

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @olizilla
    - @lidel
    - @fsdiogo

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

- Check-in: are we okay with continuing having one sync for both WGs in Q4?
- > {?}

## Notes

### Team Updates

- @lidel
    - Done:
        - Finalized draft of [Q4 OKRs: ipfs-in-web-browsers](https://docs.google.com/spreadsheets/d/139lROP7-Ee4M4S7A_IO4iIgSgugYm7dct620LYnalII/#gid=755202447) and prepared update on Q3 and plans for Q4
        - Solved cid issues and got PR to [add support for CIDv1 and Base32 to js-ipfs-http-response](https://github.com/ipfs/js-ipfs-http-response/pull/9) merged.
        - Fixed [Companion detection in ipfs-redux-bundle in Chromium](https://github.com/ipfs-shipyard/ipfs-redux-bundle/pull/14)
        - Created PoC for [optional translations of selected posts at blog.ipfs.io](https://github.com/ipfs/blog/pull/180)
    - Next:
        - Release Companion Beta with pending PRs (WebUI, improved context-menus, upload fix)
        - Prepare talks for Lab Week

- @olizilla
  - Done:
    - :rocket: Tag v2 of Web UI https://github.com/ipfs-shipyard/ipfs-webui/releases/tag/v2.0
    - https://webui.ipfs.io - DNS and Jenkins config for continuous deployment from master
    - Simplify the peers page - extract and optimise the map insted of dyamically generating it.
    - First draft of the usability testing plan for Web UI
    - PR to announce Web UI in ipfs daemon console output https://github.com/ipfs/js-ipfs/pull/1595
    - Q3 OKRs review and Q4 OKR presentation

  - Next:
    - Initial user research for Lab week
    - Fix p1 items on Web UI and PR to js-ipfs and go-ipfs
    - IPFS Desktop release plan and dev

- @fsdiogo
    - Done:
        - Add loading states before download starts
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/34
        - Updated the README
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/35
        - Add postcss and css-modules demo to IPFS UI Components
            - https://github.com/olizilla/ipfs-react/pull/2
        - WebUI fixes
    - Next:
        - Add CORS config to Share Files add page
        - WebUI P0/P1s

### Discussion Highlights

- Everyone is focused on two things: shipping WebUI and finishing OKR planning :)

### Action Items

- @olizilla: <del>review: https://github.com/ipfs-shipyard/ipfs-redux-bundle/pull/14</del> done
