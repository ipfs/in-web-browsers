# GUI & In Web Browsers Weekly IRC Sync 2018-06-18

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @agata_krych
  - @alanshaw
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

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Updates

- @olizilla
    - busy on filecoin-explorer last week, demo going out soon
    - Next: wrap up filecoin work, work on webui for the rest of the week (settings page, then addressing feedback for DAG Explorer)
- @lidel
    - removed browserify, finished our switch to webpack (including content scripts), the PR is merged: https://github.com/ipfs-shipyard/ipfs-companion/pull/498
    - created poc for global ON/OFF switch:  https://github.com/ipfs-shipyard/ipfs-companion/pull/500
    - Next: merge on/off PR, create a PR with backend selector (as noted in https://github.com/ipfs-shipyard/ipfs-companion/issues/491), then get back to libdweb PoCs
- @alanshaw
    - on holiday last week \o/
    - Next: getting back to things today, providing feedback, clearing out inbox etc
- @hacdias
    - finished the delete prompt and the rename one is almost done
    - Next: pass the last exam :-^-)
- @agata_krych
    - "too many projects, not enough agatas"
    - To tame the chaos, new design work needs to be requested via https://github.com/protocol/design/issues
    - Invision screens waiting for feedback:
        - https://invis.io/AVGRKKJ75KT#/302166384_IPLD_screen
        - https://invis.io/AVGRKKJ75KT#/302167366_Peers_screen
        - https://invis.io/AVGRKKJ75KT#/302169242_Settings_screen
        - https://invis.io/AVGRKKJ75KT#/302173034_File_screen_-_rename_file
        - https://invis.io/AVGRKKJ75KT#/302173033_File_screen_-_delete_file
    - Next: waiting for feedback or requests, will get back to webui/status page soon


### Action Items

- @all: review Invision screens (links above)
