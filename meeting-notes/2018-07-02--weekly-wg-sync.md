# GUI & In Web Browsers Weekly IRC Sync 2018-07-02

- **Lead:** @olizilla 
- **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @olizilla
  - @fsdiogo
  - @hacdias

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

- Bootstrap discussion about Q3 OKRs: https://github.com/ipfs/in-web-browsers/issues/85
  - Do we plan together & split after?
  - Hackpad with draft ideas fro Q3 2018 OKRs: <del>https://hackmd.io/63Ot04yETI6_Lmpa8sjw5A?view</del> (moved to [IPFS 2018 Q3 OKRs](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/edit?usp=sharing))
- Berlin Dev Sessions
- DWEB 2018 
- Set agenda before lunch on Mondays so we have time to think about them and ask better questions
    - Should we do it via new issue each week?

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Updates
- @fsdiogo
    - catching up with Companion and WebUI, onboarding, thinking about KRs
    - **Next:** grab something bigger to work on

- @lidel 
    - Fixed Linkify experiment to work with  Slack and Twitter, made it more robust by rate limiting and fixing race-conditions in dynamic JS apps that mutate DOM: https://github.com/ipfs-shipyard/ipfs-companion/pull/504
    - Created a workaround for Companion's uploads being broken due to 'invalid Read on closed Body' bug in HTTP API (go-ipfs): https://github.com/ipfs-shipyard/ipfs-companion/pull/509 more info about actual bug in go-ipfs can be found at https://github.com/ipfs/go-ipfs/issues/5168 (for now we only fix uploads done via browser action in browser extension, but it is possible to fix it globally for all websites using js-ipfs-api – should we?)
    - Added a way to opt-out from gateway redirect for a single request via URL hint:  https://github.com/ipfs-shipyard/ipfs-companion/pull/505
    - Released above to Beta: https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.4.0.10120
    - Researched WebRTC issues we had in past, as Mozilla asked us to provide some examples that make browser unstable. More on this next week.
    - **Next:** Work on Q3 OKRs, Prepare for Berlin, libdweb is time allows

- @hacdias
    - work on WebUI's File Browser and reviews
        - selecting and downloading multiple files
        - pretty prompts for deleting and renaming
    - **Next:** upload files, folders & by IPFS Path, maybe drag&drop

- @olizilla
    - "make the GUI team" a thing: https://github.com/ipfs/ipfs-gui
    - slide deck with feedback how we're doing on the GUIs: https://ipfs.io/ipfs/QmUjfm9heNhB4qZ2fDj35Q7CiycfFMxigP3hnWWXWiKouV/
    - solving remaining issues with WebUI's Settings Page
        - feedback welcome on: https://github.com/ipfs-shipyard/ipfs-webui/pull/690
    - IPLD start page: https://github.com/ipfs-shipyard/ipfs-webui/pull/690
    - debugging of windows CI test fails or js-ipfs
    - **Next:** getting Settings and IPLD Pages merged, IPLD Explore improvements (dealing with large buffers)

- In Other News
    - Agata is busy with other PL work, won't be able to help GUI team in Q3
        - Looking for way to adapt to this change (hiring etc)

### Action Items
- @all feedback welcome on:
    - https://github.com/ipfs-shipyard/ipfs-webui/pull/690
- @all **think about (O)KR ideas for Q3 and add them to hackpad**
    - <del>https://hackmd.io/63Ot04yETI6_Lmpa8sjw5A?view</del> (moved to [IPFS 2018 Q3 OKRs](https://docs.google.com/spreadsheets/d/19vjigg4locq4fO6JXyobS2yTx-k-fSzlFM5ngZDPDbQ/edit?usp=sharing))
    - We will have call later this week to go over proposed ideas and refine them into OKR draft
