# GUI & In Web Browsers Weekly IRC Sync 2018-07-16

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @fsdiogo
  - @olizilla
  - @hacdias
  - @alanshaw

## Goals

- GUI
    - Core IPFS features are intuitve and accessible to all
    - Everyone is empowered to make great new IPFS user interfaces
    - The GUIs push forward understanding and adoption of IPFS
- Web Browsers 
    - Browser developers are committed to addressing requirements of the distributed web
    - Ensure smooth experience for web developers in browser contexts
    - Create a developer ecosystem around window.ipfs apps


## Agenda

### Before the Sync

- Write down your updates
    - What have you accomplished since the last Weekly?
    - Were there any blockers? If so, which ones? Is it still blocked? Why?
    - What is the next important thing you should focus on?

### Regular

- Ask everyone to put their name into the list of attendees
- Go over everyone's updates and ask if there are any questions or things to discuss
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?

### Added

- Finalize OKRs for Q3:
    - we may want to schedule separate ~1h call for this on Tuesday
        - every KR should have an owner, we may split/merge things depending on who gets what
        - we should a list of what is needed from other WG' ready for OKR review on 18th 
- How should we handle CIDv0 in browser extension?
    -  converting to CIDv1 is not enough with current nodes, so displaying option to copy cidv1b32 will frustrate users as things won't work
    -  should we handle CIDv0 as a special case and convert root to CIDv1 (ipfs.files.chcid) ?

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Updates

- @lidel
    - Worked on OKRs for Q3, published draft in the  `wb` sheet: [Web Browsers OKRs](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/edit?ts=5b28e2d5#gid=755202447)
    - Restored gateway redirect for CORS XHRs in Firefox:    
      https://github.com/ipfs-shipyard/ipfs-companion/pull/511
      - This shipped to stable channel just in time for https://ournetworks.ca/livestream/ :-))
    - Filled for a visa to attend DWEB 2018 (it takes tiiiime)
    - Fixed and released a bunch of improvements to stable channel.    
      See Release Notes for [v2.4.1](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.4.1) and [v2.4.2](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.4.2)
    - Had a busy week in Berlin
        - Lightning Talk about Web Browsers WG:  https://ipfs.io/ipfs/QmYh7rfHj8sBL7f6ssEXWssuzjHUwyqHyPFy7NcNUFKs1Y/#0
        - Base32 Strike Force was born: https://github.com/ipfs/ipfs/issues/337
            - Created tasks to support [CID as a Subdomain](https://github.com/ipfs/in-web-browsers/issues/89) 
            - Drafted steps for [Companion support for Base32 CIDv1](https://github.com/ipfs-shipyard/ipfs-companion/issues/527)
    - Discovered some issues with window.ipfs.files.cp (need some feedback):
      https://github.com/ipfs-shipyard/ipfs-companion/issues/530
    - Fixed linkify experiment on hackmd (not merged yet):
      https://github.com/ipfs-shipyard/ipfs-companion/pull/528
    - Fixed pubsub with js-ipfs via window.ipfs (not merged yet):
      https://github.com/ipfs-shipyard/ipfs-companion/pull/529
    - Discovered an issue with libdweb in latest Firefox Nightly:
      https://github.com/mozilla/libdweb/issues/16 (fixed)
    - Next:
        - Release beta with recent PRs
        - AFK on Wednesday (VISA interview at US embassy) until evening call 
        - Create IPFS demo branch with the latest version of Protocol handler API:
          https://github.com/mozilla/libdweb/issues/2 

- @fsdiogo
    - Done:
        - Worked on revamping the peers page on the WebUI
            - Added the world map with coordinates to show peers
            - Added the peers table
        - Developers Meeting in Berlin
        - Updated the peers table to use react-virtualized
    - Next:
        - Add dynamic location to the map & table

- @hacdias
    - Done:
        - Kept working on Files Browser page on WebUI
            - [Add a new folder](https://github.com/ipfs-shipyard/ipfs-webui/pull/721)
            - [Truncate text on small screens + a new tooltip](https://github.com/ipfs-shipyard/ipfs-webui/pull/717)
            - [Use pull streams](https://github.com/ipfs-shipyard/ipfs-webui/pull/719)
            - [Now File Browser works with non-ascii characters](https://github.com/ipfs-shipyard/ipfs-webui/pull/716)
            - [Some Tweaks](https://github.com/ipfs-shipyard/ipfs-webui/pull/723)
        - Finally managed to continue the Awesome IPFS static website
            - [The Pull Request](https://github.com/ipfs/awesome-ipfs/pull/130)
            - [Try it out!](https://ipfs.io/ipfs/QmNcn9s3jV6QZ6eixgwmm6gagFGmKaUM5ftWoTN3qwa5Ba/)
    - Next:
        - Waiting for reviews on the tweaks PR.
        - Hopefully finish and merge the Awesome IPFS.
    - About the OKRs and Q3 (don't have permission to edit the file):
        - WebUI on Desktop!
        - I don't know a lot about IPLD and how everything works together, but I'd like to take a shot at **IPLD explorer supports 3 exotic formats (ipld-git, ipld-btc, ipld-eth-*)** OKR.
        - Can help with **Web UI pages are published as standalone webapps that can be linked to from new apps (e.g. filecoin explorer)**.

- @alanshaw
    - Done:
        - Berlin
            - base32 discussion (see update from @lidel), and consequence: assigned myself responsibility for js-ipfs base32
        - Hacked on https://github.com/ipfs-shipyard/ipfs-companion/pull/520 with @lidel
    - Next:
        - Finish peer location bundle for WebUI and add to status page

- @olizilla
  - Done:
    - Drafted OKRs for GUI team https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/edit?ts=5b489369#gid=1841105909
    - Gave the GUI Team update at Berlin dev conf https://ipfs.io/ipfs/QmTj8em6XKSfNLX6Xo6eKfp3K7sGpgj8hSwtck7p3jij98/
    - IPLD start page and large list fixes https://github.com/ipfs-shipyard/ipfs-webui/pull/690
    - Webui nav toggle
  - Next:
    - Present GUI OKRs
    - Webui status page
    - Extract ipld explorer as standalone webapp.

### Agenda

#### Finalize OKRs for Q3

We decided to have a <1h call and go over all OKRs, set priorities and leaders together.
     
#### How should we handle CIDv0 in browser extension?

We decided there will be no CIDv0-specific UI items for now  apart from providing conversion UI in native protocol handler, which is something we can't avoid.

### Action Items
- @all: keep doing good work :-)
