# GUI & In Web Browsers Weekly IRC Sync 2018-08-06

- **Lead:** @lidel
- **Notetaker:** {?}
- **Attendees:**
    - @hacdias
    - @lidel
    - {add youself}

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

- [@fsdiogo] I'll be on vacations until August 20th so I won't attend this sync nor next week's 
- [@fsdiogo] If you want to check the current status of the IPFS Share Files app:
    - See the video for a preview
        - https://usercontent.irccloud-cdn.com/file/eGJos9w5/up.mov
    - Checkout the master branch and run the app locally
        - https://github.com/ipfs-shipyard/ipfs-share-files
- [@lidel] Mid Quarter OKR Review and Resync
  We will do the review call on 13th so this week is a good time to prepare in async mode.
  I am asking everyone with [KR assigned](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/#gid=755202447) to take a moment and:
    - Do a score of your KRs on its current state (0 to 1 with regards to completion) - [Mid-Q Actual Column](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/#gid=755202447)
    - Do a score of your KRs on what you believe the degree of completion by the end of the Quarter (0 to 1) - [Mid-Q Projection Column](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/#gid=755202447)
    - Do a self-check on Priorities
- {add anything you want to discuss / show}
- [@hacdias] From the 11th to the 16th I won't be available. And until the end of the month I might be a bit less active, but still here.


## Notes

_Extracted from the meetings irc logs in #in-web-browsers_


### Updates

- @lidel 
    - Done: 
        - Attending Dweb Summit and Lab Day, various discussions and demos
        - Gave sprinty 5min talk on IPFS Companion at DwebSummit 
        - Implemented IPNS support in `libdweb` branch of Companion
        - One-liner build pipeline for `libdweb` branch 
        - Gave a quick demo of IPNS working with mozilla/libdweb at Lab Day on friday 
    - Next:
        - Convert a notes from Dweb Summit and Lab Day into actionable issues in respective repos
        - Go over the backlog from last week

- @fsdiogo
    - Done:
        - Implemented files upload
            - Add one or multiple files and see progress info
            - Get shareable link to access the added files
        - Added responsiveness
    - Next:
        - Vacations \o/

- @hacdias
    - Done:
        - fixed config.get on js-ipfs-api
        - New IPFS Desktop release (0.5.0) with some bug fixes and new go ipfs version
        - WebUI now has loadable components for each page
        - Enabled the share functionality on WebUI
        - Cached peers locations for 1 week
        - Some File Browser tweaks: https://github.com/ipfs-shipyard/ipfs-webui/pull/741
        - File Browser context menu
        - Worked on https://github.com/ipfs-shipyard/ipfs-webui/pull/715
    - Next:
        - Try out js-ipfs on IPFS Desktop 😁

### Notes from Agenda

- DWeb Summit & Lab Day in San Francisco
  - DWeb Summit
    - An 1h  block of IPFS Lightning Talks from first day of DWeb Summit 2018 starts at https://youtu.be/eO6pYYWZBs8?t=545
    - There is one 6h+ video per every room  per every day: https://www.youtube.com/channel/UCFa_X02QhJnP0FNpFAKyRRg/videos
      - list of talks and room info is at https://decentralizedwebsummit2018.sched.com, so it may be possible to find other IPFS talks that way
  - Lab Day was also recorded, videos will be published at https://www.youtube.com/c/IPFS-dweb/videos when ready
- New APIs (libdweb)
  - current approach is to design and smoke test new APIs in Firefox, IPFS and others demonstrate value added by those APIs by using them in our extensions, then other vendors have 1) API spec ready to implement 2) set of extensions that already consume those API
  - @lidel created short doc on running Companion with mozilla/libdweb: https://github.com/ipfs-shipyard/ipfs-companion/blob/libdweb/docs/libdweb.md
    - initial run of `npm run libdweb` takes a bit time (it downloads nightly and libdweb), but then its just `npm run libdweb:firefox`  to start it next time
  - Local Discovery in Web Browsers    
    We want to make js-ipfs compliant with mDNS implementation that follow DNS-SD, so we can use [mDNS API from mozilla/libdweb](https://github.com/mozilla/libdweb/issues/7) and get LAN discovery \o/
      - For background, see ongoing discussion Future of mDNS discovery in IPFS:
        - https://github.com/libp2p/libp2p/issues/28
        - https://github.com/libp2p/specs/pull/80
  - libp2p, mdns and TCP Socket API
    - @alanshaw noted we can inject custom configuration for libp2p when starting js-ipfs, which makes webext-only mdns and tcp transports much easier to ship
- IPFS Desktop
  - DWeb people been asking about IPFS Desktop app, we will probably focus on it as soon WebUI is in 'shippable' state (potential OKR for Q4)
  - Release notes will have a note about which go-ipfs version is shipped with it
  - At some point in future we will be looking into making it possible to switch to node-based js-ipfs as an alternative to  go-ipfs


### Action Items

- {?}
