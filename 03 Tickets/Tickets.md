---
sticker: lucide//folder-tree
tags:
  - Tickets
  - Tasks
  - Sprints
---
# Urgent/Ready-to-go
1. Integrate `inventory.configuration` for structures in the early game
2. [[#^d3cf10|]]

# Onboarding [[Structure per chapter|Structure per chapter]]
See [[01 Chapter 1|01 Chapter 1]]
## bugs
1. Scrolling issues [[Bug Report|Bug Report]]
	1. Telescope classification
	2. Roover images

## content/styling
[[Bug Report|Bug Report]]
1. Icons for sidebar
2. Graphic/splash
3. Change ratio for panel widths
4. Containerise roover photo properly
5. New theme
6. Implement new rover deploy photo + style/layout
7. Header menu - profile image [[Header & Navigation|Header & Navigation]]
8. After the classification is posted for the Rover Photos mission, THEN show the mineral deposits (and perhaps some explanation for this phase), hide the classification/post form
> (Note) -> I think all of these should just be created as a single child issue of `SGV2-164`

# Chapter 1 [[Overall component list|Overall component list]]
## [[Mining Operations|Mining Operations]]
1. ~~Inventory module~~
2. "Offer" to send users directly to the refinery/somewhere else after mining finishes, also allow them to select (in state) a "goal" and have a "semi-automated" pathway built from that

## Mechanics
**[SGV2-161: Crafting pipeline for items](https://signalk.atlassian.net/browse/SGV2-161)**
1. Each item has a crafting recipe [[Crafting|Crafting]] [[Basic recipes|Basic recipes]]
2. We’ll create a modal that shows the items you have in your inventory (Inventory modal, see linked/attached image), has 2 slots for you to select 2 items, and then create an output. ^d3cf10
3. Have a maximum number of deposits on each planet
4. Integrate creation of deposits with rover photo creation
5. Create rover action panel (see [[Mining Operations|Mining Operations]]) - partially completed

## Routes & containers
1. Mining route & structure - created. Working on content for the mining structure
2. Automaton structure - initialised, working on content
3. Refinery/construction route & structure - need to initialise

## Visuals
**[New planet view](https://signalk.atlassian.net/browse/SGV2-158)**
1. Find appropriate background images - ticket for Fred [[Mining Operations|Mining Operations]]
2. Fix image loading times - APPEEARS API
3. Configure the appropriate structures to go into each section
4. ~~Sections can be opened~~
5. For now, structures/sections will open up the external sections (e.g. [![](https://signalk.atlassian.net/rest/api/2/universal_avatar/view/type/issuetype/avatar/10318)SGV2-65: Mission 2.2: Mining stationDone](https://signalk.atlassian.net/browse/SGV2-65) [![](https://signalk.atlassian.net/rest/api/2/universal_avatar/view/type/issuetype/avatar/10318)SGV2-168: Automaton configurator for early mining mechanicsDone](https://signalk.atlassian.net/browse/SGV2-168) mining route), but in prod we’d have everything filter into the section rather than loading in a separate page.

## Missions
[[Mission list|Mission list]]
1. Clicking on a mission should open up a relevant component/route

### Starter [classification] missions
1. "Classification" selector should be part of the big modal

## Tickets to create
1. [[#^611492|]] -> it would be good to think about this ticket (SGV2-129) just from the perspective of the "arrows"/tooltips for the OOO messaging to the end-user

## Content/Missions
1. [[Galaxy map|Galaxy map]] -> maybe a dynamic list that fans out based on the direction and magnitude of distance? User can filter by "have visited", etc
2. Get the animal/zoodex classification to pull in classification options based on mission, integrate creation of posts mentioning the storage key [[02 Citizen Modules|02 Citizen Modules]] [[Data Sources|Data Sources]]  #zoodex 

## Classifications/anomalies
#Anomalies 
[[02 Citizen Modules/Classifications/Classifications|Classifications]]
1. [Posts about an anomaly](https://www.zooniverse.org/projects/andreavarela89/iguanas-from-above/talk/3389/3429906) 
2. Multiple classification / `PostFormMultiple.tsx`

# Generator/Visuals
[[Bug Report|Bug Report]]
1. Increase pixel count for the "low-rest" exports

# Chapter 2
## Tutorials/Onboarding
1. [SGV2-129](https://signalk.atlassian.net/browse/SGV2-129) - Tooltip & tutorial info, showing list of everything that's available to the users ^611492 (This is essentially the [[Mission list|Mission list]] /mission log)

## Mining mechanics
1. We'll introduce the user to attachments/toolchains for their rovers, rather than just upgrading "power" or "speed" they'll attach special tools (like "diamond cutters")
2. Mining stations will be implemented

# Structure tickets
[[05 Game Items/Structures/Structures|Structures]]
1. Create a component that allows you to choose which automaton you're configuring/upgrading
2. Actually implement the dynamic properties (e.g. "Uses") to be updated from functions in the frontend
# Creativity/Garden mechanics
## Rewards, Content, Items
* [Rewards formula & pipeline](https://signalk.atlassian.net/browse/SGV2-146)

# Old content
1. [Messaging | SGV2-128](https://signalk.atlassian.net/browse/SGV2-128)