---
sticker: lucide//bluetooth-off
---
Essentially the same thing as in [[01 Chapter 1]]but without the second required classification type. Just need to introduce all the basic mechanics to the user


The main thing is to get the mission sequencing, order & dialogue in place, and then provide enough classifications to make it engaging. Things like the planet switcher are interesting but not required for the current build.

## Starting on Earth
**What's the narrative?**
Key points:
* Onboarding components will be removed -
	* No need to discover new planets yet
	* No need to classify rover photos yet
	* Profile will be created as part of the mission for the user's first classification (and technically we won't need a separate mission for this as we can just use the `profiles` table to see if a user has updated it, however to keep everything formatted the same way I will create a separate mission)
* Users will immediately be transitioned to a scene on #Earth where they'll be given some starting items (after passing through the initialisation checkpoint):
	* Research #Structure (although it will have a `{"Uses": 0}` configuration)
	* Anything else?
* Initialisation checkpoint -
	* Will welcome the user, explain that they'll be starting on #Earth , what they'll be doing. After passing through this, the "Initialise Earth" mission is completed (and added to the database) and the user is then shoved onto the Earth scene
* 
* 
* Users will go through the same missions as before, choosing what they want to do. See [[#^356f8c]]
* After making their first classification, we'll need the user to research 
* 
* 
* After the user has finished their classifications, we'll show them the #Solar-System anomaly that is best suited for their chosen research topic
* User can then access the Planet Switcher

For each classification, we'll need to check the status of the tutorial for the user

Some questions - ^356f8c
1. How do we integrate resource management - just simple mining robots in a "plot" of land? Then we integrate rovers into the flow in the later stages? 
	1. Maybe mining bots just mine, they can't build or perform any other action...and regular automatons can. 
	2. So then what's the narrative reason where deposits require a classification of the landscape to be found? Something along the lines of the rovers don't know what they're looking at yet, while the mining bots already know where to go (they just can't find anything new?)?

Therefore, the following `missions` will be in place:
1. #Chapter-1 initialisation
	1. User chooses first module (this would be the same method as using the Research Station, however we'll provide a modal as part of the #Initialisation mission for the user to choose what they'd like to contribute to first, so they don't get overwhelmed)
		User then loads into the new scene, the structure for their first module will be initialised with the correct configuration, and we'll also add an entry into `researched` table (the user gets a free structure, and we don't have to add a method to the Research Station for the user to get a free research (due to `profiles.classificationPoints` value))
2. User completes tutorial for their chosen module (one of:
	1. TESS Planet candidates
	2. Sunspots
	3. DiskDetector
	4. Martian Clouds
	5. Burrowing Owls
	6. Iguanas from above
	7. South Coast Fauna Recovery
	8. Nest Quest Go
		Note - fish research (not introduced yet) and rover photos won't be part of #Chapter-1 on #Earth , although later chapters will allow users to research and conduct these observations on #Earth 
1. User makes their first classification in the module (and therefore have completed one of the following #Missions :
	1. TESS Planet candidates
	2. Sunspots
	3. DiskDetector
	4. Martian Clouds
	5. Burrowing Owls
	6. Iguanas from above
	7. South Coast Fauna Recovery
	8. Nest Quest Go
		User is then informed that they're able to classify more objects if they go into the Research Station. They're also able to go off-planet to get more content to analyse for their chosen classification (in step 2). The options then ->
			1. Research (and) build a spaceship & launchpad
			2. Research a new structure
			3. Research a new module
		The user is prompted with a question for what they'd like to do - "do you want to go to a planet/object that specialises in your previous module, research a new module with your chosen structure [show available], or participate in a new scientific discipline [show structures and a preview of their modules]?" (and after providing an answer, this completes the mission "Choose [first] next step")
		
		The user chooses one of these missions, and then an arrow that points to the relevant structure shows up (derivative missions: -
		1. If building spaceship, highlight the research station
			1. Research spaceship
				1. Research launchpad (let's put these together)
			2. Build spaceship (comes with free fuel in the configuration)
				1. Build launchpad (let's put these together)
			3. Access the spaceship and follow the tutorial for the PlanetSwitcher (spaceship) component
			Accessing the spaceship then shows the `<PlanetSwitcher ... />` component
		2. If they want to research another module, highlight their previous structure
			1. Highlight research button after clicking into the structure in `<StructureConfiguration` object
			2. Research a new module
			3. Complete the tutorial for the new module
			4. Complete their first classification
		3. If they want to research a new structure, highlight their Research Station
			1. Research new structure
			2. Place new structure (then highlight it)
			3. Research new module
			4. Complete the tutorial for the new module 
			5. Complete their first classification
4. The user must then build a spaceship and access the `<PlanetSwitcher />`, but the other 2 options aren't required. So the final mission is flying (changing `profiles.location` / `activePlanet.id` ) to the new planet (they can only select a planet that extends one of their chosen classifications. This should be explained to the user, the more they classify, the more places they'll be able to "settle"/"colonise" in #Chapter-2 ) 

Does resource collection (using the new bots I came up with) come into play here? Everything on #Earth (for "now" anyway) is sort of free (outside of researching structures, which requires `profiles.classificationPoints`)...
We also need to add a profile creation form at some point

All in all, we have a total of 28 missions available, a minimum of 9 must be completed:
1. Initialise #Chapter-1 
2. Choose first #Classifications #Modules 
3. Complete first #Tutorial #Missions 
4. Make first #Classifications 
5. Choose next step
6. Research spaceship, launchpad
7. Build spaceship, build launchpad
8. Access spaceship
9. Travel to new planet/body

Another note -> Researching new modules/structures may be completed in #Chapter-2 or later if users go straight to the #PlanetSwitcher action.

We can then introduce special missions for certain discoveries (down the line)

## Component-by-component
**Missions list**
1. Update mission component/functions to search through other API routes, or just bring everything into `/api/gameplay/missions`
	1. I also need to cross-reference the new missions with anything spare in the surplus/secondary routes

**Planet Switcher**
1. Needs to be made smaller
2. Images need to be inserted
3. Organise textual components into boxes

**Launchpad/Spaceship**
1. New icons
2. Planet switcher
3. Dialogue & documentation
Users will need to research these structures and place them.
We then need to show (through the #PlanetSwitcher what missions/modules are available, maybe provide a "recommended location"?)

**Mission Initialiser**
1. Documentation, dialogue
2. Any mission/api hits

**Main menu**
1. Capt'n Cosmos
2. Documentation/Guide

**Module researcher**
1. Need to add icons back (fixing the type error with the icons)

** #Generator **
1. Show image of planet (based on number of classifications)
2. Show their classifications
	1. We don't need to filter these by `classificationConfiguration.activePlanet` yet as users will only be on #Earth , so that makes it a little simpler
3. Trees and other things can be integrated
Sectors ("instances" of planets owned by users) will represent your unique discoveries and adaptations/buildings on your planet, and will allow different things to spawn in.
	Sectors will be introduced in #Chapter-3 

(go over other notes, too) #Greenhouse #terraforming , can add #Terrain maps (terrain affects *certain things??*?

Later ideas:
* Show a graph view of their classifications (later)