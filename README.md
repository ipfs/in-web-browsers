# IPFS In Web Browsers Working Group

> Tracking the Path to getting IPFS and other Decentralized Protocols Natively Supported in Web Browsers.

## Current Status

[![Waffle.io - Columns and their card count](https://badge.waffle.io/ipfs/in-web-browsers.svg?columns=all)](https://waffle.io/ipfs/in-web-browsers)

Currently in order to run IPFS in a web browser, you have to either bundle js-ipfs with your client-side application or your users have to run a go-ipfs daemon on their local machines. This means we've completed the first step on [The Path to Native Browser Support](#Roadmap).

You can now install the IPFS Companion, a Web Extension that works in Chrome, Firefox and Brave to give your browser super powers, I mean, to add support for the IPFS protocol.

**Watch @lidel give a quick update on the IPFS Companion at the IPFS All Hands Dec 12:**

[![](https://ipfs.io/ipfs/QmPan1yLc3AM5MzhJzL7wByrrmsGx8gz276Xn28VLrcSyQ)](https://www.youtube.com/watch?time_continue=1094&v=xCMNgBzn5WI).

## PM'ing

- [Sprint 13-24 February](https://github.com/ipfs/pm/issues/351) is aimed at tackling a number of the next steps.

## Roadmap

> **THIS IS A WORK IN PROGRESS** We are actively working on this Roadmap. It is subject to major changes during the current 2-week sprint. See [ipfs/in-web-browsers#23](https://github.com/ipfs/in-web-browsers/issues/23) to track the work or comment on it.

- What we want: Protocol handlers for decentralized web protocols, especially IPFS and IPLD, bundled natively in web browsers.
- What we need to provide to browser manufacturers: something that demonstrates why these protocols are valuable to their users. We have to show why distributed, decentralized protocols and technologies are valuable and we need to show specifically why IPFS is valuable.

**The Path to Native Browser Support**
- **Step 1.** *DONE* Implement [js-ipfs](https://github.com/ipfs/js-ipfs)
- **Step 2.** *DONE* Make [js-ipfs](https://github.com/ipfs/js-ipfs) and [go-ipfs](https://github.com/ipfs/go-ipfs) interoperate seamlessly (see https://github.com/ipfs/pm/issues/310, https://github.com/ipfs/pm/issues/343, https://github.com/ipfs/pm/issues/358)
- **Step 3.** *[IN PROGRESS](https://github.com/ipfs/in-web-browsers/milestone/1)* Define the APIs, address schemes, security models, etc.
- **Step 4.** *[IN PROGRESS](https://github.com/ipfs/in-web-browsers/milestone/1)* Create browsers add-ons and/or extensions that handle dweb protocols see [Epic: Web Extension supports gateways and core api with both js and go nodes](https://github.com/ipfs/in-web-browsers/issues/39) and the list of [web extension issues](https://github.com/ipfs/in-web-browsers/labels/web%20extension))
- **Step 5.** *NEXT STEP* Make the case for IPFS & Decentralized Web Protocols in Web Browsers with Use Cases, Sample Applications, Demos and Delightful Documentation
- **Step 6.** Native support in the Browsers: Protocol Handlers incorporated into the browsers by default
