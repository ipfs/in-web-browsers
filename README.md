# IPFS In Web Browsers Working Group
[![#ipfs-in-web-browsers](https://img.shields.io/badge/irc-%23ipfs--in--web--browsers-brightgreen.svg)](https://webchat.freenode.net/?channels=ipfs-in-web-browsers)

> Tracking the Path to getting IPFS and other Decentralized Protocols Natively Supported in Web Browsers.

## Current Status

### Browser Extension
You can now install the [IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion#ipfs-companion), a WebExtension that works in Chrome, Firefox and Brave to give your browser super powers,
I mean, to add support for the IPFS protocol and related [features](https://github.com/ipfs-shipyard/ipfs-companion#features).

Latest Beta experimentally exposes IPFS API under [`window.ipfs`](https://github.com/ipfs-shipyard/ipfs-companion/blob/master/docs/window.ipfs.md#notes-on-exposing-ipfs-api-as-windowipfs) on every web page.

### JS Libraries
Currently in order to run IPFS in a web browser, you have to either bundle [`js-ipfs`](https://github.com/ipfs/js-ipfs) (full IPFS node in JS) with your client-side application
or use [`js-ipfs-api`](https://github.com/ipfs/js-ipfs-api) (HTTP API client library) to connect to external daemon running on local or remote machine.

### IPFS Addressing in Web Browsers

See  [this memo](ADDRESSING.md). It specifies current set of conventions for the IPFS community.    
We invite everyone to submit questions and suggestions for improvements via issues/PR.

## PM'ing

 - [![Waffle.io - Columns and their card count](https://badge.waffle.io/ipfs/in-web-browsers.svg?columns=all)](https://waffle.io/ipfs/in-web-browsers)
- [ROADMAP](ROADMAP.md) (with Quarterly Objectives and Key Results)
- [Working Group Meeting Notes](https://github.com/ipfs/in-web-browsers/tree/master/meeting-notes)

## Endeavours

- [IPFS Desktop](https://github.com/ipfs-shipyard/ipfs-desktop) - A Desktop application to run IPFS with a GUI
- [IPFS Companion](https://github.com/ipfs-shipyard/ipfs-companion) - A Web Extension to give your browser super powers.
- [IPFS WebUI](https://github.com/ipfs-shipyard/ipfs-webui) - The IPFS Dashboard
- [IPFS GUI](https://github.com/ipfs-shipyard/pm-ipfs-gui) - Unifying and leveling up IPFS interfaces and the user journey into the Distributed Web
  - [IPFS Styleguide and UI language](https://github.com/ipfs-shipyard/ipfs-ui-style-guide)

