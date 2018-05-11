# GUI & In Web Browsers Weekly IRC Sync 2018-05-08

- **Lead:** @lidel
- **Notetaker:** {no volunteer, @lidel did his best}
- **Attendees:**
  - @agata_krych
  - @olizilla
  - @alanshaw

## Goals

- Our GUI apps expose core IPFS features in a robust, accessible and intuitive form
- Browser developers are committed to addressing requirements of the distributed web
- Create a developer ecosystem around window.ipfs apps

## Agenda

### Regular

- Ask everyone to put their name into the list of attendees
- Round of updates
  - What have you accomplished since the last Weekly?
  - Were there any blockers? If so, which ones? Is it still blocked? Why?
  - What is the next important thing you should focus on?
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?

### Added

- WebUI updates
- Lisbon Hack Week (who is coming? what should be the focus?)
- Enabling DWeb exploration at Mozilla
- Mid quarter OKR checkin

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Browsers

- IPFS Companion
	- Fixed websocket handshake being broken by Companion and released along with other stuff as [v2.2.2](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.2.2)
	- Automated bundle builds for 'stable' and 'beta' channels, added CI smoke test for Windows dev
	- Looking at [addressing webcrypto limitations in Chrome](https://github.com/ipfs-shipyard/ipfs-companion/issues/475)
- Enabling DWeb exploration at Mozilla
	- Internal discussion at Mozilla was initialized by @gozala (Thanks!)
	- The focus so far is to plan work related to proper protocol handler, socket API and webrtc datachannels, expect updates at some point

### New WebUI

- Getting together WebUI 2.0 base
	- Exploring how to Redux without the boilerplate
	- Next: research and make decisions on create-react-app vs parcel, redux patterns
- [Getting IPLD working in JS-IPFS](https://github.com/ipfs/js-ipfs-api/pull/755) so we can create an IPLD explorer that also works with JS-IPFS

### Other

- Adding test harness to peer-pad to avoid prod errors in fututre
	- Overview: [Testing Peerpad with Puppeteer](https://www.youtube.com/watch?v=g0l738fq3C0)
	- Next: trying to recreate the yarn build issue, as it seems significant if there are issues building new webui
- PSA: Alan have taken on lead maintainer role for [js-ipfs](https://github.com/ipfs/js-ipfs), [js-ipfs-api](https://github.com/ipfs/js-ipfs-api) and [interface-ipfs-core](https://github.com/ipfs/interface-ipfs-core/)

## Action Items

- All: think about IPLD Explorer, provide thoughts, sample screens, mockups at https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/11

- All: fill mid-quarter OKR scores
	> Following up, I want to ask you to spend 30 minutes this week scoring your OKRs on the [Q2 OKR spreadsheet](https://docs.google.com/spreadsheets/d/1xIhKROxFlsY9M9on37D5rkbSsm4YtjRQvG2unHScApA/edit#gid=755202447). For this exercise, I’m asking you to:
	> - Do a score of your KRs on its current state (0 to 1 with regards to completion) - Mid-Q Actual Column
	> - Do a score of your KRs on what you believe the degree of completion by the end of the Quarter (0 to 1) - Mid-Q Projection Column
	> - Do a self-check on Priorities. See if the things you are working on are the most important ones, if they are not, explain to yourself why and check in if they are indeed more important that what is listed. If they happen to be more important, explain it to the team, if they are not, drop it in favor of the more important ones.
