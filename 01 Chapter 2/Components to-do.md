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
2. ~~Insert original media - drip-feed~~
3. Semi-manual verification system - introduce users to #Starnet 
4. Convert anomaly data and `anomalies` types, settings
5. Sectors for #Planets ?
6. Factions/player pathways [[Narrative ]]
# Components-per-mission
### Bio classifications
1. Seeding will contain a list of available biological entities, a "selected" entity and a method to "add it to your ship" (to transport to the "next chapter"). However, since this is an "end-chapter" mission, I'm going to ignore it for now
2. Any specialised components for making the classifications (e.g. drawing on images) - waiting for product review on [[21-24 September 2024]]to go over the classifications we want to observe

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
# Components removed from Chapter 1 (02)
This page houses a list of every component that we've built that isn't in #Earth #Chapter-1 (either it's been removed or isn't visible/accessible). Some of these components should be added back in #Chapter-2 .
## Classifications
> create a note in the relevant dir that will contain a pointer to the more advanced/specific data input e.g. “bands” in sunspot project

*SSC* board -> it's just varying levels of multiple choice, but eventually we'll be able to have some sort of "drawing-on" feature as part of classifications.

We'll need to add a "Field Guide" to show example images for the multi-choice answers


# Tickets to revisit
#Chapter-1 #Chapter-2 #Tickets #Retrospective #Star-Sailors #Automatons 
## Roovers/Generating

2. `SGV2-186`: [[Planet Generator]]should be based on number of classification types, not number of classifications
	1. Additionally, landscape images with depth/maps should be generated

## Greenhouse
1. [SGV2-146](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-146) 
	> We’ve got some new ideas around gamification, exclusives/creation content so I’m going to move this out of the current epic/sprint, but we’ll bring it back once the “garden” module is in active development.  
		More details soon
	
	> For the most part, we’ve got ClassificationOutput creating rewards/additional entries based on the classificationProps so I think this has been achieved.


### Crafting/Items
[[Crafting]] [[Basic recipes]]
1. [SGV2-190](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-190)
2. [SGV2-161](https://signalk.atlassian.net/browse/SGV2-161)  -> [g](https://signalk.atlassian.net/browse/SGV2-161)

![[IMG_20240910_203254407.jpg]]

![[IMG_20240910_202942306.jpg]]


## Classifications
1. [SGV2-195](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-195) -> `classificationtype` should start with e.g. `zoodex-burrowingOwl` or `zoodex-rainbowLorikeet`...it should start with `zoodex-`