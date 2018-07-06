# GUI & In Web Browsers Weekly IRC Sync 2018-06-25

- **Lead:** @lidel
  - **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @agatakrych
  - @alanshaw
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

- Diogo Silva joins In Web Browsers WG in Q3 \o/ 
- Let's start thinking about OKRs for Q3 
- Should WebUI Revamp PRs come with  translations?
- Should we ship ON/OFF toggle asap?

## Notes

_Extracted from the meetings irc logs in #in-web-browsers_

### Updates

- @lidel
    - went over action items from last week, namely WebUI reviews (settings, dialogs etc)
    - investigated bugs: beta channel updates in Firefox and Linkify issues on Slack/Twitter
    - protoyped ways we could implement backend selector, but no PR yet
    - invited Diogo to join in web browsers WG next quarter and provided him with an initial overview today
    - Next: fix linkify, back to PR with backend selector, get back to libdweb, assist Diogo if any questions

- @alanshaw
    - working on status page
        - porting bandwidth list from old PoC
        - solving performance issues
    - reviewing webui PRs

- @olizilla
    - busy with refactor and test the Filecoin Explorer
    - settings page for the WebUI
    - Next: loading states and visualising what's going on in ipfs when you start IPLD exploring unreachable CIDs

- @hacdias
    - finishing exams season \o/
    - Next: finish the opened PRs and apply the components to the WebUI, fix some issues on the file browser

- @agata
    - busy with Berlin Dev Week stuff
    - Next: get back to status page when free

### Other

- React components are developed inside of `revamp` branch of WebUI for now
    - When mature, we will extract them into a reusable library
- Should WebUI Revamp PRs come with  translations?
    - Yes, its on the radar (currently opened PRs will not be enforced)
- Should we ship ON/OFF toggle asap?
    - Yes (there is a small rendering issue on Mac, will look into it)

### Action Items

- @all
    - review WebUI PRs:
        -   status page
        -   settings page  (second iteration)
    - think about what to focus on in Q3 and how to communitate it using OKRs
