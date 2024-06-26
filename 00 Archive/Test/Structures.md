---
connie-publish: true
connie-page-id: "11567112"
tags:
  - Star-Sailors
  - Editing
  - Active-Sprint
sticker: lucide//router
---
# List of structures

As of the time of writing, we’ve got the following structures defined in inventoryITEMS:

| **id** | **Name**                                    | **description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Parent                 |
| ------ | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| 12     | Telescope Signal Receiver                   | The base telescope. Provides a base that can then have other add-ons built on top, as well as serving as the base for all off-planet observatories                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | /                      |
| 14     | Transiting Telescope                        | An add-on to your telescope base (12) that allows users to view transits                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | 12                     |
| 22     | Vehicle Structure                           | Allows vehicles to dock to them, provides a method for deployment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | /                      |
| 24     | Surveyor                                    | This tool clips onto your telescope receiver and allows you to unlock complex stats about your anomaly<br><br>(side note: how do we get all this data? I guess the Configuration column in `anomalies` table allows us to add more fields without modifying the direct schema, e.g. if scientists decide a new field is helpful/required [for a standard] when discussing exoplanet candidacy, e.g. e.g. if temperatureEq wasn't included in V2.0 and we wanted to introduce it in V2.1). But the main question is how do we get all this data when a lot of it won't actually be known? At V2.1 I want users to be able to vote on data to be added, e.g. if `temperatureEq` isn't known when it's created. This also comes back to the creation/population process...)<br><br>> We'll determine what stats the transitting module gets and what this new survey module gets | 12                     |
| 26     | Meteorology tool (rename)                   | Will form the basis for all observations of atmosphere-related studies on the current planet (i.e. the planet it's situated/placed on).<br><br>Potentially will link in with telescopes for some initial observations on nearby/other anomalies (but will eventually require this tool on that anomaly. How do we link everything together?)<br><br>Has multiple modules.<br>At the start, it can return one cloud spotting each day -> you can augment it to return other things, and to increase the efficiency                                                                                                                                                                                                                                                                                                                                                             | /<br><br>Related to 24 |
| /      | (what tool is used to find/explore clouds?) | First module, specialising in cloud-spotting.<br><br>Could be introduced in V2.1?<br><br>Update -> Item 26 will facilitate the cloud spotting functionality. I don't know if we can come up with more specialised functionality, so this tool may be binned off                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | 26                     |
| 28     | Camera                                      | Is placed onto a vehicle structure, all vehicles created from that structure now have a camera.<br>The automatons will return from their journeys with photos (1 photo per day to begin with, across all automatons created with that camera-vehicle structure), classifying a photo will unlock an additional reward (let's say 3x rewards).<br><br>We might need to create a multiplier for rewards db-side. (edit: we might be able to create a local function that calculates rewards based on the modules you have installed in `inventory` table and the sector dynamics. Could start as a nextjs api route and then migrate to the flask setup in Sprint 4)                                                                                                                                                                                                            | 22                     |
| 32     | Camera receiver                             | Clips onto your original telescope and is used to store all images that your automatons pick up that haven't been classified. without it, your cameras can't report back to the telescope<br>Potentially the photos taken are listed as `anomalies` themselves and are linked to an `anomaly.id` "parent". <br><br>Needs to be initialised BEFORE the user builds item 28                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | 12                     |
| 30     | Mining station                              | Dedicated structure that is used to have a steady stream of resources coming in.<br><br>Same behaviour (with calculating rewards) as the automaton, we might just have one item type be able to be mined at a time (but you'll be able to choose which one, based on the sector/setting parameters) and you'll be able to upgrade it (see sprint 4).<br><br>Requires a classification on the setting [anomaly] to have been made first                                                                                                                                                                                                                                                                                                                                                                                                                                        |                        |
| 31     | Automaton upgrade station                   | Required to add things onto automatons.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | 22                     |
|        |                                             | Provide 2 more citizen science minigames (and the required structures) from `CPW-17`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                        |
| 33     | Launchpad                                   | A launchpad is used for the safe launching of all space-based structures & vehicles, and is powered by fuel. Users are given their spaceship when they pick their first planet and they use this (in the background) to travel to their planet.<br><br>Probably will require a structure for the construction & deployment of spaceships (i.e. a launchpad)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                        |
|        |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                        |
|        |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                        |
|        |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                        |

Structures will be split into the following categories:

1. Those that provide citizen science data → read/write (they will provide a platform to fetch/request data, return it, and then allow the user to make the classification).
2. Those that provide utility for resources -> allow the user to collect resources (e.g. mining drills), upgrade items (e.g. "enchanting table"), store resources (e.g. "chest"), etc.
	1. Some of these structures may allow the user to upgrade how fast/well they can do something

Summarisation of notes (below):
1. Users can create their first structure for free
2. Every launched structure has a corresponding, linked, structure on the planet
3. 12 -> Modal that shows the different telescope modules & parts
	1. 14 -> Users can add more modules/unlock tech to generate more complex/customisable light curves
4. 

## Global rules:
1. For every structure type (basic citizen science modules), if a user does not have one, they will be able to create one for free (i.e. if they do not have a TSR (12) ANYWHERE, they can create their first for free)
	1. This means we'll need to update the structure creation modal to make a list of all the structures they have so that we can have this free model in place. Currently, structures don't cost anything to create (in test versions) and I originally scoped it out so that the first structure of ANY sort would be free.
2. A note that structures that were launched will have a static command module that will stay on the anomaly's surface (or whatever synonym for surface is applicable for non-planetary anomalies). I do not think this will be a mere cosmetic decision

# Telescopes
Method:
### 12 -> Signal Receiver
This is the first structure that users will create for observatory-style citizen science interactions. It will initially be a pretty simple modal, showing a diagram of the telescope and a list of all parts that can be created.
I'm thinking long-term we have an interactive control panel with a live view of each component and being able to click onto each one, for now I think we'll just have a list view of components and their "status".
i.e. right now there's only one module to add to a telescope, which is `14`. If the planet AND AND user have this, then we can mark it as green. Otherwise, mark it as red and give them the option to build one.
Users will be able to create `14` without `12`, but it will give them a warning if they don't already have `12`.  This persistent creation method (rather than alternate creation methods based on structure hierarchy) is ideal because it makes my life easier :P

Space-based telescopes WILL require a launchpad

- While theoretically (judging by the Kepler Space Telescope, at least) one space telescope would be enough, the narrative would be that the first telescope that is launched is quite low-powered and can only observe near-field objects and generate their light curves. Once users begin collecting multiple planet anomalies, they could "connect" their telescopes to create an interactive network

### Data collation
I think that each base planet will have just one lightcurve graph, which would be potentially a binned graph. Users will have to launch instruments into orbit (i.e. space telescopes) to collate more information and build better lightcurves. This could help with the "customisation" issue but as there would be more total lightcurves (and as a rule, more methods of viewing the same anomaly of any type), that could introduce strain on our storage capacity.

# To-Do

For each type of citizen science interaction, there will be the following steps:
1. Click on a structure
2. Request data -> this may be instant or may require a time delay (e.g. sending the rover out to collect resources from a sector's deposit [Tiny Space program] will also result in it taking some photos, however these won't be received until it docks again)
3. Return the data -> this may be instant or with a delay (based on step 2). Some structures may only look at a single target and therefore not require any configuration (so Steps 2 & 3 are combined), or they may need a varying level of configuration
4. Make the classification -> this may be as simple as the text-box method we had in V1.0 and the alpha versions of V2.0, however there may be some multiple choice options or other ways to "write" the data

We will therefore need a layout for each of these options

We might want to take a look at state management for users' inventories, so we don't need to keep making requests back (i.e. make a local version/copy)?

**I also did just realise that activePlanet being used as a discriminator will be a problem when users have multiple planets...**

# Classifications
* Right now we have a global `classifications` table which I think will be where all entities/anomalies are classified (so every type of citizen science interaction publication/classification will occur here). Currently the classifications are differentiated based on the `activePlanet.id`, which is fine as now we technically only support lightkurve features, however we will need to update this (sector/structure based as well) to support other content
* We may want to have classifications (on a certain anomaly/about (for non-planet/body anomalies)) as a requirement for certain structures...

### Planets/Telescopes
* Users could share their lightcurves that are generated as a result of their findings? Potentially the telescope screen allows them to put together custom instructions for notebook snippets?
- New classification methods will need to be dreamed up so that users don't need to write a paragraph explaining data every time they want to perform an action

We'll need to plan out the category[/ies] that the items will fit into.

# (Put into GP-11)
## And make sure to mark it as a blocker of SGV2-20

Crafting
Crafting will be an important concept for the creation & utilisation of items, both in this next sprint (planned to start on Monday 29th January 2024) and the long-term vision for Star Sailors. For now, I propose we follow a simple crafting structure:
 Raw material [combination] → base building block → tool/structure/vehicle or other entity
Down the line, I think we'll insert a tertiary step between "base block" and the final product. We'll also set up things like refineries, smelters, etc and recycling items.
For now, refineries/smelters will just exist as a crafting station that don't do anything for simplicity.
Recipe list
We'll try and keep things simple (especially early-game/early-development), but realistic, and based on the materials that can realistically be gleaned from the sort of terrestrial planets we'll be exploring. Down the line we'll insert things like gas planets & transport of rare materials between planets, for now every planet will have multiple sectors for every raw material.
For the telescope, which is the initial structure, I propose the following:
1. 1x Coal
2. 1x Iron
3. 1x Alloy (made up of gold, palladium, silver, etc → essentially trace "metals"). (I know that IRL these sorts of alloys are unlikely/impossible to form due to the nature of purity of Au, however this is just an early-stage setup to simplify the number of sectors users will have to explore. Potentially we will insert 2 materials per sector).
4. 1x Silicon (for circuit board, glass for the mirrors/reflectors)

Once a telescope has been built, it will be slightly operational (will double the range of sector exploration) land-based, and we can add functionality later for ground-based observations. A launchpad will be required to launch the 'scope and get the full functionality:
1. 1x Fuel (refined from 'water' → hydrazine). (Will provide unlimited fuel in effect, for now instances of launch pads will not have a fueling utility or column/variable)
2. 1x Iron

A telescope receiver will also be required:
1. 1x Silicon
2. 1x Alloy
3. 1x Iron

I'm unsure how crafting will occur, I think for simplicity we might base it around client-side for now (i.e. client app would check inventory and deduct values, rather than setting the recipes in the db and deducting them that way).

Raw materials
Every item that will be part of this first collection:
1. Silicon. Will be labelled as "Silicates" due to its extra utility/combinations i.e. quartz, glass, etc
2. Alloy
3. Iron
4. Fuel
5. Water
6. Coal
Components
