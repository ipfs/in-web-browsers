# GUI & In Web Browsers Weekly IRC Sync 2018-08-28

- **Lead:** @lidel
- **Notetaker:** olizilla
- **Attendees:**
    - @hacdias
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
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?

### Added

- Lets try Zoom Call!
- PSA from @lgierth: CFP for chaos communication congress will start sometime soon

## Notes

### Team Updates

- @lidel
    - Done:
        - Enable DNSLink by default in IPFS Companion: https://github.com/ipfs-shipyard/ipfs-companion/pull/558
            - Thoughts?
        - Brave discussion moved to a new repository in which and I wrote a summary that includes recent developments and started research towards current bundling conventions: https://github.com/brave/brave-browser/issues/819#issuecomment-415792868
  - Next:
      - Merge things and release new Companion Beta
      - Check/addifmissing X-Ipfs-Path to js-ipfs gw
      - Research and add some notes on Translations: https://github.com/ipfs/ipfs-gui/issues/50

- @fsdiogo
    - Done:
        - Polished the upload flow
        - Add flow
        - Download flow
    - Next:
        - Finish download flow and quirks
        - Ship IPFS Share Files

- @hacdias
    - Done:
        - Charts for Status Page
        - Merged the new Welcome page of WebUI (w/ @olizilla)
        - Files navigation through arrow keys and some shortcuts
        - Started working on Status Page: https://github.com/ipfs-shipyard/ipfs-webui/pull/766
        - Started working on js-ipfs support for Desktop: https://github.com/ipfs-shipyard/ipfs-desktop/pull/651
    - Next:

- @alanshaw
    - Done
        - Fixed issue with `files.add --cid-version=1` [#1518](https://github.com/ipfs/js-ipfs/issues/1518)
        - Upgraded the [IPLD explorer CLI tool](https://www.npmjs.com/package/ipld-explorer-cli) to use IPLD directly and resolve all sorts of node types. Also now works with js-ipfs daemon \o/!!!!
        - Made progress investigating areas of the API that will be affected by adding a `--cid-base` option
    - Next
        - Continue base32 CID work [#1440](https://github.com/ipfs/js-ipfs/issues/1440)

- @olizilla
    - Done
      - Fixed issue with ipld explorer not showing dag-pb with cid v1 address
      - Fixed issue where you couldn't path into unamed dag-pb links
      - Interviews for Community Engineer and Community Manager roles
    - Next
      - Reuse ipld explorer from webui
      - Add i18n plumbing to webui

### Discussions from <del>IRC</del> video call

_Extracted from the meetings irc logs in #in-web-browsers_

- We tested syncing over video call
  - Everyone picks one item from updates and gives a quick demo followed by short discussion/Q&A
  - Worked quite well, we will try again next week and think about recording as we get more familiar with the formula

### Action Items

- @all post thoughts or :+1 for [PR to enable DNSLink by default in Companion](https://github.com/ipfs-shipyard/ipfs-companion/pull/558)
- @all read/contribute to the [plan for Translations across our GUI apps](https://github.com/ipfs/ipfs-gui/issues/50)
