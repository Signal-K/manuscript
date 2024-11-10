---
sticker: lucide//battery-low
tags:
  - Sprints
  - Sprint-Planning
  - Create
  - Chapters
  - Classifications
  - CommunityStations
Jira:
  - SSG-58
---
So, we didn't really get to where I wanted to be during this sprint:
> Goal - obviously some UI cleanup, add creativity & sandbox elements so users have the side-scrollable, editable view of their planet & structures/items, add view for noise/map (which is created by the community), and show icons of anomalies.
	Bundle that all together into shareable terrariums. Can fork anomalies/terrariums (these would be considered to have "life energy" (or something similar but less wanky)). Export anomalies/classifications to produce outputs that can then be compared with a sim environment (at a later date), add a consensus layer, add stardust, add some minimal spaceships scenes/functionality. Once we have enough content and consensus, can integrate SETI & similar projects (which then leads into some more fictional-driven parts of the narrative). Galaxy map that will then be divided into sectors, individual location anomaly sectors, and then generating perlin noise from everything to begin producing a map view.

So what I was able to do was start adding the slot feature, however I wasn't able to finish it as of now. Map & weather pattern ideas were gradually developed (frontend-only, though). 
The constant bit of advice I've received has been to give users the ability to create and collect things, and share them. So maybe we need to go back to this, gradually shift the narrative (initially, at least) towards this featureset.

I'm going to take the best of my other (currently open) notes from this week and then shelve everything and figure out where to go from here.

I think the key thing is to focus on one thing. So, we keep the current mission pathway open, but we also re-structure the "default" one provided to our users. Let's not worry about moving non-space anomalies/projects off-Earth for now. #Earth will be the main area that everyone stays in, all projects are available there. This is also where #upload s will occur.
Users will be able to participate in missions on other planets. These will range from general pre-population projects, where users discover exoplanet candidates that will later be used to bridge between this new temporary mission/plotline and the current pathway we want to re-implement in production; and to (slightly customised) planets or locations that will be fictional settings for users to "colonise" for rewards.

If we say the goal for #Star-Sailors is to allow users to perform any and all citizen science projects, on #Earth and off-world, then we need to have the content be able to be spread out and performed realistically on multiple location (types). Users would be flying around to research different skills and missions, building their own "bases" and "terrariums", etc. I don't have a mission structure or enough content to be able to come up with a way for our users to be able to perform biological or meteorological studies off-Earth with any real conviction. 
1. Dedicated missions on all location types for all playstyles
2. Colonisation/customisation of locations based on user discoveries & anomalies
3. Linking users & locations together through the use of community missions, stations & expeditions

So what we need to do now is to get users making classifications, creating some resources, and making those connections. This also allows us to restructure different missions & steps. So the first thing to do is to take a look at the missions that we currently have that would fit onto #Earth , which would fit into weekly expeditions or patch updates, and which would have to come later

A guideline for future sprints would essentially be:
1. Add at least one new project/module
2. Add new missions for each pathway
3. A new expedition or event that is different from the previous one

So here's a rough, proposed outline:
1. All biological modules will be #Earth -only for now (in terms of missions, structures can still be created off-world. However, no missions will be available for now and won't be until we can come up with a plausible lore-based explanation for how it all fits together with terraforming/habitability)
2. All meteorological modules will be #Earth -based for now, until we get to community missions/expeditions
	1. However, we will prioritise allowing users to travel to other entities in the #Solar-System , where #Mars #Jupiter #Moon will have available data
3. We will focus on perfecting #DailyMinorPlanet, #PlanetHunter , #sunspot , #Disk-Detective for #Astronomer . All of these missions will be performed on #Earth for now, so you'll have your own little "spaceport" or lab area on #Earth 
Then, we'll implement travel, allowing users to visit other parts of the #Solar-System as well as #Interstellar space ( #exoplanets ). We will require users to possess fuel & a rocket for ALL travel going forward.
We will have a special community event for each pathway each sprint, say:
1. Classify/confirm planet candidate "x" to add it to your collection
2. Find all rainbow lorikeets in your area
3. Map the surface of this planet/anomaly to get rewards

So what I need to do while at MRKT is essentially:
1. Determine a new mission plan
	1. And then how we bridge between this new mission plan and the new one. e.g. creation of planets from #Disk-Detective & #PlanetHunter  - how can we get users to work together to combine anomalies to produce their own...this is another answer for the pre- #Simulator value.
2. Link in with how we can get users to focus on #Starnet , maybe post-classification sends you straight there and you have to review others'?
3. #Earth will sort of be your terrarium area, based on what you've researched...in the absence of full terrariums and off-world travel (for now). Your area on Earth will transform and adjust ("terraform :)") based on what you add and collect. So it can show the weather & topography...because there's no restrictions on, say, having animals or anything. 
	1. So we'll need to determine a calculator or other discriminator for how these components can be shown and earned.
4. Determine a new UI, with an onboarding puppet/component. Will need to show the views (mining, weather/climate, structures....maybe a biosphere view?), quick actions (Travel, Build, etc), and #Starnet 
	1. Including the drag-and-drop structure configuration and other newly minted ideas
	2. Potentially the biosphere is replaced/part of the "terrain-osphere" for locations, for non-biological customisation
5. Determine a set of community missions to focus on.
	1. How can users travel to these new places, settle there, fetch/collect/complete and then return?
	2. Building from this, how does topography/mining work from #Earth ? Do we just, say, allow users to build their base from places they visit? So they can take pieces/maps of land and bring them back to #Earth ?
Let's come up with the simplest, most realistic narrative plan we can get, then determine the OOO and missing features (including where #user-input & #upload comes in), as well as the wriggle-room regarding narrative, and then get the priority matrices and get feedback on these features to make them more coherent.
As well as - backgrounds, characters (planet characters! - my singing monsters...)...I really need to look more at MSM. Maybe a base building game where you take care of anomalies? Just need to make sure it's more sandboxy than base-building. Allow users to comment on everything and anything, and to share it all....configurations. And look at the below content and from gpt. 
Summarise into list of missions/chapters/steps and prioritise. Then draw these characters, items, my ideal biosphere. Maybe ask v0 to draw a biosphere as part of the generator/card component.

#### Therefore, a good goal for today (3rd November 2024) to close the sprint would be to update the sign-up process in #Chapter-1 to resemble the Pokemon-onboarding process where users pick their new structure, can research and build their new projects, visit #Starnet to vote and comment, and then switch to the original pathway. 
I am not sure how exactly we can edit the current/new onboarding text flow to look more like Pokemon.
Next step - send users to #new-Earth #Scenes , direct users to click on the structure, follow the tutorial. Then have a popup explaining more content is coming, and we have a freeform mission flow [[Chapter 1 epic]][[Chapter 1-2 Mission List]][[Chapter 3 & 4 Mission List]]
> in short, let's get the onboarding to give characters, have an icon that gives help, and then figure out how we're going to implement the OOO on the [[November Mission List]]And create the new tickets
> 
> A note that surface analysis, some #zoodex-read projects & #Disk-Detective are currently missing in the onboarding
## WE NEED TO DETERMINE WHETHER TO FOCUS ON MISSIONS OR PROJECTS (AND UI). CLEAN UP THESE PAGES AS WELL
Then we can add a way to review entries in `Uploads` table and add them into `anomalies`. 

This also requires us to add the messaging & dialogue. For now, I think, we'll write-off #SSG-61 / #SSG-54 (grid-building system) to focus on getting this right. 
Tickets still in play:
1. #SSG-61
2. #SSM-41 - users will be asked to vote on #Anomalies, including #Classifications. So users will categorise things further after the initial #Classifications e.g. #Planets will be asked for the #planetTypes , we'll also allow users to connect #Anomalies together. For now, though, we'll simply ask users to vote on #planetTypes for #PlanetHunter or #Disk-Detective #Anomalies in #Starnet 
3. #SSM-46 -> Users will be able to reset their `profiles.activePlanet` value to `id: 30`, allowing them to participate in the new mission list defined in [[November Mission List]]
4. #SSM-21 - allow users to share their discoveries. As part of this ticket, determine #Generator or #icon / #drawing options for each anomaly. Include commenting and viewing in #Structures ?
5. #SSM-23 - determine how #annotations can be implemented/fixed
6. #SSC-34 - review and add into new mission list
7. Add the weather & topographic map views, only for #new-Earth, though. Show landmarks, eventually will show explored areas and other creations. Make this part of the #Starnet classification/postcard #SSM-21 
8. #SSM-59 - Update tutorials to include linked & lore content/descriptions
Allow structures to occasionally squeak and make noises, move, speech bubbles... Maybe re-add #GalacticRadio 


[[29 October 2024]]

2. Kick around ideas for post cards - include maps/views & anomalies/classifications, surveyor values, icons...clouds...icons...show icons in the view. That is a good start, me thinks. Just need to get the mission list from that, then.
	1. Things like rain
		1. Climate
		2. Colours (sky, patterns)
	2. We just need to figure out how these creative components provide value to the citizen science output (ouroboros... )
	3. Maybe these weather events can produce rewards...there's occasionally asteroid impacts which will lead to new mines opening up, or something? Maybe we map weather events to your location as well - eventually we would verify with an API like OpenWeather or something. Weather allows new anomalies to spawn? Or come out of their relevant structure e.g. owls coming out of the Greenhouse?
	4. Create views for every type of anomaly. Eventually the simulator will do its thing. For now, maybe we can argue it helps users slot their uploaded content in more easily (e.g. if it looks like your [irl] terrain...)...We just need to determine how we can use these views for the betterment (again ouroboros)
	5. Users can upload things they see and connect them to real anomalies (e.g. birds -> owls, clouds -> clouds). Maybe we're showing users how to compare and the differences, that's a good beginning? Maybe the users can help "train" or "feedback" the simulator models?
	6. Maybe users will create maps/locations matching their IRL setting to compare?




[[SSG-61-> Combining automaton & surface structure containers]]

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