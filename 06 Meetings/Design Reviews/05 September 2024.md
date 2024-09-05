---
sticker: lucide//cloud-sun-rain
tags:
  - Meetings
  - Tickets
  - Chapter-1
  - Sprint-Planning
  - Chapter-2
  - Tutorial
share: "true"
---
Continuing on from [[03 September 2024|03 September 2024]]

## Tasks to go through
1. What [[Tickets|Tickets]] (currently in `SGV2` board) are the priority, which ones (if any) can we move back into other sprints?
	1. This is probably for me
2. Go through [[Tickets|Tickets]] and [[03 Tickets|03 Tickets]] for anything that hasn't been covered in an existing ticket, or [[Bug Report|Bug Report]]. Synthesise everything here into actionable tasks, and put into buckets based on order (e.g. weeks and chapters)
	1. This is probably for me to strip back, and then hand over to Fred
3. Get a full picture (from the micro-level) of [[Chapter 1 epic|Chapter 1 epic]] [[01 Chapter 1|01 Chapter 1]] , all steps, high-level component architecture
	1. Essentially what interactions will the user be doing
	2. Update - Fred will put together his thoughts on #Chapter-1  from start-to-finish including terraforming, modules, creativity, postcards/terrariums, etc
4. Agree to layouts and determine what take-home tasks are required (visuals/assets)
	1. I'll put together a list of current components and Fred will look through and help design the layout (breadboard/wireframe)
5. Create timeline for [[Automations & Pipelines|Automations & Pipelines]] & [[Marketplace & Exclusives|Marketplace & Exclusives]], what will occur early game?
	1. ... #terraforming sort of solves this question
6. Narrative lore e.g. starting planet, outposts, etc
	1. To discuss on Saturday
7. Discussion around #factions
	1. To discuss on Saturday
8. Determine requirements for research structure, mechanics, and how research points are rewarded
9. Find (maybe off-Zooniverse) plant/biomass modules to integrate
10. Review "Urgent" tickets in [[Tickets|Tickets]]
## Questions for meeting
1. How do we go about creating structure designs that fit coherently (responsively) onto the background (without looking just like 2d images on top of a 2d background)
2. What (if any [other than the basic]) graphs should we have available for #Chapter-1  [[Finding planet candidates|Finding planet candidates]]
	1. How should planet groups be organised from a #Narrative perspective e.g. are candidates initially discovered by "central command" and then distributed to users? Is there a way we can create a pipeline for adding our own telescope data :P
3. How do we store the user's #zoodex mission (first), or does everyone start off with the same animal type? Or they choose their favourite animal (of 3) - but how is that stored db-side? #Database 
4. "Interacting with [alien] life" as a research ticket?
5. "Simulation engine" for affecting Earth-based life - what is the actionable return via classifications we can provide?
6. Limit for terraforming in #Chapter-1 
7. How do we implement [[Automaton - Rover configuration|Automaton - Rover configuration]] upgrades in #Chapter-1 ?
8. List of experiments, how we can simulate these
	1. Just have a number of Unity & Godot modules (since most of the interaction from our users will be through the frontend)

# Outcomes
## (Please insert into correct files l8r)
1. Phase folding will exist as an upgrade to telescopes, users will input the period and can then attach the output file into their classification\
2. No planet sets (apart from special interest and base candidates), the planets available at chapter x are available at chapter 1 to classify
3. Based on the planet {type}, they get a choice of 1 of 3 #zoodex 
	1. It's up to me to figure out how to store this without creating more db columns (long-term)
	2. Short-term: 3 options, user is assigned 1 based on their {planetType}
4. Research ticket for interacting/visualisation alien life (Fred will come up with proper wording for this [[Tickets|Tickets]] #Tickets )
5. Fred & I will ponder some more about the simulation engine
	1. The return is all the data together?
6. Terraforming reasons: 
	1. Create/customise your anomalies/settings/entities
	2. Observe alien life and Earth life behaviour, improve population, etc
	3. Identify & change landscape to strip back/increase (speed) of transitions e.g. remove ice to find craters, fossils, etc
	4. To-do -> base structures including habitation domes..
	5. Limit (for #Chapter-1 ):
		1. Upgrade to the rover to terraform and customise immediate sectors
7. We're going with tools, first upgrade/building type (especially in #Chapter-1 ) is free e.g. you just need to research it, no complex crafting required e.g. "Power drill" is just researchable, and then you just apply it
	1. Create a cross-section/schematic component for the #Automatons / #RoversS that shows the upgrades/toolchains
8. I think we'll just have a limited engine/"if then" statements, don't think there's any significant issues with mixing Godot/Unity with the #frontend

Go back to #Onboarding for the narrative at some point, "who left these structures on these planets". "Starnet" asks you to verify the existence of planet [candidates] sent by a mysterious alien race

We'll have a romantic dinner meeting at 7pm on Saturday