---
sticker: lucide//hop-off
tags:
  - Design
  - Meetings
  - Active-Sprint
---
## Unfinished business
1. ~~Status of new background assets (resolution MUST be fixed by today)~~

## Product changes
1. ~~Once user chooses their initial project, they're unable to change until completion of first classification~~
2. ~~Perform demo of new platform (and mobile staging) deployment~~
3. Demo and feedback for #Classifications overview ( #Generator )

## Bugs
1. Persistent scrolling issue (convert to parallax effect for mobile & terminal users) in #Onboarding 

## Missions
1. ~~Finish [[Mission list]] for today~~
## Components
1. ~~Final design for Capt'n Cosmos dialogue box~~
	1. Now i just need to implement it (thanks Fred for giving me more to do, arsehole)
2. ~~Go through icon & visual asset architecture (via Fred)~~
3. ~~`SGV2-194` -> component & modal inner design~~
4. Finalise design for GPS panel design / action panel

## Questions
1. ~~For #Mining, should the flow just be component-by-component or via a grid modal?~~
	1. Component-by-component
	2. linked/child ticket for `SGV2-200` for user feedback around clarity
3. ~~How do users earn "research points"~~
	1. By doing classifications
4. ~~Outside of your "mined" minerals, is there a requirement for the #Inventory panel in #Chapter-1~~ 
5. ~~Saving images ( [[10 September 2024]] )~~
	1. Current approach works, just need to prevent duplicate `anomalies` table entries (also refresh to change optics)
6. ~~Scope of #Greenhouse in #Chapter-1~~ 
	1. #Chapter-1 -> users are given owls, then we expand your sectors for different animal types from "central command", populate with alien life in #Chapter-2 to begin ...
	2. #Greenhouse will be the name of the structure with the utility of #zoodex 
	3. Limited scope will just be a way to keep track of your Owls (for now) and your discoveries. No plants yet
7. ~~How do we go about providing an "estimate" and "updated estimate" from the #Surveyor perspective with the [[Research topics for Chapter 1]]~~ 
	1. "Discoveries" from the #APPEEARs module, terrain generation. 
	2. Starting base planets behaviour is different to subsequent planet collections
	3. Rover photos are the key identifier in the **temporary** absence of the #Surveyor module [usyd](https://www.sydney.edu.au/news-opinion/news/2022/05/26/how-plate-tectonics-have-maintained-earth-s--goldilocks--climate.html)
8. What's the #Narrative position on spaceships?

## Scenes
1. Specific scene architecture & order of ops from initialisation of #Chapter-1 -> First #Classifications -> #Mining -> #Research & beyond

## Classifications
1. Other APIs to use (for #Chapter-2 & beyond)
	1. Is #LIDAR, #Telescopes & #zoodex sufficient for our users in #Chapter-1 

## To test
1. Test "first [choice] classification" mission when research structure has been created
# Deployment & Publishing new release
New release is scheduled for 14th September 2024, development MUST be finished by 12pm GMT+1 13th September 2024 to begin process of merging into `development` branch and begin automated testing.
Social media approach & marketing style, new version name needs to be finalised, I will handle the product launch for V2.2.

# Outcome
1.  #Telescope #Structure  -> multiple configuration options (toggle in inner modal)