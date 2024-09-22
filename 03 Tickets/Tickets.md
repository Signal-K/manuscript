---
sticker: lucide//folder-tree
tags:
  - Tickets
  - Tasks
  - Sprints
---
# Urgent/Ready-to-go
1. ~~Integrate `inventory.configuration` for structures in the early game -> SGV2-188~~
2. [[#^d3cf10]]

# Onboarding [[Structure per chapter]]
See [[01 Chapter 1]]
## bugs
1. Scrolling issues [[02 Globals/Bug Report]]
	1. Telescope classification
	2. Roover images

## content/styling
[[02 Globals/Bug Report]]
1. Icons for sidebar
2. Graphic/splash
3. Change ratio for panel widths
4. Containerise roover photo properly
5. New theme
6. Implement new rover deploy photo + style/layout
7. Header menu - profile image [[Header & Navigation]]
8. ~~After the classification is posted for the Rover Photos mission, THEN show the mineral deposits (and perhaps some explanation for this phase), hide the classification/post form~~
> (Note) -> I think all of these should just be created as a single child issue of `SGV2-164`

# Chapter 1 [[Overall component list]]
## [[Mining Operations]]
1. ~~Inventory module~~
2. "Offer" to send users directly to the refinery/somewhere else after mining finishes, also allow them to select (in state) a "goal" and have a "semi-automated" pathway built from that

## Mechanics
**[SGV2-161: Crafting pipeline for items](https://signalk.atlassian.net/browse/SGV2-161)**
1. ~~Each item has a crafting recipe [[Crafting]] [[Basic recipes]]~~
2. We’ll create a modal that shows the items you have in your inventory (Inventory modal, see linked/attached image), has 2 slots for you to select 2 items, and then create an output. ^d3cf10
3. Have a maximum number of deposits on each planet
4. ~~Integrate creation of deposits with rover photo creation~~
5. Create rover action panel (see [[Mining Operations]]) - partially completed

## Visuals
**[New planet view](https://signalk.atlassian.net/browse/SGV2-158)**
1. ~~Find appropriate background images - ticket for Fred~~ [[Mining Operations]]
2. Fix image loading times - APPEEARS API
	1. Or at least, add a loading icon/spinner

### Layout
1. Tooltip to show user how to expand section: [comment on jira](https://signalk.atlassian.net/browse/SGV2-158?focusedCommentId=10755)

### Starter [classification] missions
1. "Classification" selector should be part of the big modal

## Content/Missions
1. [[Galaxy map]] -> maybe a dynamic list that fans out based on the direction and magnitude of distance? User can filter by "have visited", etc
2. Get the animal/zoodex classification to pull in classification options based on mission, integrate creation of posts mentioning the storage key [[02 Citizen Modules]] [[02 Citizen Modules/Data Sources/Data Sources]]  #zoodex 
3. Animals can discover things, be carried on roovers - powerups (cocoa beans citizen science idea?)

## Classifications/anomalies
#Anomalies 
[[02 Citizen Modules/Classifications/Classifications|Classifications]]
1. [Posts about an anomaly](https://www.zooniverse.org/projects/andreavarela89/iguanas-from-above/talk/3389/3429906) 
2. Multiple classification / `PostFormMultiple.tsx`

# Generator/Visuals
[[02 Globals/Bug Report]]
1. Increase pixel count for the "low-res" exports

# Chapter 2

# Structure tickets
[[05 Game Items/Structures/Structures|Structures]]

# Creativity/Garden mechanics
## Rewards, Content, Items
* [Rewards formula & pipeline](https://signalk.atlassian.net/browse/SGV2-146)

# Old content
1. [Messaging | SGV2-128](https://signalk.atlassian.net/browse/SGV2-128)