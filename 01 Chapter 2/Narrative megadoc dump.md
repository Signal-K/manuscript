---
banner: 00 Assets/icon.png
sticker: lucide//dna-off
tags:
  - Narrative
  - Chapters
  - Chapter-1
  - Chapter-2
  - Chapter-3
  - Content
---
Terraforming:
6. Terraforming reasons: 
	1. Create/customise your anomalies/settings/entities
	2. Observe alien life and Earth life behaviour, improve population, etc
	3. Identify & change landscape to strip back/increase (speed) of transitions e.g. remove ice to find craters, fossils, etc
	4. To-do -> base structures including habitation domes..
	5. Limit (for #Chapter-1 ):
		1. Upgrade to the rover to terraform and customise immediate sectors

Simulation engine?

1. Phase folding will exist as an upgrade to telescopes, users will input the period and can then attach the output file into their classification
2. No planet sets (apart from special interest and base candidates), the planets available at chapter x are available at chapter 1 to classify
3. Based on the planet {type}, they get a choice of 1 of 3 #zoodex 
	1. It's up to me to figure out how to store this without creating more db columns (long-term)
	2. Short-term: 3 options, user is assigned 1 based on their {planetType}

Go back to #Onboarding for the narrative at some point, "who left these structures on these planets". "Starnet" asks you to verify the existence of planet [candidates] sent by a mysterious alien race


# Narrative
After the user has made some additional classifications, they're prompted with their first community mission, which is to take a seed and a hardy animal species from an "Earth[-like] depot" and deploy it into the system. Monitoring rovers will keep an eye on it and return "periodic" images to the user (via Zooniverse data packets).

Each chapter should introduce the user to new game mechanics and loops, and some planet candidates are better suited to this. #Chapter-2 will include a requirement to find different planet types for specific new classifications (however, users won't be required to do every classification and the requirements are relatively straightforward and open to interpretation, e.g. equilibrium temperature estimates vs "unaltered"/static temperature differences can lead to a different #Surveyor view of the #planet )

We should show the user what classifications are available in #Chapter-2 and the first part of Chapter 2 should be all about how to determine the base stats of the planet [candidate] using the #Surveyor module of the #Telescopes

## Generator
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

[[Timeline]]
The user will be able to perform some limited terraforming once they've started populating the planet with some "earth-originating" life, it will be confined to the sectors immediately around your base. Maybe a planet/spherical component that spins around, gradually becoming more grass-filled (we'll have layers that can be toggled) over time? We can also zoom into the sector to see a "slice" of the planet?

Life is initially also confined to a set sector (maybe you have to classify life from Earth, find something that's interesting to you, and build a sanctuary) until terraforming expands.

Use case for farming? (this is before life is discovered)

Terraforming requires a few steps, e.g. understanding of planet, successful isolation of life, etc. Early terraforming will be strictly limited to landscaping...

Users will be given experiments as well, e.g. Miller-Urey [[Automations & Pipelines]]. 

Sectors will generate with some new life and other properties based on your classifications and creations/modifications (user-based procedural generation). [[Questions megadoc]] -> how to build up a big ball/graph of all discoveries and creations (and what's the utility beyond a symbolisation of "our world"?) (linked bodies of post cards - have [[Automations & Pipelines]] running between the cards/entities)