# GUI & In Web Browsers Weekly Sync 2018-11-05

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @lidel
    - @fsdiogo
    - @olizilla
    - @hacdias
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

### Added Agenda Items

- @lidel: Should we move meeting notes to ? 
  - Current location: [ipfs/in-web-browsers/meeting-notes](https://github.com/ipfs/in-web-browsers/tree/master/meeting-notes)
  - Alternative location: [ipfs/pm/meeting-notes/](https://github.com/ipfs/pm/tree/master/meeting-notes/2018)
    - Why? Better discovery, JS, Cluster and DDC WGs are there
- @lidel: sync with @Gozala – who can join? (today, right after js-core sync)

## Notes

### Team Updates

@lidel

- Done
    - QA and interop testing of ipfs-webui related to directory uploads - [ipfs-webui/issues/872](https://github.com/ipfs-shipyard/ipfs-webui/issues/872)
    - Fixed some bugs and released a new beta: [ipfs-companion v2.5.1.11970](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.5.1.11970)
    - Updated `js-ipfs-api/examples/upload-file-via-browser` to work with big files and optionally keep filenames - [js-ipfs-api/pull/884](https://github.com/ipfs/js-ipfs-api/pull/884)
    - [IPFS distributions website](https://dist.ipfs.io) will now publish checksums for every new artifact - [ipfs/distributions/pull/199](https://github.com/ipfs/distributions/pull/199)
    - Added QUIC to js-multiaddr - [js-multiaddr/pull/71](https://github.com/multiformats/js-multiaddr/pull/71)
        - band-aid release with fixed ipfs-webui: [ipfs-companion v2.5.1.12010](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.5.1.12010)
    - github/email catch up
    - Started some code related to window.ipfs 2.0 but run out of time last week :(
- Blocked:
    - We need [js-multiaddr/pull/71](https://github.com/multiformats/js-multiaddr/pull/71) to be merged & released to fix [ipfs-webui/issues/878](https://github.com/ipfs-shipyard/ipfs-webui/issues/878)
    - Are we good with releasing WebUI with Companion Stable? (go-ipfs and js-ipfs both ship the new version..)
- Next
    - Release ipfs-companion to Stable?
    - [Participate in the Origin Trial (Signed HTTP Exchanges)](https://developers.google.com/web/updates/2018/11/signed-exchanges) ([context](https://github.com/ipfs/in-web-browsers/issues/121))
    - third time's a charm: window.ipfs 2.0

- @hacdias
  - Done:
    - https://github.com/ipfs-shipyard/ipfs-desktop/issues/669
  - Next:
    - https://github.com/ipfs-shipyard/ipfs-desktop/issues/669

@alanshaw
* Done:
    * Released `js-ipfs 0.33.0` - thanks for all the Web UI work! 🥰 💖
    * We had a bumper week last week, MANY closed PRs and issues
        * ![Throughput Graph](https://ipfs.io/ipfs/QmQeEyDPA47GqnduyVVWNdnj6UBPXYPVWogAQoqmAcLx6y)
* Blocked:
    * `null`
* Next:
    * Roadmapping 2019 for JS IPFS
    * Work on `--cid-base` option

@fsdiogo
- Done:
    - Language selector
        - https://github.com/ipfs-shipyard/ipfs-webui/pull/866
    - Storybook
        - https://github.com/ipfs-shipyard/ipfs-webui/pull/862
- Next:
    - Storybook
    - OKRs

### Discussion Highlights

- Bugfix/release week, shipping PRs and closing issues
- PR with ipfs-desktop 1.0 
    - How to expose ipfs-desktop settings without having two settings screens
    - Expose them on Web UI Settings screen
- Manual language selector lands in Web UI, some tooling is born out of necessity
- [The 100th release of IPFS Companion!](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.5.1.11970)
- [js-ipfs 0.33.0](https://blog.ipfs.io/51-js-ipfs-0-33/) \o/
- Move Meeting Notes to ipfs/pm? Yup. – [#130](https://github.com/ipfs/in-web-browsers/issues/130)
- Sync with @Gozala scheduled after js-core call

### Action Items

- @all: spend some time thinking about priorities in 2019
- @lidel: write some thoughts on exposing ipfs-desktop settings in ipfs-webui - DONE: [ipfs-desktop/issues/674 (comment)](https://github.com/ipfs-shipyard/ipfs-desktop/issues/674#issuecomment-436251422)
- @lidel, @alanshaw, @olizilla – sync with @Gozala
