# GUI & In Web Browsers Weekly IRC Sync 2018-05-21

- **Lead:** @lidel
- **Notetaker:** @alanshaw
- **Attendees:**
  - @lidel
  - @alanshaw
  - @kyledrake
  - @hacdias
  - @olizilla
  - @gozala

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

- Update from convo with gozala
- Brave news

## Notes

* IPFS Companion news
    * New beta of Companion that preserves file names and supports sharing of multiple files
        * https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.2.2.9320
    * Bugs investigation related to uploads via Companion in firefox and chrome (out of memory, playing with streaming to mitigate that, and looking at ways we can provide visual feedback)
* WebUI news
    * Progress on new IPLD explorer page
        * ![IPLD explorer page](https://usercontent.irccloud-cdn.com/file/TsppHg9u/Screenshot%202018-05-21%2016.04.47.png)
    * UI components being built out using React Storybook
        * Files components: https://github.com/ipfs-shipyard/ipfs-webui/pull/658#issuecomment-390351489
* Firefox news
    * Gozala is working on Firefox experiment (think prototype of actual WebExtension API) that will provide 'native' ipfs:// protocol handler
        * https://github.com/Gozala/libdweb/
    * @olizilla, @lidel and @gozala discussed priorities and challenges related to industry-wide conventions around origins and URIs:
        * Aiming for ipfs:// as it does not go against origin conventions already present in browser vendors, and specifically to Firefox, does not require changes to sensitive parts of browser
        * The dweb: may remain a redirect to ipfs:// for some time
        * If we have case-insensitive CIDv1, then we can use it as-is in ipfs://<cid>
* Brave news
    * Bringing forwards the release date for the chromium based version
    * **Canceled** bundling go-ipfs with muon version
    * Want to bundle IPFS Companion with chromium based version


## Action Items:

* Gozala/libdweb
    * Feedback on issues in https://github.com/Gozala/libdweb/
    * Push for a useful default CID encoding for use as the host part of urls so we can integrate with browsers in this decade - https://github.com/ipfs/go-ipfs/issues/4143
* It's h4ck week in Lisbon this week, aims:
    * Companion upload improvements shipped to stable
    * window.ipfs security perimeter and its UX defined
    * Decision on details of creating WG/Teams
* Brave
    * Feedback to Brave team on other APIs or tweaks we might want to make a more seamless experience (for IPFS Companion bundled), that are less work than `registerProtocolHandler`
