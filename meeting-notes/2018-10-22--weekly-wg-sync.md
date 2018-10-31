# GUI & In Web Browsers Weekly Sync 2018-10-22

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
    - @olizilla
    - @lidel
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

- How did London Meetup go? :)

## Notes

### Team Updates

@fsdiogo
- Done:
    - Updated  pie charts tooltip to display clearer info
        - https://github.com/ipfs-shipyard/ipfs-webui/pull/859
    - Fixed notify bundle to differentiate connection and files failures
        - https://github.com/ipfs-shipyard/ipfs-webui/pull/860
    - [WIP] Fixed storybook
        - https://github.com/ipfs-shipyard/ipfs-webui/pull/862
    - [WIP] Add language selector
        - https://github.com/ipfs-shipyard/ipfs-webui/pull/866
- Next:
	- Week off

@alanshaw
- Done:
  - [IPFS London meeetup](https://www.meetup.com/london-ipfs/events/255386386/)
  - [Released js-ipfs-api@25](https://github.com/ipfs/js-ipfs-api/releases/tag/v25.0.0) with fix for big uploads
    - @olizilla immediately found [#1638](https://github.com/ipfs/js-ipfs/issues/1638), and I fix [#1645](https://github.com/ipfs/js-ipfs/pull/1645)
  - [Released js-ipfs 0.33.0-rc.1](https://github.com/ipfs/js-ipfs/issues/1635) with new Web UI \o/
- Next:
  - Complete work on `--cid-base` option for js-ipfs [#1552](https://github.com/ipfs/js-ipfs/pull/1552)


@lidel
- Done: 
	- Created a summary about potential IPFS use cases for [Signed HTTP Exchanges and WebPackage](https://github.com/ipfs/in-web-browsers/issues/121)
	- Tested IPFS Companion with [recently released](https://brave.com/new-brave-browser-release-available-for-general-download/) Chromium-based Brave Browser,  it can be installed from Chrome Web Store and [works without any changes](https://cloudflare-ipfs.com/ipfs/QmV7cL21fJUJ283d9Mwefty5YzdXMXDaRaj2z9bY3R2FnL/2018-10-22-105404_900x519_scrot.png) \o/  
	- Researched why the [fix for random UI glitches: check only for recursive pins](https://github.com/ipfs-shipyard/ipfs-companion/pull/594) did not work in Companion
		- Identified a bug in js-ipfs-api that ignores checks for specific pin types: [PR with fix](https://github.com/ipfs/js-ipfs-api/pull/875)
		- Added regression tests in separate [PR for  interface-ipfs-core](https://github.com/ipfs/interface-ipfs-core/pull/375)
- Next:
	- Release Companion Beta
	- Identify open problems and create work plan for ["window.ipfs" 2.0](https://github.com/ipfs-shipyard/ipfs-companion/issues/589)

@hacdias
- Done:
	- Organized some issues related to IPFS Desktop's next version:
		- https://github.com/ipfs-shipyard/ipfs-desktop/issues/669
		- https://github.com/ipfs-shipyard/ipfs-desktop/issues/668
		- https://github.com/ipfs-shipyard/ipfs-desktop/issues/618
		- https://github.com/ipfs/ipfs-gui/issues/44
		- **I need feedback from everyone reading this!** 😁
- Next:
	- Start working towards the new IPFS Desktop version:
		- Decouple Settings screen from the main menubar to have more room and space to breath.

### Discussion Highlights

- IPFS London Meetup was a success, a lot of good talks 
- ipfs-companion runs in Brave 0.55 
- ipfs-webui will land in js-ipfs soon
- Fixing bugs, ramping up for work on ipfs-desktop

### Action Items

- @all: provide feedback for ipfs-desktop issues and plan
- @alanshaw: review PRs: [js-ipfs-api/pull/875](https://github.com/ipfs/js-ipfs-api/pull/875) & [interface-ipfs-core/pull/375](https://github.com/ipfs/interface-ipfs-core/pull/375) 
- @olizilla & @alanshaw: figure out how to properly detect API port of js-ipfs in ipfs-webui
