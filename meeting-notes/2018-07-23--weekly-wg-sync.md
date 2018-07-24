# GUI & In Web Browsers Weekly IRC Sync 2018-07-23

- **Lead:** @lidel
- **Notetaker:** @lidel
- **Attendees:**
  - @fsdiogo
  - @lidel
  - @alanshaw
  - @hacdias
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
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?

### Added

- Plan/sync DWEB Summit 2018 talks (@lidel, @alanshaw)
- What's missing in the WebUI status page? (@fsdiogo, @olizilla)
- {add anything you want to discuss / show}


## Notes

_Extracted from the meetings irc logs in #in-web-browsers_


### Updates

- @alanshaw
    - Done
        - Finished peer locations bundle ([#702](https://github.com/ipfs-shipyard/ipfs-webui/pull/702))
        - Working on peer country chart ([#734](https://github.com/ipfs-shipyard/ipfs-webui/pull/734))
    - Blocked
        - `null`
    - Next
        - Pie charts for up/down speed and disk quota

- @fsdiogo
    - Done:
        - Integrated peer locations bundle
            - Added peers locations to the world map
            - Added the flags to the peers table
        - Shipped the revamped peers page
    - Next:
        - File sharing flow

- @hacdias
    - Done:
        - Kept working on File Browser page
        - Thought about caching and started implementing it as a proof-of-concept
        - Awesome IPFS published (https://awesome.ipfs.io)
    - Next:
        - Find a way to make reactX functions to be called on time (https://github.com/ipfs-shipyard/ipfs-webui/pull/736) otherwise we won't have a responsive WebUI.


- @lidel
    - Done:
        - Added streaming and basic error handling to libdweb's ipfs:// ([wip PR](https://github.com/ipfs-shipyard/ipfs-companion/pull/533))
        - Added support for CID in subdomains to [is-ipfs](https://github.com/ipfs/is-ipfs) and Companion ([PR](https://github.com/ipfs-shipyard/ipfs-companion/pull/537))
        - window.ipfs.files.cp|mv scoping fix [PR](https://github.com/ipfs-shipyard/ipfs-companion/pull/531)
        - Created initial draft of "IPFS Addressing in Web Browsers" Memo ([PR](https://github.com/ipfs/in-web-browsers/pull/92))
    - Next:
        - Release Beta and Stable before Dweb Summit
        - Work on presentations for Dweb Summit and PL Day
        - Write up feedback on ipfs:// (edge cases such as video tag) 

### Agenda

- Discuss next work focus for @fsdiogo
    - Sharing seems like a good pick, can be worked in a fashion that is mostly decoupled from Files screen.
- Should we rename webui `revamp` branch to `master` and `master` to `legacy`?
    - Ok, but need to finish status page and have NPM package ready to get buy in from go-ipfs and js-ipfs to ship ship ship

### Action Items

- @fsdiogo will look into "Sharing via IPFS" flow, design and screens
    - https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/34
- @lidel, @alanshaw, @daviddias: met tomorrow and discuss Dweb Summit talks
