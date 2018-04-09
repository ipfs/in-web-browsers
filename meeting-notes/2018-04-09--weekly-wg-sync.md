# In Web Browsers and GUIs: Weekly IRC Sync (2018-04-09)

- **Lead:** @lidel
- **Notetaker:** @lidel
- **Attendees:**
  - @lidel
  - @alanshaw
  - @hacdias
  - @agata_krych
 

## Agenda

- Ask everyone to put their name into the list of attendees
- Round of updates
  - What have you accomplished since the last Weekly?
  - Were there any blockers? If so, which ones? Is it still blocked? Why?
  - What is the next important thing you should focus on?
- Ask for general questions. Could be things like:
  - I'm stuck with something, I don't know who to ask. Who knows who to ask?
  - Who can help me with xyz?
- Brave call update please!
- Plan this week
- Review remaining issues if there is time left


## Notes

### IPFS Companion v.2.2.0
- [Release  Notes](https://github.com/ipfs-shipyard/ipfs-companion/releases/tag/v2.2.0)
    - blog post later this week

### "the gallery thingy like experiments.google.com"

- Continue discussion in https://github.com/ipfs/awesome-ipfs/issues/126
    - if we add tags to awesome-ipfs  somehow, that will make things super easy to share (eg. share demos that use window.ipfs, share)

### Brave Call Notes

Brave is moving away from Muon (electron fork) and will use Chromium fork instead:
- https://brave.com/development-plans-for-upcoming-release/

We (@olizilla, @diasdavid and @lidel) had a call with Brave team last week to figure out where we stand and what will be the future of IPFS in "new Brave".

IPFS call summary created by Brave team:
> - [IPFS team] have been working on a Muon based approach, but it sounds like have been blocked on some things.
> - The IPFS guys are willing to spend more time on integration within Brave especially if we can improve responsiveness.
> - It sounds like we should re-use the web-extension based ipfs-companion extension: https://chrome.google.com/webstore/detail/ipfs-companion/nibjojkomfdiaoajekhjakgkdhaomnch and https://github.com/ipfs-shipyard/ipfs-companion
> - [IPFS team] is interested in leveraging Chrome App APIs (and possibly custom ones Brave would create) to give them the functionality they need to innovate for what a P2P browser would be.
> - Oli will work on getting a brave-core build up and working.
> - The ipfs-companion extension needs a separately installed locally running IPFS daemon from what I understand. We could do like Tor does to bundle the daemon with Brave.
> - We might introduce a bi-weekly call once work starts heating up, first step get them running on a chromium-fork build.

**tl;dr** It is a mixed bag, but in the long run we may end up with more powerful apis, such as [socket API](https://developer.chrome.com/apps/socket). We may need to adjust our OKRs for Q2 to account for these new Brave efforts.

### GUI Design 

- Agatha is finishing wireframes for start page, nothing to link yet, expect an update soon. 
    - We will try Invision for comments this time (may be more friendly than Zeplin)
- Next step will be File Browser
    - Design: Add files to IPFS https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/35
    - Design: File Browser https://github.com/ipfs-shipyard/pm-ipfs-gui/issues/9
