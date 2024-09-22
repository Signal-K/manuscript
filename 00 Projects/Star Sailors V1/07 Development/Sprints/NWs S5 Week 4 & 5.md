---
tags:
  - Active-Sprint
  - Sprint-Planning
  - Star-Sailors
  - API
sticker: lucide//folder-up
---
Here are some ideas about features I want to implement into #Star-Sailors :
1. Get a comprehensive planet & landscape generator based on user data, classifications & overall anomaly completion
2. Introduce a mechanic for post card features where users can see their discoveries, zoom in on a planet (so have dynamic routes based on the home page to see their setup on each anomaly) and their classifications
3. "Expeditions" or community events in the vein of No Man's Sky expeditions where there's an objective, a special reward, and some collaboration initiatives
4. New narrative:
	1. Starter planets
	2. Base planet (location) sets for different mission paths
	3. Build a bridge between the planet narrative/content and our content in the solar system (e.g. Martian clouds combining with the equilibrium temperature from the exoplanet)
	4. A progression tree and map of your anomalies
5. Set up dynamic routes for anomalies to view the setup of each planet (users should be able to see each other's bases, maybe we start with a list of users on that planet (see `userAnomalies` table)). 
6. The post card can almost function as a sort of "terrarium", it starts off as an image of the planet with maybe some slight alterations to show the structure/life "configuration" and then shows the specific discoveries (imagine a vertical profile card with a cover image). Allows the user to paint their planet; 
7. Simple mechanic to design your own creations (e.g. custom configurations for roovers/automatons, structures, etc) via a sandbox building mechanic/component. And add a spaceship event and maybe a graphic too

The key take-away: we will centre things around community events, which themselves will be based on the demand of researchers. Users will work together to discover new areas to explore.

A key definition/note: Some planets will appear in our editor with "flat" areas (sort of like a flat earth) so that we can make them appear to simply be "worlds" or "locations/settings" and not focus on the planet aspect.

Here's what we can do immediately:
1. A list of anomalies (across all disciplines, not just planets) that are relatively simple but are at least partially unexplored. Create a configuration model for these anomalies (types) and create a configuration as well for "completion"
	1. There should be a completion definition for the overall userbase of an anomaly and each individual user for a particular anomaly, if they've visited it (setting/planet/location) or observed it
	2. An anomaly being completed does not mean it cannot be observed further, it simply means that all information has at least been partially estimated/calculated
2. Implement the new narrative with planets, starter guides and tooltips, move existing missions into a new set of anomalies
3. Simplify the structure models so that we have automatic upgrades and less structures providing more data/classification opportunities
4. Simple post card with (for now) manually generated image configurations for planet types, users select them based on their data (e.g. we have a planet generator that I run myself, spit out about 1000 images and then map them in the backend to different planet types, users will then see these based on their classifications). Later on I'll build a pipeline to convert the anomaly & classification data into a seed that will work in the current generator build![[icon.png]]
	1. Limited customisation available, maybe we provide 3-5 colour options for each configuration (so 3-5000 images total if we have 1000 configurations)
	2. Eventually I'll build sprites (like with the Polybrush editor in Unity...what's the alternative in Godot) for the structures and automatons, mining sites, etc
5. Page for each planet, showing the image, dynamic background and the discoveries and setup of the planet, will default to the home page for the active planet. Post card appears on top for the dynamic route/page. This way it's shareable
6. Page showing all community events (classify 100 planets, discover 3 bird species), link community events with sets of anomalies/planets
7. We need to devise a reward mechanic and an item mechanic that doesn't make things too complicated...regular game loop  


# Mission report update
I think that the tutorial text should still be based on missions, however it should be defined in the actual route for the mission, not in a separate component like it currently is (`TextBlocks.tsx`).
Additionally, I'm creating new routes for mission configurations and lists. This can serve in a similar format to the NMS community expeditions.


# Planet selector
I've created a new script that will allow the user to select the planet they're starting on as well as the planet they'd like to go to next. What we have to do is group the anomalies into the settings/locations and then into location groups (ordered by expeditions). Then we present them different views based on their completed missions, for example directing them towards the initial planet selector if they're just starting out, and then showing the full navigation (eventually the "galaxy map") with the planets ordered by expedition and collection/"mission type state" (e.g. "for navigators" or "for hunters")

# Database tables
## Anomalies
1. `classification_status` is probably something we're going to want to take another look at
2. We're going to need to take a look at adding a mechanic to track the "set" the anomaly is in
3. Anomalies actually need to be created - right now, `planet` anomalies are being created manually (either through the database editor and then using the python scripts to backfill the data; or an automated script. However, the planets are being added to the game not through the game). Cloud data DOES point to a planet (hence the placement in the `storage/{planetId}/clouds}` bucket), however the actual cloud image instance is itself an anomaly. If rover photos are being saved as entries in the `anomalies` table, why not clouds?

# Component-by-component
`PlanetGrid` ( `PlanetSelector.tsx` ):
1. There needs to be a function that will select a different set based on the missions the user has completed
2. Base set 1 is the default shown
3. Base set 2 will be shown when the user is ready to start their mission pathway
	1. Oh, we're going to need to create a global state here, aren't we...
	2. Users will have expeditions set, which will zoom in on certain parts of the map/list (however every set will be visible). Similarly, they'll be able to return to the traditional mission path
	3. Users will have the option to finish one entry in the second base set and then just go through the full models (if they just choose to prioritise one skill), or they can complete the entirety of a set.

It might also be nice to change the layout of the `PlanetGrid` component, maybe stretch it out so it takes up the entirety of the display and have the tutorial as part of it (just like how we're going to place the tutorial for each structure into the structure itself)
> I'm going to begin focusing on this tomorrow (24/7/24)

I think we need to create a scene for every type of planet. - **new jira ticket**

`TerrestrialPlanet`
1. I'm assuming that this will work for every type of terrestrial planet mentioned above

We need to have a global inventory mechanic that can fetch every item the user currently has (another thing we require electric-sql for)

`MyStructures` / `AllStructures`
1. Create a configuration for each planet type (only for certain structure types?)

What's the reason for components for each planet type? Just a different background configuration or something else? - Probably because there will be a different number of structures so there will be granular layout changes. Does this matter at this point though?
* There will NOT be a sliding panel for multiple structures - as few structures as possible. Some planets will have 3, some will have 4, gas giants may only have 1

### Post card
1. Implant godot or dynamic images at a minimum for all planet sets
2. Cover image, dynamic routes for sharing
3. Get custom post types working & integrated into each section; carousel for duplicates for same `author` `anomaly` `classificationtype`

# Scene(/mission) by scene
## Some notes/internal understanding
Currently, the flow of the game goes like this:

1. User authenticates themselves and begins the game by selecting the planet they want to start on (we give them a base set of 6 to choose from)
2. They'll then be sent to the planet they choose from, which will be "initialised" with a set of basic structures and an automaton (mining robot) already there
3. Users will be instructed to interact with each structure to make a classification and collect some resources, which will be used to power their rocket (spaceship) and carry on to the next location (they'll then be sent to a new set of planets [locations], each of which has a special citizen science (module) pathway/focus; e.g. users would select planet "a" if they want to focus on discovering new planets (the planet might be in the "best position" to collect lightkurves))

What can we add to step 1 (maybe splitting it up into a few "missions"/steps) so it's not just "click on a button and you're there"? Is it time to look into heavily animating the site using 3js?

## Subsequent plan/actioning
The users are going to start by selecting their planet

## Start/end
### Chapter 1
1. Selecting planet
2. User has an understanding of the main (current) classification options and has a post card with their discoveries

### Chapter 2
1. Choosing their pathway
2. A new set of discoveries on a new location, this time *more specialised* (tunnel vision), and the option to continue on their current location (setting *entity*), move onto a new pathway, or continue their current focus on a new location

We'll need to create new scenes for each pathway, taking a different anomaly/setting instance in as a parameter (dynamic components)

### Chapter 3
After completing one pathway, users will be invited to participate in community events. Community events will be limited-time projects that can be part of a larger citizen science module, will come with a participation badge and special rewards, and will introduce new mechanics and behaviours for game items like structures.

Community events will each have a goal (classify the entirety of this 1000-object dataset or provide 1000 candidates of *x*), a deadline, and a leaderboard to introduce a competitive aspect. 

Teams/factions will later be able to compete against each other; not entirely sure how this will work at the moment. Factions will be able to gain territory/resources that have not already been claimed (no PVP introduced), so in theory users may only be able to work in areas that have been attributed to the faction.

In addition to community events, users will also have new settings to explore and will continue using their existing structures (on previously visited locations)

When new citizen science modules & structures are introduced, new missions (not events) will be added to the mission log and new pathways will be introduced.

Another key part of chapter 3 will be about slowly starting to overwrite the Earth/solar-system-based content (e.g. martian cloud data) with actual content from the real planet.