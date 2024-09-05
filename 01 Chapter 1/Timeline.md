---
sticker: lucide//messages-square
tags:
  - Chapter-1
  - Mechanics
  - Data-Sources
---
User picks what they'd like to do (module-wise), they are then given a structure that has enough "strength" for **1 classification** (tutorial). User is then asked if they want to continue (they'll have to collect some resources and build their base) or if they'd like to pick another focus

This then starts filling out the mission log

**[[05 Game Items/Structures/Structures|Structures]] should be created from the `ChapterOneOnboarding` component.** 

1. First [broken] classification
1. Mining
2. Refining/building & crafting [[Basic recipes|Basic recipes]]
3. Next classifications
4. ...(loop of collecting resources)
n+1. Discovering next location to go to

Users will start off with a selection of animals they can start with (1 of 3), so we'll need to create 3 initial animal classifications for them.

After the user has made some additional classifications, they're prompted with their first community mission, which is to take a seed and a hardy animal species from an "Earth[-like] depot" and deploy it into the system. Monitoring rovers will keep an eye on it and return "periodic" images to the user (via Zooniverse data packets).

[[Citizen - Creative|Citizen - Creative]]

Users will be able to return to planets/settings they've previously been based at

### [[Citizen - Creative|Citizen - Creative]] components
#### Chapter 1
The user will be able to perform some limited terraforming once they've started populating the planet with some "earth-originating" life, it will be confined to the sectors immediately around your base. Maybe a planet/spherical component that spins around, gradually becoming more grass-filled (we'll have layers that can be toggled) over time? We can also zoom into the sector to see a "slice" of the planet?

Life is initially also confined to a set sector (maybe you have to classify life from Earth, find something that's interesting to you, and build a sanctuary) until terraforming expands.

Use case for farming? (this is before life is discovered)

Terraforming requires a few steps, e.g. understanding of planet, successful isolation of life, etc. Early terraforming will be strictly limited to landscaping...

Users will be given experiments as well, e.g. Miller-Urey [[Automations & Pipelines|Automations & Pipelines]]. 

Sectors will generate with some new life and other properties based on your classifications and creations/modifications (user-based procedural generation). [[Questions megadoc|Questions megadoc]] -> how to build up a big ball/graph of all discoveries and creations (and what's the utility beyond a symbolisation of "our world"?) (linked bodies of post cards - have [[Automations & Pipelines|Automations & Pipelines]] running between the cards/entities)