---
sticker: lucide//folder-search
tags:
  - Research
  - Structure
  - Learning
  - Classifications
  - Missions
  - Chapter-1
  - Chapter-2
  - Chapters
  - Mechanics
Jira:
  - SGV2-199
---
Down the line, users will be able to discover things like alien artifacts ( #Zooniverse tomes) etc, for now the research will be devoted strictly towards things like new structures and content.
Maybe vehicles & #Automatons configuration, too?

But anyway, this doc is just for items being researched/discovered by the user in #Chapter-1 

[[Chapter 1 Research scope]]

# #Classifications
## #Chapter-1 
1. LIDAR
	1. Clouds (from Mars)
2. Telescope
	1. New planet candidates (TESS)
3. #zoodex 
	1. Burrowing owls
	2. More content will be added to each chapter in subsequent versions, so burrowing owls may be joined with another object/Zooniverse project later
4. #APPEEARs (Automaton controller)
	1. #RoversS photos (from Perseverance roover) - help generate the landscape/terrain

The first one they choose (during the initial phase of [[01 Chapter 1]]) will not require any research, so we'll need to have an API route that keeps track of all structures the user has researched (maybe a database as well), the first structure the user chooses should be considered to have been "researched" just without the visual feedback that research was performed. We'll also need a new field in `profiles` called `research` that keeps track of their "experience", for every classification it adds `+1` to the `profiles.research` value, while researching new technology takes away `x` from `profiles.research`.

# #Chapter-2 
Ideas:
1. Volcanoes
2. #zoodex uploader - need to tie back into the #Narrative for where animals come from
	1. New #zoodex modules ( #read , not #upload / #Create  )
3. New planet types (better graphs, improving behaviour to tie into #Surveyor module)
4. Sunspots, solar activity
5. Is there something that ties into specific stars that isn't #Transit -related?
6. [Asteroid activity](https://www.zooniverse.org/projects/orionnau/active-asteroids/classify) 

In [[01 Chapter 2]] // [[02 Chapter 2]], users will be able to unlock the following technology:
1. Expansions to scope in #Telescope #Structure (and other #Structures the user has already unlocked)
2. New structures (e.g. #Volcanic activity)

Question ( [[What's left]] ) - when do we start introducing research tickets for [[Automaton - Rover configuration]]?

# #Automatons & Vehicles
1. Improved power (what minerals are being mined that will require a power upgrade?)
2. Improved speed, capacity

#Chapter-2 
1. Spaceship to travel to new planets? (see #Questions in [[12 September 2024]])