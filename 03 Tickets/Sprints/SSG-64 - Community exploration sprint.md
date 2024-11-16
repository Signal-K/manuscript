---
sticker: lucide//cloud-sun-rain
tags:
  - SSG-63
  - Missions
  - Chapter-1
  - Chapter-3
  - Chapter-2
  - Chapters
  - SSG-64
---
Every sprint document will have a list of #Tickets , #Tickets-To-Create , #Bugs , #Missions , Working trees, and other notes.

First up,

# SSG-64 - Community exploration
The goal for this week's sprint will be as follows:
1. Allow users to follow & unlock all missions for all pathways, as well as structures
2. Fix the bugs & implement user suggestions/feedback as described below
3. #Chapter-2  -> Allow users to begin some travel and joint-exploration & construction on other locations (and prepare flow for exploring exoplanets & disks in #Chapter-3 )
	1. This will include #Mining , #RoversS / #Automatons and changing #CommunityStations to be more intuitive and based on these missions, which will build off the main/initial classification-type missions (essentially into more creative and sandboxy, collaborative missions/steps)
	2. [[Locations for mission groups]] && [["The Create Sprint" - fix & retrospective]]
4. Improve #Starnet , including fixing issues with classification output, voting (I think we should have a record of user votes in a new table), and add a proper flow for users voting on #planetTypes and validity. Also improve how user suggestions and uploads are integrated into structures)
5. At a minimum, determine a plan for #annotations integration
6. Integrate #SSP-15 / #SSP-31 into the fe flow

# Tickets
> So we strip it all back, fix the mobile & responsiveness, propose new missions and content, inc. #Starnet , let's get it done, draw the design for the toolbar and the flow for the uploads & screenshots, and we'll be good

Create a ticket SSG to remove `StructureInfo` - this should be redesigned and included directly inside the rest of the structure.

I think that we should update the flask/python scripts so that the `anomalies/avatar_url` is also included...and updated
## Ongoing tickets
Ability to view the anomaly from the #starnet in your structure - anomalies will have a structure, we open that and then the view (e.g. `Transiting` function).

SSM-21 - share screenshots, post form - new `posts` table
[SSM-55](https://signalk.atlassian.net/browse/SSM-55) - overhaul the "add" item/structure, add to the "unplaced" section in the grid building, then for SSG-53; add properties & modal to grid
[SSM-57](https://signalk.atlassian.net/browse/SSM-57) - add research UI, quick panel
<details> <summary>SSM-54 - Community stations will be used for establishing settlements on other planets while we don't have the full customisation features yet. </summary> Community stations will allow users to unlock new projects & data (under the “Projects” header), find dedicated missions for projects (e.g. “find x anomaly type” or “place y anomaly type”, “map this terrain”). Mining will also be a part of the community stations, showing maps, etc.
 Update the pathway/mission list so that the new missions will introduce the user to the different mechanics, help them start building and bring the sharing network into the mission requirements </details>
 [SSC-34](https://signalk.atlassian.net/browse/SSC-34) - Where do physics labs come in? Maybe users need to discover and create landmarks for this...we need to have a community mission/anomaly expedition for each project, maybe this is where [terraforming & simulation comes into play](https://signalk.atlassian.net/browse/SSC-34?focusedCommentId=11319) . Users could be able to add their own media to anomalies, which [would include the post cards and customisations made](https://signalk.atlassian.net/browse/SSP-15?focusedCommentId=11320).

## New tickets
### #SSM-57  - Research integration & UI update
Firstly, the content should be updated so each module is more clearly defined. Secondly, they should be separated by structure, allowing for structures to be researched, constructed, and then have their modules researched. I don't think we need to strictly define the location blockers simply because everyone is remaining on #new-Earth #Earth . 
Finally, we need to improve the research flow with the new UI
#SSM-57 

I think I'll create a new page first, and this will then be brought in as an overlay/view

# #Bugs 
I have identified that projects/missions appear to be available on structures (at least for the #Telescope ) regardless of research state. I think a key goal for the upcoming sprint will be to make the #Structure #Configuration dynamic and fix this issue, additionally integrate it with #SSG-53 (the structure grid view)

Making the classification should engineer a confirmation message and then return to the first modal view or the main structure view.

The structure close field should also be changed to ensure that all methods of exiting/closing the structure allow it to be re-opened

Change the "Research a new module" mission to be based on whether the user has a structure with at least two modules activated, or at least two structures with one module activated.

We need to add a mission to find the deposits first (based on survey probes), and integrate "Rover A"/"Rover B" into the actual inventory. For now, these two ^^ missions have been commented out.

"Table entry" from missions no longer seems to be working. So let's get to work to fix that.

~~The (expanded) mission guide is not scrollable on mobile.~~ - #SSM-60 

Convert the v0.dev components e.g. weather from `jsx` to `tsx`

## Other changes
I also believe we either need to change the behaviour of the (inner) structure modal dimensions, or to increase the size of the tutorial & classification components (especially on desktop!)

Perhaps there should be a field in the annotation/text area for outliers or key points (whether in graphs or otherwise), so that we don't have to add an entire llm network to decode users' suggestions.

Perhaps, we should add a feature to move structures from other planets/locations to #new-Earth 

Perhaps we can have the asteroids & other objects discovered seenx in the night sky area. Perhaps these things could be generated via Flask/Jupyter simulations

I also think we should rename #zoodex to #biodome or someth for all frontend interactions/mentions

Replace `MissionsForStructure` with a `guide` view inside #Structures & #CommunityStations 
# Other notes
[[05 November 2024]]


# Bugs (end of sprint)
1. #SSM-57 - showing research for structures that don't exist for the user