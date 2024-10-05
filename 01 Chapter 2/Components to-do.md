---
sticker: lucide//layout-grid
tags:
  - Chapters
  - Chapter-1
  - Chapter-2
  - Tickets
  - Components
  - Content
---
Related:
[[01 Chapter 2/Tickets to revisit]]
1. Update the #Orbital structure display to take in the profile picture of the planet and any satellites as props
	1. Need to come up with some new profile pictures...
2. Insert original media - drip-feed
3. Semi-manual verification system - introduce users to #Starnet 
4. Convert anomaly data and `anomalies` types, settings
5. Sectors for #Planets ?
6. Factions/player pathways [[Narrative ]]

### Profile Form
`SGV2-143`
Maybe we have the #Profile #Form as part of the "requirement" to make your first classification, so we just drop the user on the planet with #CaptnCosmos guiding them? [[Questions for testers]]1. Starnet comes in to solve this - SGV2-143 comes in as the entry point for this

# Components-per-mission
## Classification missions
1. Revised structure modal
2. Feed to show discoveries
3. Grab data
4. Post Form - will likely need to be revised to be more responsive and have the secondary options in the multiple choice configuration

### Bio classifications
1. Seeding will contain a list of available biological entities, a "selected" entity and a method to "add it to your ship" (to transport to the "next chapter"). However, since this is an "end-chapter" mission, I'm going to ignore it for now
2. Any specialised components for making the classifications (e.g. drawing on images) - waiting for product review on [[21-24 September 2024]]to go over the classifications we want to observe

## Structure missions
1. ~~Buttons to upgrade, repair and otherwise administrate structure~~
2. ~~Research new data (for classification structures)~~

### Researching
1. ~~Show all available (unlocked and locked) research items, with the capacity to unlock these items (functional, but need to update the table structure and conduct a design review)~~

## Mining - (possibly)
(for mining from the "traditional" mineral deposit mechanic)
1. Show deposits
2. "inner deposit" (upon selecting a deposit)
3. Automaton select
4. Mining UI
All of these components have been completed AND are functional, but we just need to do a design review for what can change here

I think that these are the main components that are relevant, my question is is this enough from a narrative perspective?
We just need to move everything to Earth and come up with an order for initialising each component (not necessarily a narrative order, just something we can go off while building/testing)

Also, when does the #Surveyor come into this?

## Future
Anything to do with other #Planets can be ignored for now, e.g. terrain generation or terraforming
1. Terrain generation/landscaping (unless terrain understanding is of any relevance to #Earth ?)
## Automatons
1. Create a component that allows you to choose which automaton you're configuring/upgrading
2. Actually implement the dynamic properties (e.g. "Uses") to be updated from functions in the frontend

## Mining
1. We'll introduce the user to attachments/toolchains for their rovers, rather than just upgrading "power" or "speed" they'll attach special tools (like "diamond cutters")
2. Mining stations will be implemented

## Crafting
1. Refinery

## Classifications
New modules:
1. #zoodex uploader

## Planets
1. [[Galaxy map]]