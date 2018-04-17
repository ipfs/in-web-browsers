# GUI & In Web Browsers Weekly IRC Sync 2018-04-16

- **Lead:** @lidel
- **Notetaker:** @olizilla
- **Attendees:**
  - alanshaw
  - olizilla
  - lidel
  - jonkrone
  - kyledrake
  - agatakrych
  - hacdias


## Goals

- Our GUI apps expose core IPFS features in a robust, accessible and intuitive form
- Browser developers are committed to addressing requirements of the distributed web
- Create a developer ecosystem around window.ipfs apps


## Agenda

- Ask everyone to put their name into the list of attendees
- Round of updates
  - What have you accomplished since the last Weekly?
  - Were there any blockers? If so, which ones? Is it still blocked? Why?
  - What is the next important thing you should focus on?
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?
- Updated OKRs for Q2 after initial feedback from David
- What should be the first step for Brave integration?
- Splitting GUI WG?
- where are we with WebUI? 
    - will [name change](https://github.com/ipfs-shipyard/ipfs-webui/issues/612) happen?
    - does it make sense to start building backed in a new branch?
- Review remaining issues if there is time left
- IPFS branch in Beaker
- Tech choices https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/51


## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Beaker Browser working on read-only ipfs support.

- https://github.com/beakerbrowser/beaker/tree/ipfs-readonly
- Let's ask what their plan is for implementation (external daemon, or embedded node?), and help make this a thing.


### ipfs-companion v2.2.1 released. 

- Feedback on v2.2 rolling in, issues getting fixed. https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.2.1
- Discussion needed on hide window.ipfs from sites (privacy / fingerprinting) https://github.com/ipfs-shipyard/ipfs-companion/issues/451


### Awesome-ipfs and demo apps

- IPFS Bandwidth viewer https://tableflip.github.io/ipfs-peer-bw-example/dist/
- Building apps is helping us find the apis we need https://github.com/ipfs/go-ipfs/issues/4740#issuecomment-381546347
- Work started on building the cataglog https://github.com/hacdias/awesome-ipfs
- Work in progress on a "share files" demo
- Adding ipfs.types and ipfs.util to window.ipfs via ipfs-postmsg-proxy
- Perf concerns around adding window.ipfs to evey page. Profiling needed. https://github.com/ipfs-shipyard/ipfs-companion/issues/460


### Brave integration

- Switched focus to "nu-Brave" (the internal codename for the chromium based rebuild of Brave.)
- ipfs-companion currently works without modification in nu-Brave.
- Oli to update Brave and seek guidance on bundling go-ipfs deamon with Brave.


### More input needed on arewedistributedyet.com

- Agata has created some rad designs https://github.com/ipfs-shipyard/arewedistributedyet/issues/16
- Oli to arrange a call to get more input on technical discussion


### WebUI redsign

- We had first iteration on WebUI Wireframes for start/status page. https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/33#issuecomment-380017873
- Next iteration on start/status and first draft of the files page this week.
- Demo apps are proving out functionality that will be needed for the new WebUI, once designs are ready.
- Oli to arrange a call with jonkrone about overlap with peerbox, webui, companion and all the things. https://github.com/ipfs-shipyard/peer-star/issues/1 and https://github.com/ipfs-shipyard/pm-ipfs-gui/issues?q=is%3Aissue+is%3Aopen+label%3A%22existing+feature%22
- Tech choices to be finalised for nest weeks catchup https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/51
- Discussion of a name change for WebUI is on hold until we've got designed and built.
- Need to find out if using aegir is a requirement, and if so, find a champion to make it happen.


### Other business

- Q2 OKRs re-worked after feedback https://docs.google.com/spreadsheets/d/1xIhKROxFlsY9M9on37D5rkbSsm4YtjRQvG2unHScApA/edit#gid=755202447
- Hello jonkrone o/
