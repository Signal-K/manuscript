# Components to design
### Planet views
1. Ring layout
	* Could be used to display structures in orbit
	* This is dependant on the classification models that will be available in V2.0, potentially we won't need to launch anything into space and therefore we can hold off on this for now.

### Sector views
Sectors won't be pages, they'll be individual overlays, I think starting off as a popup list that shows the basic information. The interactions in-game are occurring on a planet-scale for now (e.g. deploying rovers, building/interacting with structures) so I don't think we need to have any write-actions for sectors at the moment

* Background images & maps/portions of maps could be useful though
* Generate complete make-up/composition when creating a new sector, including confirming that the rover images change each time

### Media
* Could the bg image be made up of a representation of your colony? "Our space colony".mp3

## Data
* Need to get planet data to filter into sector data - currently it's all disorganised

# Bugs
### Supabase
* Error: using the `AddResourceToInventory` button on `planets/sector/{$id}` does NOT add a sector value. I am assuming this is a bug as we do have a discriminator in the component definition, and not that this is intended to be the case (e.g. structures will be confined to a sector/planet, while items may not be by default? But should they at least show where they originate from)

# Items
### Automatons
Each of these will be introduced in the `inventoryITEMS` table, and they will have a parent item of id: `22`, as this is the "Vehicle launch structure". Not all of these will be vehicles, however for now we are working on rovers so this is the best way to do it for now

* Rovers will start on a planet and then be deployed (multiple times) to a sector to explore (gain information), collect resources, aide in construction, or collect info to review (e.g. photos). > SGV2-20 
* * SGV2-20: I will set rovers to be craftable using 1 piece of iron, this will be a placeholder crafting recipe (see [[Crafting]]) and will not use the crafting microservice/API route during this phase of development. Items will be collected just by the rover, there won’t be any special modifications/'rover arms' etc. for now.

# Classifications
### Rover data
* Each sector has a series (currently one, could be multiple though) of images from a rover, which can be classified (and would then return a reward, theoretically allowing us to structure the inventory/items component into this)
# Review (4-7/5/2024)
I would say the goals are as follows for V2:
1. Voidpet interface, supporting all below features
2. Crafting
3. Planets, sectors, and other "settings"
4. Working inventory across structures, blocks/items, resources, tools, vehicles/automatons
5. Mining, construction, crafting & travel mechanics
6. Following citizne science components:
	1. Classify planets -> lightkurves, compositions, etc
	2. Classify rover data
	3. Classify cloud data
	4. 1x lifeform tagging classification e.g. burrowing owls
7. Begin the narrative development & tie-in with old #Star-Sailors writings
8. Content population at a base level for "basic" planet data
	1. Complex routes beyond basic mineral calculation (for sector deposits), planet types (and basic stats as per v2 alpha stats component), generating data points (e.g. lightkurves to display), and a semi-automated verification system for classifications will be documented, but not implemented until subsequent versions.
9. Upgrading database schema for `"basePlanets` collections & other objects/entities to be classified (aka anomalies)
10. Music & other media

I believe we should look into minigames, broader rover/construction configurations & visual components in V2.1. Main goal for V2.1 will be consolidating our success & upgrades, adding more narrative content, and beginning a full stack migration towards implementing the next step in terms of visuals & content population. Of course, we will also be implementing user requests as well. 

# Inventory standards
All items will be created and deployed to a planet, and can then be migrated to any sector on that planet.
If it's on a planet but not a sector, it's not deployed
Hopefully this fixes some of the persistent errors I've been having as well as maybe providing some actual utility at some point (I don't want to be adding this confusion just for the sake of my immediate programming mood :))