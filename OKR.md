# IPFS in Web Browsers: <br>Objectives and Key Results for Q1 2018

This is a markdown version of [relevant sheet in IPFS + libp2p 2018 Q1 OKRs](https://docs.google.com/spreadsheets/d/1clB-W489rJpbOEs2Q7Q2Jf1WMXHQxXgccBcUJS9QTiI/edit#gid=1872064387).    
Is is provided here as-is, see original document for priorities, assignments and progress.


## We have a shared understanding of **how IPFS _should work_ in web browsers**

_Focus on people. What are the user journeys; what are their goals. How will IPFS improve a web users day?_

### Key results

- Document user journeys that capture an ideal UX for using IPFS in daily web browsing
- Create IPFS Brand Book/Style Guide/UI Kit + logos for Desktop and Companion
- Publish a ui-style-guide repo to define the design language of IPFS apps
- Create the reference document for what user goals are when using IPFS as part of their daily web browsing, publish as a blog post
- Provide a step-by-step guide for developers to create apps that use `window.ipfs`


## Browser developers understand the **requirements of the decentralized web**

_Support the conversation with browser vendors. Make it as easy as possible for them to see where we are at, what's needed and why._

### Key results

- Get people involved in a communication channel (ie. email list and a regular phone call) for devs at browser groups to participate in discussion around IPFS support & integration
- Create a final draft spec for [Addressing on the Decentralized Web](https://github.com/ipfs/specs/tree/master/dweb-addressing)
- Collate the list of apis needed, what each would allow, and a list of p2p projects that want it (publish as a blog post "IPFS in Web Browsers: The Missing Pieces"?)
- Publish the list under arewedistributedyet.com as a communal call to action, with tests where possible ([in-web-browsers/#24](https://github.com/ipfs/in-web-browsers/issues/24))


## Move towards IPFS **working seamlessly in browsers**

_Improve UX of existing features. Make it easy to start playing with IPFS in the browser today._

### Key results

- Companion exposes IPFS API as `window.ipfs` on every page ([in-web-browsers/#42](https://github.com/ipfs/in-web-browsers/issues/42), [ipfs-compaion/#330](https://github.com/ipfs-shipyard/ipfs-companion/issues/330))
- Companion is able to upload data to IPFS without external daemon (fallback to js-ipfs)
- Implement or solve 5 issues marked with "ux" label
- Brave can add & get all file types from IPFS via native protocol addresses without redirect ([ipfs-companion/#312](https://github.com/ipfs/ipfs-companion/issues/312))
- Add test coverage reporting and achieve 80% coverage
- Publish welcoming, up-to-date documentation for Companion
- Companion UI follows the (draft of) IPFS Style Guide
- Switch to Jenkins-based CI process for Companion


## Provide a nice **desktop experience for casual users** of IPFS

_Improve installation experience. Make it easy to control IPFS node on the desktop without commandline._

### Key results

- Publish signed releases of Desktop
- Add test coverage reporting and achieve 80% coverage
- Publish welcoming, up-to-date documentation for Desktop
- Implement or solve 5 issues marked with "ux" label

