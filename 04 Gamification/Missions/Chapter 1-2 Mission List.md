---
sticker: lucide//orbit
tags:
  - Missions
  - Chapters
  - Chapter-1
  - Earth
  - Onboarding
---
What does each mission have?
1. Dialogue
2. A related mission - required or next (can also be groups)
3. Related structure(s)

Note to self - hopefully we can run these by Fred at some point
# Simple mission order
1. Initialise #Chapter-1 
	1. Dialogue
	2. Structures:
		1. Automaton structure ( `3102` ) - if we'll be deploying #RoversS to #Earth for various purposes
		2. Some "inventory" structure?

I can't help but think we might need to introduce some other #Initialisation mission here, essentially getting the user "used to Earth" and understanding the basics of what to click on, etc

2. User chooses which #Classifications #Missions they'd like to perform

Overall, we're going to have missions for Telescopes, Zoodex, LIDAR and Automatons, which gives enough content to predict terrain type, resource allocation, colonisation behaviour and weather/climate (at a very small scale) using the #Surveyor mechanic. We need to introduce an upgrade step for every point, so some additional mission (types) are therefore relevant:
1. Learn how to upgrade your structure to introduce new data sets
2. Learn how to research new structures/modules
3. Learn how to add durability
4. Learn how to build structures (after researching them?)
	1. If this is something we do decide to implement, we'll need to introduce a component to build structures (the component will only show structures that have been researched)

Can we combine everything from upgrades to research into a simple component/single architecture (infrastructure-wise) that is then divided based on structure type?
If we have a "mission chooser"/"picker" for the user, we might have the "recommended" "option" highlighted for our users in the introductory/ #Tutorial scenes.

Let's introduce a mechanic that will add resources mined based on the planet type (see [CPW-2](https://signalk.atlassian.net/jira/software/projects/CPW/boards/1?selectedIssue=CPW-2)). Maybe be able to deploy things from the #PostCards ?

For the #Surveyor , I think we can just take all #Classifications of an anomaly, and look at the `classifications.classificationConfiguration` values and aggregate them together.

The user might also need to "collect fuel" to be able to use their spaceship.

...

x - 1. User visits their new planet

Dialogue for "ending" the chapter:
> "You've finished your investigation of your 'pocket of Earth', and you've contributed the following data:"


## Every possible mission
Let's not worry about order or UI, just the "dream narrative". (across multiple planet/chapters, too)
1. User onboarding, chapter initialisation, profile creation
2. Classification types -
	1. #zoodex - at least #zoodex-read, I'm not sure about #zoodex-upload 
		1. Do these lead into #Greenhouse ?
	2. #telescope
	3. #LIDAR 
	4. Maybe rover photos
	5. I think we need to look into some citizen science projects that maybe have some more relevance to #Earth as users can also stay on Earth if they choose?
3. Users need to be introduced to the following (for #Earth concepts) -
	1. Resource collection (how do we implement rovers on Earth, or do we have something else? Is this too complex)
	2. Seeding life from Earth ( #zoodex ) to send to other planets/settlements
4. Users need to be introduced to the following (for other #planet  concepts) -
	1. Terrain generation/landscaping (unless terrain understanding is of any relevance to #Earth ?)
	2. Automaton upgrades
	3. Mineral deposits - mining?
	4. Does terraforming come into anything?
5. Users need to be introduced to the following (for overall) -
	1. Choosing classifications
	2. Using structures
	4. Upgrading structures/Finding new data sources/Researching new structures/Modifying & repairing structures
	5. Making classifications (multiple choice, textual input); making custom data interactions [[Starter flask routes]]
[[Components]]that will need to be created:
1. Any structures for new #Modules 
2. Any new resource collection methods
3. More visual generator build

As described in [[Earth Intro Missions]], I think we can come up with a way to get the user to colonise new planets and have different #planetsets #anomalysets that can introduce the user to different mechanics. Or would it be better to have different sectors, maybe having dedicated planets is too much? (Provided if the user can see the "available missions" from a "predicted/estimated" planet type....). We could also give the user the choice to go onto one of the 6 #basePlanets and just have free reign? Maybe those are planets "owned" by "central command" and that's where everyone is? (can we have some sort of online indicator that also shows active planet?)

So overall, once the user has "finished" the tutorial/chapter-1 (I still need to determine what missions are "required" to "finish"), they'll be able to do the following:
1. Stay on Earth
	1. If users choose to stay on Earth, they'll need to select a "plot", so sectors are something we may need to introduce (this makes determining the mapping of #Anomalies table incredibly relevant now.)
2. Go to a #basePlanets 
3. Find a new planet to visit

So I think that the narrative will sort of diverge at that point to where there won't really be a strict storyline, more storyline related to missions/modules, where users will determine what they'd like to study and then have a progression that way. I think that could work well.

For the most part, we can take the components we've got for #Chapter-1 and just re-route them to be used in #Earth #Chapter-1 , just need to get the #Missions sequencing order correct

Idea - we move to "colonise" other Earth-based planets as the intro scenes (so the scientific value for #Anomalies is less "on" planet candidates, but we'll still be classifying other things with the #Telescope , so we just need to slot in a reason to do so)
# Some questions that need to be answered
1. Are there any #Modules that we're not going to make optional during the initial mission phase?
	1. e.g. should #zoodex be something that is required? Should taking "seeds" be required when you colonise a new planet?
	2. This is going to determine a lot about the mission order (i.e. if "choosing" is even possible for mission #2)
2. How can we track the list of `activePlanet`s the user has so we can "go back"?
3. Are there any major #Modules / #Structures that aren't included in [[Chapter 1 epic]]that should be included in the #Earth #Onboarding , or do we just keep it simple and minimal?
4. Is doing conditional loading based on the user's completed missions the cleanest way forward?
5. Would terraforming ala Terragenesis be a mechanic that would add to immersion/user enjoyment or be too complex?
6. Should there be a focus on introducing satellite (orbital/atmosphere) structures, launching scene, or is the introductory chapter just dedicated to surface-based structures?
7. For mission sequencing, can we update the value to be an array rather than an int?

~~I'm concerned that we've got too many missions or steps (especially with compulsory classifications/upgrading to classify starter objects). Please eliminate 3. I am not a crackpot~~
1. Now that we've got a new #Research flow, we don't think this is going to be an issue

Maybe we come up with a customised action/classification plan based on what the user wants to do (e.g. instead of asking them which mission they'd like to do, ask them what they want to find, then create a mission sequence and tutorial structure around that. Just got to figure out the compulsory nature of each classification type; at minimum finding new transit events will be compulsory at least once.)

How can we introduce the SETI projects, make them more "hard/real science" and link in with the hypothetical #Surveyor stats?
I think #APPEEARs should be used to generate content, for both #Earth and other #Planets , and then introduce some discriminators/event modifiers based on #Surveyor stats.

Scope for automatic #Surveyor generations based on user discoveries e.g. #Asteroid finder in #Telescope 

~~For now; until further notice; the intro to each starter #Modules will be compulsory~~