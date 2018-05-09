# GUI & In Web Browsers Weekly IRC Sync 2018-04-30

- **Lead:** @lidel
- **Notetaker:** {@lidel}
- **Attendees:**
  - @lidel
  - @agata_krych
  - @olizilla
  - @hacdias
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
- WebUI update
- Goals for Lisbon Hack Week
- Should we move sync 1h earlier? or to other day?

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Browser Extension

* Researched `window.ipfs` perf
	* TLDR; the content scripts also add constructor @ `window.Ipfs`, this adds a **~500ms** delay, suggested removing it

### New WebUI

* Started work on WebUI 2.0 foundations
	* Tech Stack
		* Started by using Aegir found a few pain points
		* Looked into options for e2e testing and found Google's Puppeteer to be least flakey, quickest, and free
		* All findings written up here: https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/51#issuecomment-385425256
	* Reviewing wireframes
		*  [Drag and drop](https://invis.io/AVGRKKJ75KT#/293709612_File_screen_-_drag-drop_in_subfolder)
		*  [Share single file](https://invis.io/AVGRKKJ75KT#/293742323_Share_screen_-_single_item)
		*  [Share a few files](https://invis.io/AVGRKKJ75KT#/293763510_Share_screen_-_few_items)
		*  [Share folder](https://invis.io/AVGRKKJ75KT#/293767639_Share_screen_-_folder)
	* Reviewing design
		* [Status screen](https://invis.io/AVGRKKJ75KT#/294213577_Start_Webui_Design) 
		* [Smaller menu version](https://invis.io/AVGRKKJ75KT#/294213563_Start_Webui_Design_Small_Menu)

### Other

- [PR with discussion on awesome-ipfs being a static site](https://github.com/ipfs/awesome-ipfs/pull/130)
- http://arewedistributedyet.com interviews started, Oli wrote some thoughts on [what is needed to extend browsers with p2p protocols](https://github.com/ipfs-shipyard/arewedistributedyet/issues/19)
- [Add a "desktop" friendly init profile to go-ipfs](https://github.com/ipfs/go-ipfs/issues/4989)

## Action Items
- Please take a read through the [Aegir findings](https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/51#issuecomment-385425256)
- everyone to go over proposed WebUI designs and provide feedback (ASAP)
- think about IPLD Explorer, provide thoughts at https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/11 (ok to do it ater this week)
