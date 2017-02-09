Roadmap: IPFS In Web Browsers
======

_**THIS IS A WORK IN PROGRESS** We are actively working on this Roadmap. It is subject to major changes durring the current 2-week sprint. See [ipfs/in-web-browsers#23](https://github.com/ipfs/in-web-browsers/issues/23) to track the work or comment on it._

**What we want:** Protocol handlers for decentralized web protocols, especially IPFS and IPLD, bundled natively in web browsers.

**What we need to provide to browser manufacturers:** something that demonstrates why these protocols are valuable to their users. We have to show why distributed, decentralized protocols and technologies are valuable and we need to show specifically why IPFS is valuable.

## The Path to Native Browser Support

* **Step 1.** *DONE* Implement js-ipfs  
* **Step 2.** *IN PROGRESS* Make js-ipfs and go-ipfs interoperate seamlessly (see https://github.com/ipfs/pm/issues/310, https://github.com/ipfs/pm/issues/343, https://github.com/ipfs/pm/issues/358)
* **Step 3.** *[IN PROGRESS](https://github.com/ipfs/pm/issues/351)* Define the APIs, address schemes, security models, etc.
* **Step 4.** *[IN PROGRESS](https://github.com/ipfs/pm/issues/351)* Create browsers add-ons and/or extensions that handle dweb protocols
* **Step 5.** *NEXT STEP* Make the case for IPFS & Decentralized Web Protocols in Web Browsers with Use Cases, Sample Applications, Demos and [Delightful Documentation](https://github.com/ipfs/pm/issues/357)
* **Step 6.** Native support in the Browsers: Protocol Handlers incorporated into the browsers by default

## Making the Case for Browsers to Support These Protocols

We have to show both the short-term value propositions for browser users and the long-term value propositions.

The short-term propositions show how distributed & decentralized tech will _incrementally improve existing browser use cases in a number of ways_.

The long-term value propositions show _completely new possibilities for what browsers could do in the future_. The decentralized web is going to develop either way. We want that evolution to involve existing web browsers. However, if the web browsers don't step up to meet this challenge decentralized apps will evolve on a new generation of platforms, without the benefit of the browser manufacturers experience maintaining a healthy, open, standards-based web.

One example of long-term value proposition is Virtual Reality. As we barrel towards a world where the metaverse is a real thing, browser manufacturers could play a major role in ensuring that the metaverse evolves as an open web rather than a closed one. Currently nobody thinks of web browsers as the main way you interface with VR worlds; those use cases are not central on the list of "browser users" use cases. However, there is a huge opportunity here if browser manufacturers start using decentralized protocols to handle VR data.

Things that create new possibilities in browsers
* disconnected operation & offline (ie. local chat, share files without access to backbone, easy way to load simple applications and work with the person next to you)
* when you're in an environment, being able to see (network-local) nodes around you and applications you can run with them -- ie. airdop, chat, collaborative doc editing
    * modifier: geographically local vs. shared affiliation
        * treating all data as social data and all interactions between nodes as social activity
    * iiif annotations
    * Jeromy's p2p large file sharer

COUNTERPOINT TO: "your machine is a portal to the cloud." Instead, emphasize visibility of what's around you and who's around you -- geographically and metaphorically.
