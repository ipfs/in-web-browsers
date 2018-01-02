# IPFS in Web Browsers Q1 Planning/Brainstorming 

## Attendees

- @diasdavid
- @olizilla
- @lidel
- @dmitriy
- @kyledrake
- @flyingzumwalt

# Agenda
- Overview
- Forming the working group
	- What is the purpose of the WG
- Checking in with the context
- Setting OKRs

## Notes

First official meeting of the not yet official IPFS in Web Browsers working group.

### Forming the Working Group

**[Current Working Groups Proposal](https://github.com/ipfs/ipfs/blob/8dc70f4d9676b181734c7818908f422af8fb47f5/WORKING_GROUPS.md#integration-with-web-browsers)**

What is the purpose of the WG? What does the IPFS world think a WG is?

We want it to be clear what the community should expect from a WG.

Some things we're leaving loose or undefined for now:
- does the WG control a repo?
- where is their work tracked?
- Is there a procedure for discussions, decisions, etc?

Some desirable characteristics for WGs
- If you have KRs for the WG it should be hard to pull you off that.
- It should be welcoming/inviting for people to join and participate
- (as specified in the proposal) there should be a captain and a co-captain 


### Context (checking in, getting synced)

- lidel's proposed OKRs: https://github.com/ipfs/in-web-browsers/pull/62
  - these are only for browser extension
  - a starting point for further discussion

Lots of ideas and conversations already floating around
- kyle's thoughts about UX
- address scheme discussions ... [The four stages of the upgrade path for path addressing](https://github.com/ipfs/specs/pull/152#issuecomment-284628862) ... 

Use Cases
- persistence layer for a dapp developers (Open Bazaar use case)
- IPFS as filesystem ... nice distributed filesystem
- IPFS for serving/publishing web pages
- IPFS the distributed web ... getting 2 billion to use something that works better than HTTP


### Setting OKRs

**TASK**: Extract the document that defines the ultimate dream for IPFS in web browsers and expresses what to do in the next 3 months
- this mainly involves gathering all the info that's floating around out there, putting it in one clear document

Proposal: revisit kyle's "screed" proposal, update that and use it as the defining UX vision.
- the only part that people have disagreed with is the idea of creating our own browser
- if we don't build our own browser we will need to set someone up as our lobbyist connecting with the browser manufacturers 

#### Possible KRs

- Understand what is the ideal UX and agree on it (multiple iterations)
- create a browser demo that shows the browser manufacturers how it _should_ work (some misgivings about whether this is the right way to spend effort)
	- cost-effective alternative: [Create WebExtensions Experiments to Prototype Missing APIs](https://github.com/ipfs-shipyard/ipfs-companion/issues/343)    
      ([WebExtension Experiment](https://webextensions-experiments.readthedocs.io/en/latest/)  + demo use in IPFS Companion)
	- expensive alternative: fork firefox as a demo -- this is how Tor Browser works, and how they propose features within the firefox team 
- create a "Call to Arms" that tells and shows why this is important and how it should work
- Establish a style guide for IPFS apps in the browser
- spring cleaning -- clean up the in-web-browsers repo. update issues, update docs, etc.
	- make the web-browsers repo into a reliable reference point for anyone interested in this effort 
  
Straw Poll of Group's Priorities
- Making IPFS look & work well
	- are we distributed yet?

# Action Items 
- submit PRs with OKR proposals ([OKR.md](https://github.com/ipfs/in-web-browsers/blob/master/OKR.md))
  - everyone declare what they want to work on (pitch your own goal)
- create a channel in irc 
- meet again in 10 days (around 8-10 January)
- spring-cleaning https://github.com/ipfs/in-web-browsers/issues


