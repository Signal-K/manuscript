---
tags:
  - Missions
  - Chapters
  - Transit
sticker: emoji//1faf0
Jira:
  - SSG-58
  - SSG-50
---
# Chapter-1
The goal for #Chapter-1 will still be the same - Introduce the user to structures, classifications & construction. If we treat it a little bit more like a "base building game", we could start the player on #Earth , and give them the option to pick the first object to study, and we give them a matching structure. They are then shown how to research missions on that structure and then participate in the mission they pick. So, users are sort of choosing "Pokemon" characters in the form of structures. 
I will create a new entity in `anomalies` table for the "new #Earth" where users will be able to start fresh (id: 30), and "old #Earth" will allow users to participate in the larger mission flow & sandbox environment.

## Order of operations
1. User registers
2. Player appears on #Earth  (id: 30) - #new-Earth 
3. Player is asked which scientific discipline they'd like to investigate, and then is given a #Structure to place on #Earth 
	1. The user is shown the grid to place the structure onto, we have a tutorial component if the user hasn't placed any items into a slot on their `profiles.activePlanet` value
5. The player is invited to click onto their new #Structure and complete the tutorial mission for the module they researched
6. The player is then informed that they can participate in new projects/modules with new structures at any time, as well as being directed to the "mission page" on #Starnet to follow the previous/future pathway on #old-Earth
7. User is invited to add data (and maybe compare it to a previous classification they've made?)

~~So we'll have a speech bubble component/character that will show up for Steps 3.1, 5, 6...just need to come up with a method for dialogue distribution that isn't solely based on `missions` not completed. Maybe we have a global missions pathway & onboarding component for each step/chapter?~~

Let's also take a look at all the features missing, available and close (e.g. views, mining, etc)...how do we simplify things like the toolbars?

For research:
4. The player then selects the module they'd like to investigate from that structure, and by selecting the module, will "research" it for the structure. 

Community stations will be visible as part of the #Structure-Grid, allowing users to see available projects, missions, anomalies & requests. However, I think I'll leave these empty for now.

Users can share a configuration map of their location on #Earth , as well as all their discoveries, in #Starnet . We'll generate a view of #Earth based on their discoveries and construction, this can be recreated for other location anomalies.

> Users need to be able to perform all classifications & projects by the end of #Chapter-1 

Players will be given an incentive or "reason" to return daily - new data points, the first classification performed each day could give a reward? Then you send your automatons & probes out to collect more information, which is then "beamed" to your structures. Structures will run out of power and energy and will need to be recharged. 

Uploading new data into the feed (and specifying the project) will allow structures to recharge, however, for now this will just be added to `uploads` table and won't have any objective frontend/end-user response. 

Users who comment or vote on an anomaly can have a "fork" of that anomaly sent to their "terrarium/collection". 

We can then do weekly exports, give users feedback on their classifications and simulation output...

Starnet will be where users can send their discoveries to, get votes, etc. Potentially anomalies can't be used until they've been vetted, or we tweak the multiplier value. Maybe anomalies that have been vetted can be placed anywhere? Either way, we need to get a pipeline for #upload s and #Starnet into the mission log here for #Chapter-1 . Sharing your discoveries, resource manipulation & of course the discoveries themselves seems like a good place to leave this, and if we have the upload mechanic that leads into the other #Create elements, I'm a happy camper.

Potentially surface analysis & other projects are some ideas for the new planets/locations in community missions? For now I'll consider these to be #Chapter-2 projects but I might insert them into the onboarding for the new #Chapter-1 ...

Missions will lead into mining, along with probing...deposits are created from your discoveries (as well as other things created from...will later be customisable/malleable)
# Chapter-2
In #Chapter-2  we'll allow the user to discover new planets/location #Anomalies as well as travel #off-Earth for re source missions. We'll also allow them to upload their own data, eventually the uploaded data will be able to be combined with things like the terrain & weather generators, e.g. users can upload clouds, once they're classified & confirmed in #Starnet they can appear in the user's #views.

We'll start new location generating by asking users to go to the #Disk-Detective & #PlanetHunter  projects in their #Telescope structure. We need to come up with missions for #biologists & #Meteorologists related to this as well. 

We'll allow users to build launchpads & create different spacecraft.

Some starter expeditions will be a new exoplanet each week that users can visit to collect some fuel or other resource from. 

Maybe users will need to map planets/locations partially before they can visit them? Create landing sites, etc - these are other community structures/stations (items).

Don't forget to look at `planetType`s and `compatiblePlanetTypes` for #Data-Sources 

We'll create missions based on anomalies - starnet

# Chapter-3
In #Chapter-3 , we'll allow users to create terrain/topographic & cloud maps from previously classified projects. This will be copied by the #Biosphere feature and other views, eventually. Users will also be able to begin construction off-world and share anomalies around. Users of different types/skillsets will work together to create these landscapes (e.g. #Astronomer , #biologists #Meteorologists working together to create the planet maps & #Locations ). 

We'll need to implement a #bridge allowing users who did press ahead in #Chapter-1 to come back and merge all these data points/assets together.