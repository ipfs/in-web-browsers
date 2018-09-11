# GUI & In Web Browsers Weekly Sync 2018-09-10

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @hacdias
    - @olizilla
    - @alanshaw
    - @fsdiogo
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

### Added

- What is missing for "having WebUI CID for PR against go-ipfs"? :-)
- Q4 Planning is almost here. 
    - The various calls will take place Sept 24-28. 
    - Still time, but we should start thinking about OKRs for Q4. 
- olizilla: Let's do the sync call (with rad demos) on Wednesdays as of next week.

## Notes

### Team Updates

- @lidel
    - Last week:
        - Various PR reviews
            - Really excited about [js-ipfs-api: add support for chunked uploads](https://github.com/ipfs/js-ipfs-api/pull/851) as a way of solving multiple issues with uploads of huge files over HTTP API.
        - [Small progress with bundling go-ipfs with Brave](https://github.com/brave/brave-browser/issues/819#issuecomment-418713997)
        - [Shipped Translation Project for IPFS GUIs](https://github.com/ipfs/ipfs-gui/issues/50)
            - Moved js.ipfs.io, WebUI and Companion to Transifex:
              https://www.transifex.com/ipfs/public/
              - [Set up automatic sync of source files](https://github.com/ipfs/ipfs-gui/issues/50#issuecomment-419680213)
        - [Released IPFS Companion v2.5.0](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.5.0). DNSLink is enabled by default now.
        - [Created a sandbox illustrating current problems with the lack of range request semantics in libdweb's Protocol Handler API](https://github.com/lidel/libdweb/tree/video-range-use-case-demo/demo/protocol#dweb-range-request-sandbox)
    - Next:
        - PR Reviews, Go over Q3 backlog
- @hacdias
    - Last week:
        - i18n https://github.com/ipfs-shipyard/ipfs-webui/pull/772 (props to @lidel)
        - 💄ing the status page:
            - https://github.com/ipfs-shipyard/ipfs-webui/pull/780
            - https://github.com/ipfs-shipyard/ipfs-webui/issues/778

- @alanshaw
    - Last week:
        - Made progress on `--cid-base` option to js-ipfs (working here https://github.com/ipfs/js-ipfs/tree/feat/cid-base-option)
        - js-ipfs 0.32.0-rc.1 is out, rc.2 coming soon (waiting on https://github.com/ipfs/js-ipfs/pull/1543)
    - Next:
        - Send PR for `--cid-base`
        - Write interop tests for retrieve from block store by any CID version
        - Implement that ^^ in js-ipfs

- @olizilla
  - Done:
    - Extracted IPLD explorer as a reusable module and use from IPLD Explorer and Web UI
      - https://github.com/ipfs-shipyard/ipld-explorer-components
    - WIP on i18n in story books for component only modules
  - Next:
    - fix perf issue or disable bandwidth per peer.
    - Add ipfs provider info to status page
    - handle ipfs connection errors.
    - Web UI polish / snagging list.
    - publish webui.ipfs.io
    - user goals & user test scripts
    - interviewing Dan Ordille

- @fsdiogo
    - Done:
        - IPFS Share Files got deployed
            - It’s not online yet because CI is giving me a fight 
        - Worked on the landing pages for Companion
            - https://github.com/ipfs-shipyard/ipfs-companion/pull/565
    - Next:
        - Landing pages for Companion
        - Add copy to IPFS Share Files
        - Add translations to IPFS Share Files


### Discussion Highlights

- Right now the entire team is in EU, so [we will move sync call to 9:30 AM UTC](https://github.com/ipfs/in-web-browsers/issues/106#issuecomment-419872656)
- [PR](https://github.com/ipfs-shipyard/ipld-explorer-components/pull/1/files) with a neat way of passing HTML tags (formatting, links) into ICU translation keys: `Some <0>stuff</1>, some <1>other</1> stuff`
- js-ipfs work related to cidv1b32 is progressing, adding support for `--cid-base` to all commands
- [IPFS Translation Project at Transifex](https://www.transifex.com/ipfs/public/) is live! ([original issue](https://github.com/ipfs/ipfs-gui/issues/50))
- It is okay for landing page in Companion to give shell command example when API is off. We will make it more user-friendly when IPFS Desktop in refreshed version lands.
- We've identified [things that need to be done before we can ship WebUI](https://github.com/ipfs-shipyard/ipfs-webui/issues/749). 
    - We want to get some community feedback before we PR a new hash to go-ipfs.

### Action Items

- @all: **think about OKRs for Q4**, [add async notes/ideas to the hackpad in this issue](https://github.com/ipfs/in-web-browsers/issues/110)
-  @all: [any ideas on how we could get vanity hostnames for localhost gateway?](https://github.com/ipfs/in-web-browsers/issues/109)
- @lidel: create issue for UX when webui + companion produce problem due to config.get being blocked over window.ipfs
  - done: https://github.com/ipfs-shipyard/ipfs-webui/issues/787
