Stages of IPFS Support in Browsers
======

> How web bowsers can progressively add support for IPFS, and which use cases will be enabled by each stage.

There is a [working copy of this document in hackmd](https://hackmd.io/JwQwjATAHApgJgdgLQDZgGN1ICwoGYhIBGYYAzEmdnDAAxRS1hQplA==?both)

# Overview & Terms

## Terms

Decentralized Web client states:
* Read
    * From DHT
    * From local store
* Write
* Announce hashes
* Publish (IPNS names)
* Distribute/Provide blocks to peers

A sketch:

<a href="files/napkin_sketches/napkin%20distributed%20web%20client%20states.JPG">
  <img alt="decentralized web client states" src="files/napkin_sketches/napkin%20distributed%20web%20client%20states.JPG" width="500px">
</a>

# Are we Decentralized Yet?

> How this effort fits into the overall upgrade path for decentralizing the internet.

# The Stages of Browsers Supporting IPFS

Stages of Integration/Support/Adoption broken down according to functionality & Use Cases
* When in this timeline will browser nodes actually act like p2p nodes (distributed scalability...)


* Stage -1: WebRTC connections in Browsers
* Stage 0: p2p stack + multiformats
* Stage 1: Moving Data (Read-Only) via Protocol Handler
* Stage 2

A Sketch:

<a href="files/napkin_sketches/napkin%20stages of%20support%20in%20browsers.JPG">
  <img alt="decentralized web client states" src="files/napkin_sketches/napkin%20stages of%20support%20in%20browsers.JPG" width="500px">
</a>


## Stage -1: Browsers support WebRTC


## Stage 0: Peer to Peer stack + multiformats

### Functionality

* Peer Management in the Browser
    * Connecting to DHT
    * Peer Discovery

### Use Cases
Adding this functionality enables browsers to support use cases like:
* TODO

### Libraries Involved
Needed libraries: TODO


## Stage 1: Moving Data (Read-Only) via Protocol Handler

### Functionality
At this stage, we add support for:
* Protocol Handler
    * Resolve IPFS links in address bar
    * Resolve IPFS links within HTML (or within other rendered browser content)
* Dereferencing
    * DHT lookup
* Retrieval
    * Retrieval from Peers
    * Retrieval from local data store
    * Write retrieved content to Local Storage (use browser's native filestorage)
        * what user downloaded

### Use Cases
Adding this functionality enables browsers to support use cases like:
* TODO

### Libraries Involved
Needed libraries: IPLD, Multiformats, CID

## Future Stages

_TODO: Decide how to arrange this as actual, ordered stages._

Functionality to cover in Future Stages
* **Announce & Distribute/Provide:** IPFS node in browser provides content that it's holding
    * Use cases:
        * browser nodes act as an auto-scaling p2p network
* **Add:** Add content to IPFS through browser
* **Publish** IPNS updates

# Backlog of Use Cases

* Serverless hires images & 3D content: IIIF image tiles served from IPFS & resolved using ipfs/dweb uris
* Serverless annotations: IIIF annotations written to IPFS and held by the network
* browsers act as peer-providers on the network (auto-scaling CDN)
* treat local ipfs repository/repositories as a cache
* bookmark and snapshot


# Problems to Solve

<a href="files/napkin_sketches/napkin%20browser support%20relevant%20problems.JPG">
  <img alt="decentralized web client states" src="files/napkin_sketches/napkin%20browser support%20relevant%20problems.JPG" width="500px">
</a>

## Things IPFS Needs to Address

### js-ipfs + libp2p
- Load js-ipfs
- js-ipfs is slow
- webRTC is slow
- every page has separate instance of IPFS
    - separate repository
    - separate peers

### Protocol Handler
- can't resolve IPFS uris in address bar
- can't resolve IPFS uris in HTML
- can't dereference hashes


## Things Browsers Need to Address

### Network
- nothing beyond WRTC
- Difficult finding peers
- ad-hoc stack: each app needs its own peer discovery & other things

# Major Factors to Consider

* Single-origin Policy
* Browser Limitations
    * limited connection ... network is only wrtc
    * limited storage
* Caching
* Storing retrieved content in browser filestore
* Redistributing content through browser node
* Redistributing content in background

Something to consider:
IPFS-CORS
- would this ever be anything other than `ALLOW *`?


IPNS-CORS
- an IPNS entry can assert which IPNS publishers to trust
