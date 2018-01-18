# 2018-01-09: IPFS in Web Browsers Q1 Planning/Brainstorming (II)


## Attendees

- Matt Zumwalt
- Alan Shaw
- @olizilla
- David Dias
- @lidel

## Agenda

- **Review OKR**
	- Discussed `OKR.md` draft, fleshed out some action items:
		- reword _"Embedded js-ipfs runs in Brave without installing external daemon"_ to something like _"Identify and document missing pieces to run a reliable embedded js-ipfs in Brave (without installing external daemon)"_
		- reword _"Improved initial experience for non-technical users of mainstream browsers"_
			- focus KRs on Fleshing out user stories/journeys and create UX/style guides
		- fold "Brave  one" into a KR under "Structure documentation and discussion around the primary Browser vendor concerns"
    - Everyone will do one more iteration in a single PR
    - ... then move OKRs to Google Spreadsheet and add assignments and priorities
- PSA: Started GUI/UX initiative at https://github.com/ipfs-shipyard/pm-ipfs-gui
	- PSA: Started work on UX/Style Guide: https://github.com/ipfs-shipyard/ipfs-ui-style-guide
-  Briefly introduce a Person of Interest to new team members :-)
	- @gozala is a valuable point of contact/discussions for dweb integration with browsers (Beaker etc)
- Spring cleaning in progress
- Identified need for coherent documentation of addressing on the dweb
  - current state of addressing spec: https://github.com/ipfs/specs/tree/addressing/dweb-addressing
- `arewedistributedyet.com` kick-off
  - Tracked in [existing epic @ ipfs/in-web-browsers](https://github.com/ipfs/in-web-browsers/issues/24#issuecomment-355942618)
  - Registered Domain Name: AREWEDISTRIBUTEDYET.COM

## Appendix

### Q:
- where is the line between functionality that’s only available in node vs func that’s available in browsers?

### A:
- Anything that's in IPFS-core spec should be available in browsers and in node (Everywhere)
- tl;dr anything that interfaces with the OS is tricky or different in browsers. mostly: libp2p transport and discovery, and ipfs datastore (and also different between language runtimes, js/go/rust, depending on the availability and quality of libraries)
- IPFS should be figuring out how to talk to other nodes, but in some cases this doesn't work within the browser. We are working to address those cases.

