# GUI & In Web Browsers Weekly IRC Sync 2018-08-20

- **Lead:** @lidel
- **Notetaker:** @lidel
- **Attendees:**
    - @fsdiogo
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

- @lidel, @olizilla: [Mid-Quarter OKR Scoring for Q3 2018](https://github.com/ipfs/in-web-browsers/issues/101)

## Notes

### Updates

_Added in async mode before IRC sync_

- @lidel
    - **Two weeks ago** (everyone else was afk so we had no sync):
        - Went over backlog and notes from Dweb/LabDay, created issues in various repos
            - Highlight:  filled SVG/WEBM/ContentType issues with mozilla/libdweb, most got addressed by @Gozala already :-)
        - Started work on re-using [ipfs-http-response](https://github.com/ipfs/js-ipfs-http-response) in ipfs-companion, so we have the same directory listing and content-type heuristics in js-ipfs, service worker gateway and ipfs-companion
            - Blocker: [missing CIDv1 support](https://github.com/ipfs/js-ipfs-http-response/issues/8), started working on PR
            - Identified some missing apis, missing/spotty support for hamd-sharding: looking into ways to address that in generic and reusable way that works today
        - Switched libdweb branch to `async` handler (https://github.com/mozilla/libdweb/pull/59), which enabled us to set contentType based on first 512 bytes of received payload. Issues with webm and svg are solved, but use in `src` attribute works only within same origin/protocol:
            -  **cross-origin**: assets within the same protocol but under different root CIDs do not load: https://github.com/mozilla/libdweb/issues/55
            -  cross-protocol: `ipns://` page loading assets from `ipfs://` does not work: https://github.com/mozilla/libdweb/issues/52
    - **Last week**:
        - companion+libdweb
            - Switched to latest libdweb
                - Cross-origin assets within the same protocol now load fine, demo: `ipfs://bafkreihosso7nxtyhjtpvjmrdoflyup6ex6b2xgzezibavuonobt2l4dai`
            - Looked into `ipns://tr.wikipedia-on-ipfs.org` issues with with embedded js-ipfs node
                - right now fails on deep links due to sharding: https://github.com/ipfs/js-ipfs/issues/1279#issuecomment-413307589
        - http://arewedistributedyet.com
            - Moved under vendor-agnostic org (following plan from [issue 25](https://github.com/arewedistributedyet/arewedistributedyet/issues/25#issuecomment-411730739))
            - CI does not work after the move, handed it over to @VictorBjelkholm, tracked [here](https://github.com/ipfs/testing/issues/126)
            - In an effort to get [this](https://github.com/arewedistributedyet/arewedistributedyet/issues/23) off the ground opened issue for changing WHATWG HTML Spec to include DWeb protocols on the "safelist": https://github.com/whatwg/html/issues/3935
                - [This](https://github.com/arewedistributedyet/arewedistributedyet/issues/23#issuecomment-413881896) comment describes how protocol "safelist" support looks like in Firefox, Chrome and Brave.
        - Identified and reported a bug: [ipfs.files.add with {cidVersion: 1} returns CID of an empty file](https://github.com/ipfs/js-ipfs/issues/1518)
    - Next:
        - Add WebExtension context support to [ipfs-redux-bundle](https://github.com/ipfs-shipyard/ipfs-redux-bundle) and see identify any blockers for bundling WebUI with Companion
        - Create PoC [dnslink support with X-Ipfs-Path](https://github.com/ipfs-shipyard/ipfs-companion/issues/548) (in effort to have dnslink enabled by default in stable channel without waiting for DNS TXT lookup API)

- @hacdias (this includes the previous week)
    - Got better from the allergy!
    - Worked on JS-IPFS and external APIs support for IPFS Desktop (https://github.com/ipfs-shipyard/ipfs-desktop/pull/651)
    - Working on WebUI: Files Polishing: https://github.com/ipfs-shipyard/ipfs-webui/issues/748

- @fsdiogo
    - Done:
        - Vacations
    - Next:
        - Continue the work on ipfs-share-files

- @alanshaw
  - Done:
    - Initial working version of discovery and transport using libdweb: https://youtu.be/LDHFqwC8Syg
    - Added mid-quarter review https://github.com/ipfs/ipfs-gui/issues/63#issuecomment-413509702
  - Next:
    - Begin work towards base32 CIDs in earnest

### Notes from Sync

_Extracted from the meetings irc logs in #in-web-browsers_

- Discussed [ipfs-shipyard/ipfs-share-files](https://github.com/ipfs-shipyard/ipfs-share-files) for some time
    - [Work in progress demo video](https://usercontent.irccloud-cdn.com/file/eGJos9w5/up.mov)
    - We want to plug it into WebUI for sharing feature and embedd it into ipfs-companion to replace current Quick Upload screen
    - "Download directory tree as `.tar.gz`" feature can be done via HTTP API: `curl https://ipfs.io/api/v0/get?arg=/ipfs/QmRAJM5ByzuKKpzKKisGDwBPHzYqMvVrYC2PcVhkMnP3gd&archive=true&compress=true > archive.tar.gz`
        - We need to see how to handle this in context of embedded js-ipfs in browser (no local HTTP API)
    - We want to be able to pass a list of CIDs via URL to enable use case where user selects multiple files in WebUI and clicks "share"
- Discussed 3 step onboarding flows for webui / companion / desktop as another nice-to-have priority before Q3 ends
    - some 'landing page' prior art/discussions: https://github.com/ipfs-shipyard/ipfs-companion/issues/324, https://github.com/ipfs/ipfs-gui/issues/27
- Discussed [User testing plan for webui / companion / desktop](https://github.com/ipfs/ipfs-gui/issues/62)
    - webui will go first, when initial version of revamp branch is released and shipped with companion/desktop we will unblock them to follow 


### Action Items

- @all with a KR for Q3:
    - Do a score of your KRs on [Mid-Quarter OKR Scoring for Q3 2018](https://github.com/ipfs/in-web-browsers/issues/101)
- @olizilla, @fsdiogo + interested parties will have a call about [ipfs-shipyard/ipfs-share-files](https://github.com/ipfs-shipyard/ipfs-share-files) at 2018-08-21 10:00AM GMT – link will be posted on IRC
