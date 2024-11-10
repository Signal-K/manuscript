---
Jira:
  - https://signalk.atlassian.net/jira/software/c/projects/SSG/boards/20?selectedIssue=SSG-61&sprintStarted=true
  - SSG
  - SS
sticker: lucide//cloud-snow
tags:
  - Structure
  - Structures
  - Automatons
  - RoversS
---
Essentially we will have these items exist in the same space to limit the height-based clutter in the mobile frontend.

Question - how can we manipulate this new grid feature to better explain & direct the users (mission list)? Do we add a floating #CaptnCosmos  button after all? Then, how does it affect/lead to the cards/customisation?

## SSG-62
Okay, so if it's like Pokemon, we have a grid where users start on #Earth , they choose what they'd like to do first, and then we give them a structure to place on #Earth 
This structure will then be configured with the project/module the user requested
We'll do the same thing on each planet - based on the user's pathing/pathway, we'll present them with some available projects as part of the structure, they'll choose which one and the structure will be created
We can then create a "quick actions" panel on the edge of the grid that will allow them to quickly research new projects, this research will automatically be added to the relevant structure

So ^ this overhaul/edit affects/fixes some of the user flow/documentation issues we were having before, but it also leads to a new component (SSG-63?) - some sort of tutorial text area. I might need to have a chat with Rhys about how we can point to certain text strings based on missions. Maybe we just have a text value after each mission is completed, that then is displayed below or above the grid?

For mission completion/pathway updates, I propose that we follow a new type of structure/format -
1. Users will have to complete pathway-relevant projects on starter ( #Solar-System ) planets - #Chapter-1 , #Chapter-2 
2. Users will have to discover new planets - #Chapter-2 
3. Users will only be able to populate their planet with data/content from projects they've performed in the #Solar-System - so we can have a "Main quest completed" & an "All quests completed" ribbon for each #Chapters 

The goal for each #Chapters :
1. #Chapter-1  -> Introduce the user to structures, classifications, and construction. Transition to #Chapter-2 begins when the user heads off-world after researching & building a #Launchpad (and maybe a #Rocket as well)
2. #Chapter-2 -> Introduce users to community stations/missions, connecting pipelines and travelling around the #Solar-System completing similar projects/missions
3. #Chapter-3 -> The user should begin classifying missions/projects on their new planet
4. #Chapter-4 -> The user begins crafting their world/environment. There will be a sandbox world for everyone to manipulate that is #Earth-like - #Earth . Users can go back at any time. 

Users will need to work together and wait on other users or themselves to complete other pathways. So community stations will serve as a reference for content or items/anomalies that are missing or research that needs to be performed. E.g. once a new system is found in #Disk-Detective , users can browse for these in their #Structures , but will need to find a matching #PlanetHunter anomaly too. A planet will need to be mapped before mines can be placed on it; this would require clouds to be discovered and matched.

So community stations will allow:
1. Anomalies and items to be transferred
2. List of missions or next steps for the current location. Ability to research new projects, missions. Upload content
3. Early customisation of anomalies

So now we just need to determine the reason for building off-world ( #Earth ). How does this help us/science (output)? Can we combine this with the creativity/sandbox environment/outlet to answer this question?

Next steps - 
1. Reorder missions. Introduce a "base level" and "100% completion" level for each #pathways  & #Chapters 
2. Update MissionPathway/Log component to identify completion based on `researched`, `inventory`,  or `missions`
3. Add the dialogue component, and add a string value to each mission
4. Add proposals to #Starnet , ask users to classify/vote on them further for them to be added. 
	1. And determine missions/jobs for users to perform as part of the pathway, but specific to #Starnet or #CommunityStations
	2.