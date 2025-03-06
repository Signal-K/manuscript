---
sticker: lucide//cloud-snow
tags:
  - Questions
  - Sprint-Planning
uniqueId: 27e1afa3-ddf4-4e44-a868-b106135a1fc5
pageId: "97353729"
spaceId: "34021"
confluenceUrl: https://signalk.atlassian.net/wiki/spaces/SSV/pages/97353729/Question+Megadoc

---
Scope:
1. Ask these questions at the end of every sprint, tick them off


# #SSG-100

 1. Do we suggest that each location/planet [anomaly/entity] can only have a limited amount of anoms attributed to it by a player? I.e. do users need to start scanning other planets after a while?
 2. Puzzle pieces - how to implement [[Earth layout]]
 3. New folder for [[Data collection (probes)]]?
 4. Location in Obsidian for [[Post Card Designs]]? (make.md)
 5. Where does [[02 Globals/Galaxy map|Galaxy map]] fit in (in terms of gameplay and obsidian)
 6. Hexagonal map - if we allow multiple biomes/terrariums for single locations (or maybe allow users to see others' biomes/locations on the same location [entity/object]). 
	 1. I do think that allowing for multiple biomes on the same planet, maybe with some (eventual) shared infrastructure is a good plan
7. Are there any opportunities for life on "non-Lush/life" biomes?
8. How do we indicate oxygen/ozone-rich clouds or CO2 clouds in #CloudspottingOnMars ?
9. #picaso as an extension of #PlanetHunter mission group, or someth else? Likely to push this further back, anyway
10. How do we match up the specific entries in each biomes' parameters with classifications?
11. Ocean biome solvents...
12. Should P.temp calculation be in #Chapter-1 or #Chapter-2 or #PlanetHunter ?



# #SSG-102 
1. What is the process for verifying/vetting planet types, including subgroups (terrestrial > icy), and how do we implement that into the `PickPlanet` components
2. Let's add #WeatherEvents back with some updated UI fields - #Tickets-To-Create  #Tickets 
3. Very important - https://signalk.atlassian.net/browse/SSG-105?focusedCommentId=11481


# Required tutorial updates
1. Finding/sharing your discoveries, as well as for locations, viewing where you can go
2. Annotation behaviour

#Sprint-Planning 
1. What is every page, structure, route, project, etc required from Miro?
2. I'm sort of comfortable with stating that #zoodex-upload or general #uploads #upload need to be integrated as missions fairly soon...so in this upcoming sprint
3. Maybe we can use the `BasePlate` component structure to completely overhaul how structures and internal modals are composed
4. We'll need to add scope for adding new levels to the #PlanetGenerator and allowing these changes to interface with the #Biomes / #Terrarium customisation
5. Sharing the #PlanetGenerator with structures is a high concern -> fits into #SSG-96 possibly?
6. #CloudspottingOnMars shapes and #ActiveAsteroids...


# Post-SSG-110
#SSG-110 
1. Old greenhouse/plant cards
2. [[SSG-110 - Construction & Collaboration]]
3. Should simple post cards show the structures, and how about in the downloaded images - #SSG-117 #SSG-112 

I think that having a biomass value on #Earth that allows you to go through more things works, maybe the first discriminator is that users have a set number of stations they can build. So #biomass is the objective "currency", then

# Post-SSG-118
1. At some point soon, storms & other events need to come into play...


# #SSM-150
1. Precipitation events - any other proposals for variables?
	1. With richer inputs rather than just one of 3 options