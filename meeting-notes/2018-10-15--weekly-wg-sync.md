# GUI & In Web Browsers Weekly Sync 2018-10-15

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @fsdiogo
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

- Lab Week Summary?
- Priorities for GUI team

## Notes

### Team Updates

- @lidel
    - Done (mostly before lab week):
        - [created cross-platform orchestration for fetching webui from ipfs during companion build](https://github.com/ipfs-shipyard/ipfs-companion/pull/590#issuecomment-426827936)
        - [investigated upload issues with ipfs-cluster](https://github.com/ipfs-shipyard/ipfs-companion/issues/600)
        - [decoupled blog.ipfs.io from ipfs.io and fixed various bugs related to IPNS and DNSLink](https://github.com/ipfs/website/issues/274#issuecomment-427210000), tl;dr being:
            - PR: [fix: redirect /blog to blog.ipfs.io with IPNS support](https://github.com/ipfs/website/pull/275)
            - PR: [fix: blog permalinks that work on IPNS](https://github.com/ipfs/blog/pull/182)
        - Lab Week
    - Next:
        - Go over AI from Lab Week notes
        - New Bugfix Beta of Companion  

- @fsdiogo
    - Done:
        - Add CORS config instructions to Share Files and WebUI
            - https://github.com/ipfs-shipyard/ipfs-share-files/pull/40
            - https://github.com/ipfs-shipyard/ipfs-webui/pull/839
        - Add fixed footer with code links
            - https://github.com/ipfs-shipyard/ipfs-webui/pull/809
        - Add git revision
            - https://github.com/ipfs-shipyard/ipfs-webui/pull/844
        - Add Web UI intro to files page
            - https://github.com/ipfs-shipyard/ipfs-webui/pull/847
        - Glasgow Team Week


### Discussion Highlights

- Plan for ipfs-desktop
    - focus on basics for first iteration 
        - visual revamp / wireframes / i18n
        - autoupdates for ipfs-desktop AND go-ipfs shipped with it 
- Plan for ipfs-share-files
    - come up with better onboarding text
- Additional work around GUI
    - paginated directory listing 
    - alternative to http polling (realtime API)
    - in general, identify missing APIs and communicate to *-ipfs 

### Action Items

- @all go over backlogs and AIs from Team Week
