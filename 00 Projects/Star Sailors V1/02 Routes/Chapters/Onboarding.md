---
tags:
  - Star-Sailors
  - Sprint-Planning
  - Data-Population
connie-publish: true
sticker: lucide//cup-soda
---
The main aim of this chapter is to introduce the user to the key mechanics of the early chapters, including 
https://signalk.atlassian.net/browse/SGV2-136?focusedCommentId=10569

We need the user to be introduced to the main mechanics over time, here's what I would say the full list of mechanics would be:
1. Getting resources
	1. Using rovers to collect small amounts
	2. Upgrading your roover/automaton to get more (variety & quantity)
	3. Deploying dedicated mining stations/protocols ^5f21c1
2. Building
	1. Creating structures [[#^5f21c1]] ^46498e
	2. Creating base components (this is probably the most sandbox component overall, I'm just not really sure what the users could build. The goal would be building and customising your terrariums/post cards so what can we do there...)
		1. A note that this is probably a way off because I don't think we have the infrastructure ready to integrate a dedicated game engine into the web build yet
3. Classifying data (which comes from structures) [[#^46498e]]
	1. Planet data
		1. Planet candidate validity - lightcurves (determining if the planet you're looking at is real)
	2. Fill-in data (essentially data from Earth/solar system entities that we use to fill-in the missing pieces of the user's EXO-planet)
		1. Martian cloud data
		2. Mars rover photos - user works with these to "populate" (add content) to their planet (e.g. adding mineral deposits (which would also come from mining citizen science projects/modules later) or animals)
	3. On-planet data
		1. Animals
			1. Classifying others' animals (users' submissions as well as dedicated research projects' assets)
			2. Adding new animals to the database (file upload, can extend to pretty much anything). #zoodex component/module, this will serve as one of the big entry points for Capt'n Cosmos

Here's a brief list of what I would say our UI components would be (that we need to sort out for the onboarding chapter & chapter 1):
1. Dynamic background image, organisation of layout (structures, automatons, anomalies/other entities)
2. Dynamic planet images (for the terrarium/post-card)
		![[2.png]]
		See [[Planet list - Anomalies]]
3. Public dynamic routes to view anomalies (we also need to take a look at overhauling how `"anomalies"` are organised database-level to better support non-planet [candidate] entities) [[NWs S5 Week 4 & 5]]
4. 

Layout/vibe inspiration for Fred:
1. Voidpet
2. Hades' Star
3. Pixel Starships

Some other ideas (from pages like [[NWs S5 Week 4 & 5]]):
4. New narrative:
	1. Starter planets
	2. Base planet (location) sets for different mission paths
	3. Build a bridge between the planet narrative/content and our content in the solar system (e.g. Martian clouds combining with the equilibrium temperature from the exoplanet)
	4. A progression tree and map of your anomalies

Get a comprehensive planet & landscape generator based on user data, classifications & overall anomaly completion
2. Introduce a mechanic for post card features where users can see their discoveries, zoom in on a planet (so have dynamic routes based on the home page to see their setup on each anomaly) and their classifications
3. "Expeditions" or community events in the vein of No Man's Sky expeditions where there's an objective, a special reward, and some collaboration initiatives

We also need to get the user set up with a profile for their classifications (username/display name, avatar, bio/name, etc). How do we introduce Capt'n Cosmos in the onboarding?

So we need to take a look at the overall narrative and determine the order that users should be introduced to the different mechanics, e.g. what structures/data modules we put into the onboarding (e.g. the cloud classifying module will be introduced to the user in chapter 1/2, not in the onboarding (same with other, new structures)) and then sort out an Order of Operations (and subsequent long-term [responsive] layout) for this.

# Sprint planning
## Gp board
> Goal: Components (generating, classifying & gameplay/mechanics) for onboarding (teaching users how to play the game, starting them off with a borderline starting point that feeds into the main game loop starting in chapter 1).

Zoodex/Animal classification (both uploading & "scanning"/classifiying [others']), Lightcurve classification, Rover photos. This will populate your first planet (chapter 1)

Update: Will review with @liquidnetwork.ai , I think we have a start of something. At the very least we can use this as a starting point for importing dynamic images with flask, which is probably the closest to my original design philosophy (see microservices I once came up with and abandoned 🙃 ).

I’m going to get onto putting the base images into the simple two-panel editor in [https://signalk.atlassian.net/browse/SGV2-136](https://signalk.atlassian.net/browse/SGV2-136) now as we don’t need to have a full dynamism yet, maybe we can convert lightkurve to a js package too (thanks Tim Meehan for the suggestion)

R2-D2/roover shaped terrarium
## SGV2 board
* Create a ticket to archive/keep track of `components` dir and relevant files (i.e. what will be retained and what has been functionally replaced as of now)

Goal:
1. ~~Final nordkurve changes, including /terms route~~
2. Clone copernic repo, run supabase locally, make sure everything works, copy everything to a new page for nfts, update the table fields (new table schema on supabase) to be more in-line with spacibles/art NFTs, and then add a search component
3. Star Sailors - working simplified lightcurves for each of the `basePlanets` and integrate into the SGV2-14 workflow, give something back to the user
	1. Idea -> standalone reading app, also good portal for researchers to add/view data (can be in game format or reading format)

# Come up with a list of components (frontend & sytizen/backend) that will be required for onboarding (connect with above notes)
What will be the onboarding steps?
1. Fill in your profile
	1. Avatar
	2. Username
	3. Full Name
	4. Email (already included) [readonly]
	Consists of:
	1. Avatar component; button to upload new avatar
	2. Three text input boxes with labels (above)
	3. Some sort of Capt'n Cosmos textual information
	4. Update button
2. Lightcurve classification - first part of "populating" your new planet
	1. Lightcurve graph; with labels
	2. Description of how to classify the graph (from Capt'n Cosmos)
	3. Initial answer [multiple-choice] buttons with subsequent text [input] box for more detailed answers
	4. Submit button
3. Rover photos classification (will be used in conjunction with your findings from step 2 to determine which animal set to show in step 4)
	1. Deploy your rover to the new planet
	2. Get some photos back (one photo/image rendered (at a time))
	3. Multiple choice input
	4. Submit button
	Notes:
	1. We'll need to update the api to only fetch photos from a certain rover camera, as your automaton will start with only one camera (and be upgradeable)
4. Animal classification (classify others' only, no uploading yet. The type of animal research project (e.g. penguin classification) will depend on the picture of the planet that has been generated so far (we'll use AI/some other algo based on your answers and the other details of the lightcurve))
	1. Image
	2. Description of how to classify (and what to do)
	3. Multiple choice answer (provided based on the mission, e.g. https://www.zooniverse.org/projects/penguintom79/penguin-watch) (these will be hardcoded for each "starter" mission (i.e. those that are available in the onboarding chapters) before relying on an API to interact with)
	4. Submit button
	Notes:
	1. We'll need to produce some explanation (in-game & irl lore) of what this has to do with generating the planet, including the information about backfilling your new world with info/content from the worlds in our solar system (especially Earth)
1. Your planet will generate (and populate) with content from your answers (and the algos)

Other/global components to make:
1. Capt'n Cosmos & textual responses (and dialogue)
2. Perhaps we should also show a view of the planet you're creating (after the first one, of course)

Some notes:
1. Aside from the Lightcurve mission (step 2), we won't be having any expandable (custom) input for the citizen science modules. Well, maybe we could (don't want to limit the user, especially if they see something cool), but the algos won't take their input into account. Unless we explain clearly to the user that they can go back to their first classifications later...hmm
2. Outside of the lightcurve component, we also need to take a look at the overall order of operations for the onboarding window/tile and the `StructuresInNav` script too

# Aim for tomorrow - clean up current Jira board (maybe archive/delay current sprint), or start a new one

# Index route - OOO
There are a few types of visitors/users we'll be experiencing:
1. Users who aren't authenticated
2. Users who haven't finished the onboarding/
	1. Mission 1
	2. Mission 2
3. Users who are at the sandbox stage of gameplay

What differentiates them (from a code perspective)?
1. No session token -> show `<LoginPage />` component
2. Haven't finished onboarding chapter -> `<OnboardingWindow />` component (this would be defined by a mission completion step, right?)

We should probably restructure missions to follow a pattern rather than just be an incremental increase in numerical value for the primary key. So let's divide things into a set of mission groups:
**Mission Group 1 - Onboarding**
1. Sign up/initial authentication
2. Filling in profile - just need the username, users don't have to upload an avatar or have a display name if they don't want to
3. Initial lightcurve classification
4. Initial animal classification
5. Initial rover photo classification
6. Planet has generated - you [the user] now have your first anomaly (anomaly group? Anomaly setting - remember we need to redefine the `anomalies` structure)!

For the onboarding, there won't be any mention of an inventory (beyond rewards being added, maybe a little animation for that [upon completion of missions/steps]). Users won't be requiring the building of structures or even using them (they'll be generated behind the scenes, I changed my mind about how anomalies are displayed in the [[Onboarding]] chapter. Data collection/population process will be decoupled into a different component to the overall structure, but they'll still require structures. These structures will be on a "void" planet (implied to be your spaceship, or someth) and then move to the planet you "generate" ("discover") when chapter 1 begins/onboarding tutorial ends)

7. Transitional mission - travelling to your planet (between MG1 & MG2)
**Mission Group 2 - Chapter 1**
1. Structures update their location - autonomous step (however we still need to keep this as a step to track IF this has happened)
	A note that the next missions/steps are not all in order
2. Surveyor module (not using the surveyor structure, as that won't exist I don't think - more say the "surveyor" "functionality" of the telescope) - look at lightkurves PLUS other data to get a picture of the raw values of your planet (come up with some bullshit narrative as to why you need a telescope to get this information. Maybe it's to double track/check and keep an eye out for neighbouring planets that might be interfering, to better the telescope for everybody (another citizen science addition)) 
3. Last mission - classifying another lightcurve (basic one for now)

Enquiring to GPT about the best way to define missions/progress from a programmatic perspective (dictionaries in an api route). Coming up with pro-gameplay names for these missions, combined with maybe an indicator or splash modal when one is completed/achieved?

Inventory & missions need to be more coupled to provide rewards and better understand the difference between automatons, upgraded automatons, mining stations, and the relationship between `inventory` and `missions` table from a db perspective.

Showing a mission log for completed, in-progress & upcoming missions, with the internal steps and a deeplink to the area/component for the mission is something we should add.

Note: in the future, missions will need to be able to be created dynamically so that we can fit more information into the log:
> We need a component that can be dynamic enough to take in some metadata/information from the interaction (e.g. identify which classification was completed for the mission to take place), take in mission data itself (e.g. don't create another entry for mission id "8" if the user has already completed it), etc. 

### inventory updates
What items will be part of these steps?
1. Structures -
	1. Telescope
	2. "Zoodex" module
	3. Rover photos (determine relationship between current workflow [items] & automaton entities/instances)
		A note that these structures are "'semi-'broken" and don't have a location until the user begins chapter 1 (mission group 2)
2. Entities - 
	1. When do anomalies come into this? (~~we won't need automaton instances for 1.3 as the photo~~...oh, maybe we will, something to "deploy")

Earth "base planet" introduced after chapter 1 for where early-game NPCs/complex constructions come from (explains away the need for alien intelligence until later in-game when we have more clarity about how to introduce this relationship)