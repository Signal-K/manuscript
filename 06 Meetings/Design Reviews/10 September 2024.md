---
sticker: lucide//cloudy
tags:
  - Meetings
  - Retrospective
  - Active-Sprint
  - Design
  - Layout
---
Some key questions:
1. Does every structure require repairing in the starter mission group, or just the first one the user adjusts to completion?
	1. Repairing the first one "powers" all other ones -> only on first/starter planet
2. How do we organise mission groups?
	1. Probably more for me to determine
3. Where are we with Fred's deliverables, what should we re-allocate?
4. Overall number of estimated users; subsequent data points required (essentially how many points of each `anomalytype` do we expect our users to get through?)
5. Whatever was in `SGV2-132` ticket
6. Better profile **card** and **form** design
7. What do we think about the recipes in [[Starter recipes]]
	1. What other items will be required to be crafted in #Chapter-1 (look through dialogue requirements!)
	2. No crafting in #Chapter-1 , just repairing & researching
8. Is Capt'n Cosmos going to serve as the dialogue provider for everything in [[Chapter 1 epic]]?
	1. > Yes
9. Final conclusion - officially merge "Mining" & "Automaton" #Structures together?
	1. > Yes
10. What would a 'light' colour palette for "Novadust" look like?
11. What is the scene order after mining?
	1. > Repair their structure, then direct to Research structure
12. Inner modal options, action buttons for all structures
13. What else can we integrate API-wise, content for each module (up to #Chapter-2 )

To code during meeting (and create ticket):
1. Rover classification module under `SGV2-180`
2. Convert avatar in [[Header & Navigation]]into a circle, discuss with @Fred about optimal positioning
 
To walk through:
1. Jira format, Obsidian, Confluence

Improvements/deliverables required post-meeting:
5. Resolution issues with main background file
6. Scene order & layout across dialogue, mining, refining/crafting and all missions/structures
7. Scrolling issues in #Tickets for [[01 Onboarding]]
8. Other things we can add to the inner structure modal & overall planet landscape
	1. Maybe some stat icons, performance, etc?
9. Improved design for mining scene & inner components
	1. Including the Rover "action panel" aka GPS system, how does everything pop up?
10. Design & layout for (overall) inventory panel/component
11. List of planets the user has discovered (component)

Planets & modules have allocation requirements in #Chapter-2 
Mining -> simplified interface (one panel at a time)
Repair structure component - TO DO

Component/context to show if you've run out of data points to classify (for now)
Minimal requirements component, linked with `SGV2-186`.

### Questions for post-meeting
1. Should "saving" an image be done automatically or have a refresh/next button if users don't like the image (for now, we'll just have it save automatically to save time on state management) [[Rover photos]] 

Related:
[[Mission list]]
[[06 Meetings/Personal Notes/05 September 2024|05 September 2024]] && [[06 Meetings/Design Reviews/05 September 2024|05 September 2024]]
[[Timeline]] && [[Chapter 1 epic]]
[[Basic recipes]] && [[Starter recipes]]