---
connie-publish: true
sticker: lucide//database
connie-page-id: "28606513"
tags:
  - Editing
---

Everything here is a task or update we need to make that hasn't been passed into a specific sprint or ticket yet. Make sure to accurately mark the relevant obsidian/confluence pages as well

See more at [[Frontend timeline]] & [[Suggestions from user demos]] 

# Game items
## Structures
* Don't show all structures in the overlay area on index route
	* [[Structure Modals]] & [[00 Archive/Test/Structures]]
	* [Jira](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-86)
		We need to determine the setup of structures, e.g. does the camera receiver station pair up with the telescopes or with the automaton upgrade station? Is the MT part of the [telescope] array or something else?
* Prevent duplicate structure creation
	* [[00 Archive/Test/Structures]]
	* [Jira](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-84) 
* Mining station should show your inventory, and deposit information (from automatons)
	* It should also show the context based on what missions are available (maybe the user selects something they want to do and we then provide tooltips instructing them what to do next)
* Structure tech tree
* I’m wondering if we should move things like the launchpad/spacecraft into automaton, structure sections or somewhere else entirely?
	* [Jira](https://signalk.atlassian.net/browse/SGV2-90?focusedCommentId=10487)

## Crafting
* Single row for every item type
	* [[First Mission Group - SGV2-40 Retrospective]]
* Add discriminator to `<CraftStructure` that determines the crafting requirements from `/api/gameplay/inventory/route.ts` 
* Crafting grid (to add on to the inventory component)
	* [[UI Cleanup sprint]]

## Automatons
* Restrictions for what is available for the user to collect
* Improve/restructure the Automaton Upgrade Structure Modal, list everything together...
* Improve AUS (31) to have dedicated slots for speed and storage, make storage actionable

## Mining
1. Set up resource deposits
	1. Sort of relies on sectors, though, right?

## Planets
* It would be cool to have some sort of galactic map (or, bring it back...)
	* [[Planets to add]]
	* We'd also need to provide the user with a list of planets they have previously visited (i.e. "own"). 
		* I got the idea when thinking about the order that planets would be in
We need to give something for the users to aim for if they decide to stick with their first planet

# Page layout
## Utilities
There should be an overlay area that shows the utilities options (e.g. deleting superfluous minerals at the end of a turn/mission. Note that this is purely for debugging as I'm hoping to improve the organisation of the in-game items)

Maybe the utilities section could be where the tutorial/tooltips are located?

## Extra buttons
* Feed
* Mission list?
* Inventory?

## Styling bugs
* Fix the PickYourPlanet component so it doesn't dramatically warp the height of the display

# Classifications
*  Update the `classifications` table so that we can specify the anomaly type being classified
	* [[First Mission Group - SGV2-40 Retrospective]]
	* [[Classifications]]
* The rich-text editor should be added back
	* [[First Mission Group - SGV2-40 Retrospective]]
* Freeform text is a privilege  for verified classifiers, checksums are the default
* Mining options are dependant on the classifications
* Can we link in with Zooniverse talk?
	  [[Planets to add]]

# Users/Profiles
* Profile picture -> https://www.figma.com/design/3FmAUZtk0T9bGGTiMFbQjo/Config-Virtual-Badge-Template-2024-(Community)?node-id=0-1&t=fKjoSWf6R0duQkbR-0

# To update when we introduce sectors
* Fuel harvester structure mechanics will need to be changed so they are deployed onto a sector with a fuel deposit (or we allow users to craft fuel)
	* The launchpad can be moved (just like with any structure) between sectors, but if the launchpad is not on a sector with a fuel deposit, it can only be fed with crafted fuel



Life "energy" generates real animal tagging stuff