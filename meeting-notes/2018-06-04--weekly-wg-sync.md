# GUI & In Web Browsers Weekly IRC Sync 2018-06-04

- **Lead:** @olizilla
- **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @agata
  - @hacdias
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

- Should we create separate waffle boards for GUI Team and in-web-browsers WG ? 
    - js-* teams seems to be utilizing them quite nicely: https://github.com/ipfs/js-ipfs/blob/master/MGMT.md
    - right now there is one huge board: https://waffle.io/ipfs/in-web-browsers

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Updates

- @akrych
  - Settings wireframe is ready for feedback: https://invis.io/AVGRKKJ75KT#/300639276_Settings_Webui_Wirefram
  - Next: addressign feedback, planning next design tasks

- @hacdias
  - Been busy with uni work :)
  - Next: get back to WebUI after exams end next week

- @lidel
    - Released small beta with some fixes for bugs from backlog
    - Made a small poc that confirmed we can't normalize URIs in protocol handler from mozilla/libdweb (an open problem: how to solve this regression)
    - Made some progress on getting a privileged (non-sandboxed) window.ipfs object work in ipfs-companion without need for any shared-secret. standard content script APIs wont work for internal page, but found possible workaround
    - Next: paused other work and looked into ways we can address CORS false-positives (https://github.com/ipfs-shipyard/ipfs-companion/issues/436), as it broke some websites. Release beta + Stable  with the workaround/fix.

- @alanshaw
    -  Added ping to window.ipfs (https://github.com/ipfs-shipyard/ipfs-companion/pull/492)
    -  Spent some time on sorting out the dag api (https://github.com/ipfs/interface-ipfs-core/issues/125)
        -  dag.resolve shouldn't exist, but it's really useful
        -  we need to improve API by dogfooding it, namely in IPLD Explorer in new WebUI
    - Next:  get the proposal for DAG API accepted & implemented, holiday next week

- @olizilla
    - Tracked down the "already piped" bug in js-ipfs (https://github.com/libp2p/js-libp2p-switch/pull/262)
    - Reviewed the rad Files screen in new WebUI made by @hacdias
    - Learning about dag get vs dag resolve for the IPLD page, prototyping UIs and missing IPLD APIs that are needed for IPLD Explorer in new WebUI
    - In brave news, together with @lidel figured out what we'd like to improve next in companion and what would be needed for brave

## Action Items

- @all: comment/provide feedback on https://invis.io/AVGRKKJ75KT#/300639276_Settings_Webui_Wireframe
- @olizilla, @hacdias ++ go over comments in Invision, help Agata build the list of "whats next"
- @all: comment on proposed _New UI for Backend Control_ in browser extension: https://github.com/ipfs-shipyard/ipfs-companion/issues/491
