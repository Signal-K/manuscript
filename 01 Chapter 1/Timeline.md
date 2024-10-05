---
sticker: lucide//messages-square
tags:
  - Chapter-1
  - Mechanics
  - Data-Sources
---
User picks what they'd like to do (module-wise), thxey are then given a structure that has enough "strength" for **1 classification** (tutorial). User is then asked if they want to continue (they'll have to collect some resources and build their base) or if they'd like to pick another focus

This then starts filling out the mission log

**[[05 Game Items/Structures/Structures|Structures]] should be created from the `ChapterOneOnboarding` component.** 

1. First [broken] classification
1. Mining
2. Refining/building & crafting [[Basic recipes]]
3. Next classifications
4. ...(loop of collecting resources)
n+1. Discovering next location to go to

Users will start off with a selection of animals they can start with (1 of 3), so we'll need to create 3 initial animal classifications for them.

After the user has made some additional classifications, they're prompted with their first community mission, which is to take a seed and a hardy animal species from an "Earth[-like] depot" and deploy it into the system. Monitoring rovers will keep an eye on it and return "periodic" images to the user (via Zooniverse data packets).

[[Citizen - Creative]]

Users will be able to return to planets/settings they've previously been based at

### Incentives for new planet discovery at the end of #Chapter-1 
Each chapter should introduce the user to new game mechanics and loops, and some planet candidates are better suited to this. #Chapter-2 will include a requirement to find different planet types for specific new classifications (however, users won't be required to do every classification and the requirements are relatively straightforward and open to interpretation, e.g. equilibrium temperature estimates vs "unaltered"/static temperature differences can lead to a different #Surveyor view of the #planet )

We should show the user what classifications are available in #Chapter-2 and the first part of Chapter 2 should be all about how to determine the base stats of the planet [candidate] using the #Surveyor module of the #Telescopes

## Minimal planet requirements
We need to get a full picture of a planet and its respective anomalies, anomalies are grouped by planet (both per-user and "globally"), so part of the long-term goal in subsequent chapters/community missions would be completing a data set, however in the early-game with #Chapters we will just stick with a percentage completion of a planet on its own.

Currently, the stats for planets include:
1. Candidacy/validity (legitimate)
2. Animal population (fictional/Earth-based)
3. Landscape/terrain type (Mars-based)
4. Weather (Mars/Earth-based, maybe other solar system entities)
5. Mineral population (partially fictional initially)
6. Planet stats (based on #Lightkurve ) -> to be included in Chapter 2

Down the line, we'll introduce a mechanic to base the candidate anomalies shown to our users on the planet stats ( #Surveyor #Telescopes module) and the overall discovery pattern, e.g. rover photos similar to those marked a certain way will be shown on planets with certain stats

Later, stats will include volcanic activity etc.

We will need to find some citizen science mechanics that work for populating [hypothetical] moons of planet candidates (especially gas giants), and populating gas giants in general.

For now, we can just say that users have to complete 2 different classification types/modules on a planet to finish #Chapter-1 
### [[Citizen - Creative]] components
#### Chapter 1
The user will be able to perform some limited terraforming once they've started populating the planet with some "earth-originating" life, it will be confined to the sectors immediately around your base. Maybe a planet/spherical component that spins around, gradually becoming more grass-filled (we'll have layers that can be toggled) over time? We can also zoom into the sector to see a "slice" of the planet?

Life is initially also confined to a set sector (maybe you have to classify life from Earth, find something that's interesting to you, and build a sanctuary) until terraforming expands.

Use case for farming? (this is before life is discovered)

Terraforming requires a few steps, e.g. understanding of planet, successful isolation of life, etc. Early terraforming will be strictly limited to landscaping...

Users will be given experiments as well, e.g. Miller-Urey [[Automations & Pipelines]]. 

Sectors will generate with some new life and other properties based on your classifications and creations/modifications (user-based procedural generation). [[Questions megadoc]] -> how to build up a big ball/graph of all discoveries and creations (and what's the utility beyond a symbolisation of "our world"?) (linked bodies of post cards - have [[Automations & Pipelines]] running between the cards/entities)