---
tags:
  - Editing
---


# Frontend components
What do we currently have?

1. Initialised nextjs project with the main styling and backend providers initialised and working (only waiting on blockchain/federation, and payment processing, which I don't think is required at the moment. I want to have a chat with David, Grant/Manu & Rhys about federation vs Supabase)
	1. Update: I think I'll keep an eye out for the new announcements from Lens Protocol and Farcaster regarding integration & interaction (custom frontends). herocast appears to be a good bet for building a frontend around.
	   Most of the other blockchain stuff can wait for now. Supabase for `classifications` and other db stuff WILL suffice for V2.0 UNLESS LP comes out with a new & improved SDK & documentation very quickly
2. Main layout structure -> I want to review the way we have the layout components organised (and the rest of the component folder/directory structure) with Rhys, once he finishes the grid
	1. Waiting on a meeting with Rhys...

## Pipeline - Immediate
1. Fix grid. Currently it's an *8x8* grid which is not compatible with mobile devices (as it converts to a single column on small screens [width(s)]). We need to take a look at how we can achieve the desired positioning and fix the grids.
	1. I've done the Minimum stage for this by creating the grids and components (automaton single & structure single, as well as the fetching) that is required. At a base level, all that is required is these single components to be placed into dedicated sections. The next step is to match that Minimum component status up with the original design
2. Plan out narrative/order of operations for the user (Rhys, I'll need you to run all the "First Hour of Gameplay" bullshit(/notes) through some sort of AI summariser, and we can compare it to the new Minimum plan). This is important because we need to determine how users are going to build things like Automatons (Rovers at the moment) & Structures, including the free threshold at signup/onboarding (initialisation of [the] user). 
		This will also include the process of mapping out the structures (from a narrative p.o.v.) and the hierarchy. The hierarchy will be further expanded upon in subsequent versions (see below)
		For now, rovers will be the only type of automaton, I don't think we require an upgrade system yet, and we'll have <10 types of resources to collect. (see population pipeline)
1. Control panel format. For now I'll plan out the Minimum stage (what information is to be shown and what interactions will be possible) for Automatons, Structures and the broader planet route ([page]) and then start building that out while you (Rhys) handle the grid. Once that's done I'll hopefully have completed the Minimum stage here and can handover my code & vision for the finished design.
2. Once we have designed the control panel format for the 3 main components (as of now), I will begin work on integrating them all together with the "Single"-Automaton/Structure components, which have already been created and are/will be in use in the Grid layout (see #1).
3. Then we can begin work on the overlay structure and animations. I will take screenshots & describe my ideal scenarios/inspiration.

## Subsequent versions (post-V2.0)
1. I want to look into converting some of our components into a NodeJS package so we don't need to have so many components. Things like buttons and stuff. Potentially content-rich/argument components like the structure components could be packaged this way as well
		The question I have here is how much understanding will we have when using these components, and what will the process of editing them be like? Will we have to make a full-on production deployment to `npm` to update them?
		Do we maybe just have a local package that has major releases pushed to `npm`?
2. I think that the broader control panel (full screen) for the automatons/ro(o)vers can probably be postponed as the basic requirements for V2.0 probably don't require it yet. However, we will review the requirements shortly.
3. Periodic-table style tech tree (for roovers and structures).

# Administration/Project timeline
1. Plan out how our Jira boards will be initialised/expanded (e.g. we need to move away from GP, CPW, FCDB & SGV2). This ties back into the Confluence stuff

# Content population components
## Immediate pipeline - V2.0
1. ~~Define the list of structures that will be used for our citizen science modules, the upgrade structures and the crafting/resources needed to construct them~~

## Subsequent versions (Post-V2.0)
1. Maybe we could extend the `sectors` pipeline further with coordinates?

# Gameplay timeline
## Subsequent versions (Post-V2.0)
1. Currency system (GP-7). To review viability...
2. Potentially the alchemy-style graphics/construction [mini]games (little alchemy )
   SCROOBY WANTS TREES! Easter eggs (gizmo/scrooby/r2d2...**&^ (inside rover/structure)) <!-- Washing/repairing "retires" a cycle/chapter in the life. Plan for immortality. s[paceships]. Plan for graphics, inspired by SW  -->

# Backend timeline
## To make/initialise
1. ~~Docker configuration & local Supabase instance
		This will include a Flask configuration (potentially with a local runtime environment for Zooniverse/projects that are in Zooniverse in later versions), a Supabase instance that matches up with the current "Testing Playground" container (format & env), and the NextJS frontend. Should include scope for other additions if required
		We need to review if Flask will be used in V2.0, upon further reflection I feel that we should only have the Docker container setup for the immediate requirements (for now).~~

## Classifications/Citizen components
1. ~~Upgrade Supabase structure so that we can have one table for all types of anomalies (if possible). Discuss with Dave how we can do this. I will start building out an interactive API for the creation of new anomalies & the autofilling of data points & classifications. Additionally, I will discuss different contribution models to ensure we can provide maximum value from the start (from a contribution/classification standpoint), even for anomalies that have already been classified (e.g. further things to classify like spectra/atmospheric [emissions])~~ I have now created a `configuration` table which should take care of all of this.
2. Define "read" data points for the initial citizen science anomaly types -> what data will be showing (e.g. TIC ID graphs)
3. min. 1 further type of anomaly that piggy-backs off the `basePlanets` type/anomaly (that will be implemented in V2.0), as well as a plan (technical & narrative) for 2 more anomaly types.


# Design review & subsequent components
Here's a list of everything that the current Figma design proposes:
1. View structures
2. View automatons
3. Interact with structures
4. Interact with automatons
5. Switch between your "active planet"
6. Background & information section

Outside of the two external pages (see the VP top navigation menu), this is probably a good start.

**What does this allow us to do?**

Here's the desired requirements from earlier:
1. Voidpet interface, supporting all below features
2. Crafting
		This can be done in a "craftery" structure, basic implementation of crafting would be required. In terms of building structures/automatons from raw materials. Crafting recipes for structures will be changed in subsequent release versions, additionally more types of things to craft (e.g. you may need to craft a "middleman" item from raw materials before you can craft a structure.). At V2.0, we will not have a separate structure to perform crafting interactions, there will simply be an interaction to build a structure (by clicking on an empty location) and then the transaction of the required materials.
		Potentially we could have the structure locations be based on their proximity to resource deposits or other settings (including non-natural, e.g. some structures will require a "twin" to be paired/partnered with)
1. Planets, sectors, and other "settings"
		It's looking like we'll scrap sector functionality for now for structures & other items. Sectors will only be used to deploy rovers to, to acquire resources. Structures will be assigned to a planet, not sectors (this is to save issues with filtering/postgres interactions across multiple table FKs). This will change in subsequent versions and may require automatic assigning to sectors or new item creations when we do so.
1. Working inventory across structures, blocks/items, resources, tools, vehicles/automatons
		I think perhaps the first thing I could do is begin testing a local instance of `inventoryITEMS` and move that processing to be entirely client-side.
		Resources are collected from sectors by automatons, and used to create structures, ergo everything in the current [minimal] frontend plan is compatible with this requirement
1. Mining, construction, crafting & travel mechanics
		Travel in spaceships will be held off until at least V2.1
		Mining - done by automatons/rovers
		Construction -> already covered
1. Following citizne science components:
	1. Classify planets -> lightkurves, compositions, etc
	2. Classify rover data
	3. Classify cloud data
	4. 1x lifeform tagging classification e.g. burrowing owls
2. Begin the narrative development & tie-in with old #Star-Sailors writings
		The old writings will remain in purgatory until closer to V3.0, but a broader narrative can be adopted (e.g. Sky Machine) 
1. Content population at a base level for "basic" planet data
	1. Complex routes beyond basic mineral calculation (for sector deposits), planet types (and basic stats as per v2 alpha stats component), generating data points (e.g. lightkurves to display), and a semi-automated verification system for classifications will be documented, but not implemented until subsequent versions.
2. Upgrading database schema for `"basePlanets` collections & other objects/entities to be classified (aka anomalies)
3. ~~Music & other media~~

Perhaps I could create some different things to classify based on new structures (for new citizen science interactions), stub functions for API interactions.
Also, if we move `inventoryITEMS` to be client-side, this may fix the rover issues.