# GUI & In Web Browsers Weekly IRC Sync 2018-06-11

- **Lead:** @lidel
- **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @hacdias
  - @olizilla

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
- (holidays, so it will be brief sync)

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

Updates:
- @lidel
    - spent some time on revisiting how we inject window.ipfs. tl;dr: Chrome limitations still stand but I was able to improve fingerprinting situation on firefox a bit using firefox-only API for injecting contentScripts, PR: https://github.com/ipfs-shipyard/ipfs-companion/pull/495
        - A digression: we may want to change approach to window.ipfs at some point to make it work more like navigator.permissions.query (solves fingerprinting and improves UX of asking multiple APIs via single dialog) but this requires either a wrapping lib  or a new webextension API.
    - While doing that I noticed pain points related to browserify, and invested some time to work towards webpack-based build. Based on initial experimentation it is not only faster than browserify but plugin ecosystem will enable us to do vendor-based builds in programmatic way. 
        - got the basic build working and ready for review: https://github.com/ipfs-shipyard/ipfs-companion/pull/498 (tl;dr its faster and produced bundles take less space)
    - Next: review/merge PRs and go over github backlog, take a stab at backend switch UI in companion, and then switch back to libdweb endeavor (revisit protocol handler after recent changes in Firefox Nightly)
- @hacdias
    - afk due to exams
    - Next: ace exams! work on webui (if time allows)
- @olizilla
    - got the explore page graph and internals refactor done
        - PR: https://github.com/ipfs-shipyard/ipfs-webui/pull/672
    - Next: focus on webui, particularly the loading and empty states for the files and explore pages
- @akrych
	- Sorry guys, did't make it :) from my side I made all designs on invision:
		- https://invis.io/AVGRKKJ75KT#/302166384_IPLD_screen
		- https://invis.io/AVGRKKJ75KT#/302167366_Peers_screen
		- https://invis.io/AVGRKKJ75KT#/302169242_Settings_screen
		- https://invis.io/AVGRKKJ75KT#/302173034_File_screen_-_rename_file
		- https://invis.io/AVGRKKJ75KT#/302173033_File_screen_-_delete_file

Action Items:
- @all: review and comment on new designs in invision (links above)
- @alan/@oli: review move to webpack https://github.com/ipfs-shipyard/ipfs-companion/pull/498
- @lidel: review DAG explorer UI https://github.com/ipfs-shipyard/ipfs-webui/pull/672
