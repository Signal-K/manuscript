---
sticker: lucide//droplets
---
# Working tree
1. #SSG-65 
2. #SSM-60 
3. #SSG-66

I think #Mining will require a significant UI overhaul. And let's determine which `v0.dev` components are relevant this sprint and match them up w/ their tickets


# 13 November 2024
## Goals
1. ~~Determine how research will be linked with the new onboarding scope~~
	1. The Mission Guide can sort of be a control panel guide as well - add a button to open the #Research view
	2. We show #Structure > #Modules , user has to create the #Structure and then #Research the #Modules 
	3. New #Structures created in #Research #View will have an identifier in the `inventory.configuration` that marks them as such. For the #Research #Missions to be complete, we have to have one of these #Structure plus either two #Structures with 1 #Modules #Research or one #Structure with two+ #Research #Modules 
	4. Do a test to make sure that these #Missions are correctly stored on the #frontend 
2. Get anomaly cards combined with post cards - SSM-21
	1. Each #PostCards is based on a `Classification` made on an #Anomaly. We then show linked #Anomalies and will later allow the user to customise these (including #Icons & #Paint / other customisations/configurations). Will allow for #Voting & #Comments 
	2. Users can update the `classifications.classificationConfiguration` if they own it, this will mainly adjust the bg colour and then will follow the above #Instructions. If the user doesn't own it, it will just appear a solid white #background.
	3. When users share a #PostCards , they distribute a copy of the `PostCardSingle` component with the configuration inside another `PostCardSingle`
	4. #Comments on #PostCards will mention if they were commenting on the original or modified #Classification card.
	In short, we need to allow for limited customisation, correctly show `ClassificationOptions` and allow for sharing & commenting, voting, show child #anomalies and have these feed back into the #Structure and #views 
3. ~~Mission & voting on #uploads  & types ^a56a3a~~
	1. So get the new mission list as an OOO, go over w/ Rhys/Asher about how we lay it out (with Rhys's notes) - on tram
	2. Another #View or #Modal that is in the #Missions #field-guide #guide - update `Guide` to allow for this
	3. We'll have a list of #Anomalies that have had #Classifications made, we'll need users to vote - so we can make a filter to show entities/entries that have not been voted on sufficiently, we can also have a page that shows your #Anomalies in this category.
	4~~. We'll need to have a separate table for #Voting so that we can determine if users are voting on their own #classification or someone else's~~

		1. ~~Show planets, then show the vote functionality - merge `DiscoveryCard` w/ `PostCardSingle`~~
1. Determine where these post cards fit into the flow, maybe in the inventory
	1. Each structure can also show discovered #Anomalies , so this will show the #PostCards obviously
	2. The user is invited to create a vote on another #classification , once they do this they'll be directed to their " #Anomaly #Inventory " which will show entries in #classifications, #uploads & #comments  tables that they are "watching".    [[Structure UI]]
	3. After thinking about it a little bit, I've decided that each #Structure will have an #AllDiscoveries action button.
## Working tree
1. #SSC-38 
2. ~~#SSG-67~~ 
3. #SSM-57 

hence below nirvana total mowing lullaby degrees nuisance occur ruling loudly eclipse biweekly silk rowboat rapid etched language trying goldfish criminal thwart pairing rally ruling

~~Finally, schedule all this, cross-reference with open tickets, and get to bed~~

The current mission list consists of:
1. Complete a [structure] mission using your #Structure 
2. Get this mission list, then determine how the above 4 tickets/goals fit in...to get the level of customisation/create we want. After bugs...and how it fits into the #views e.g. #Mining 
	1. Test out `components/Projects/(classifications)/Collections`

Fix #SSG-67 - why is one #Astronomer #Mission showing up for all users?

# 14 November 2024
1. ~~Uh oh, it appears that the guide is fucked again - missions aren't being displayed/separated anymore~~
Maybe a new layout for views that go over the background?

And obviously the new structures....cleaning up...
1. Ticket with table entries - `uploads`?
2. Look at overhauling the `uploads` table
Missions should be pulled from a flask API so we don't need to do a merge into `signal-k/client:main` every time. Same with `/api/gameplay/inventory`...

[[#^a56a3a]]

Maybe we can create a new minimal background for the #Starnet along with the shapes

1. #SSG-59
2. #SSC-39 
3. #SSM-61, but for #uploads as well - ask users to add to an #Anomaly or #AnomalyType . If it gets 5 likes, we add to #Anomalies table.

Finally, summarise all of this & #SSG-64 #NovemberMissionList into an OOO, tickets, and determine the #Create elements week-by-week. 
# 15 November 2024
If we make good progress on the #Active-Sprint , we'll buy a new notebook, maybe the Moleskine; and a new pencil case, paperclips

1. #SSM-62 - add this into the flow, allow users to nominate anomalies or groups...

How do we show different #views in #Anomalies ? I think we should create post cards that show a preview of planets (like sharing the #Structure #View ).

Fix the bug around `Guide` not showing completed missions based on table entry.
Missions, insert everything and create mission for terrain or other generator.

Closing:
1. #SSM-57 
	1. Note - we still need to add the modal to the guide
	2. Note 2 - we still need to add the researched state to the mission

Finish off these tickets

# 16 November 2024
1. ~~Handle migration Balwyn > PM~~
2. Draw cards & layout for mining, cloud/map scene
3. Integrate these missions
4. Component/structure in `Guide` to open?

Working tree:
1. #SSM-63

Designs/Inspiration
1. Let's try and find some new designs for the #Pokedex #upload form

At cafe -
1. Plan missions
2. Components in `Guide` - #SSM-63 
3. ~~Determine exports~~
4. Add comment form to `AllClassifications`
5. Design post cards to show `anomalies.configuration`, `classifications.classificationConfiguration` and fields from `uploads`, `comments`...and a big avatar. Users can add a #Comments that will be structured like a CLI that will temporarily be an "early"/pretend configurator/generator.
6. Send off #Missions for Rhys, Nathan etc to review
7. Determine closing sprint requirements
8. Get some ideas around updates to #StarnetLayout
9. ~~Summarise this & plan out next sprint, plus tomorrow's cafes~~

The next set of #Missions will be about mapping #Earth 
1. Find #Clouds, trees or other landmarks (for #biologists ) for where #Anomalies will go
2. #Meteorologists will travel to other #Solar-System #Planets to map #Clouds and other #Landmarks to find mining or meteorological sites - will link up w/ ^ #biologists missions
3. #Astronomer will look at #Satellite & #RoverPhotos to identify other landmarks

Users can go #Mining off-world and then we'll bring them to #Earth again for resource production.
We'll adjust #PostCards so that users can see their #Anomalies - these will show either #Landmarks or #Planets (location/setting #Anomalies ) with a list of #childAnomalies (these child components will be separate component mappings and therefore have customisation parameters and icons.). 
Then we need to have a #PhysicsLab mission/project.
Allow users to #Share their #Cards . These will include a map & #Weather-Map - leading into customisation.
## Ideas for the next sprint
Users will have a location map that shows planet candidates that have been vetted, requiring further investigation, and new locations/journeys for expeditions (e.g. #Mars).  [[#^a56a3a]]
As well as creating the community missions / #Expeditions
Mining mission, topography

Updates/Changes -
1. All structures will have an action item to show #AllDiscoveries 
2. [[SSG-64 - Community exploration sprint]] -> we will add a `posts` table that will allow users to post directly to #Starnet, it can include #comments, #Classifications , #votes, and anything else that can be stored in a #Tables 
3. Grid system - finally
4. Dedicated #Research missions
5. For #SSP-31, let's get a dataset that is relevant to each #anomalysets and cross-reference with #ClassificationOptions
6. #SSG-66 - new design
7. #SSG-65 - overhaul #Properties with new #StructureConfigs pages
8. Update #SSM-40 so that users can add additional fields - #Surveyor (this will be a precursor to #childAnomalies )

[SSM-57](https://signalk.atlassian.net/browse/SSM-57) - add research UI, quick panel
<details> <summary>SSM-54 - Community stations will be used for establishing settlements on other planets while we don't have the full customisation features yet. </summary> Community stations will allow users to unlock new projects & data (under the “Projects” header), find dedicated missions for projects (e.g. “find x anomaly type” or “place y anomaly type”, “map this terrain”). Mining will also be a part of the community stations, showing maps, etc.
 Update the pathway/mission list so that the new missions will introduce the user to the different mechanics, help them start building and bring the sharing network into the mission requirements </details>
 [SSC-34](https://signalk.atlassian.net/browse/SSC-34) - Where do physics labs come in? Maybe users need to discover and create landmarks for this...we need to have a community mission/anomaly expedition for each project, maybe this is where [terraforming & simulation comes into play](https://signalk.atlassian.net/browse/SSC-34?focusedCommentId=11319) . Users could be able to add their own media to anomalies, which [would include the post cards and customisations made](https://signalk.atlassian.net/browse/SSP-15?focusedCommentId=11320).


# 17 November 2024
While at coffee:
1. Design for missions & views, missions for each view and pathway -> #SSP-33 
2. Review of belows:
3. Review (design and otherwise) of aboves
4. Improve #uploads flow & dedicated missions, integrate into #Surveyor & #votes 

5. #SSG-66 - design for #StructureInfo
6. #SSM-63 - dedicated "More" button rather than just clicking on the entire `RenderMission`
7. Determine scope for [#SSC-40 ](https://signalk.atlassian.net/browse/SSC-30) 

Do a review of the #Create-Sprint and the original goals
Organise #Tickets for this new sprint

> Broad goal - users can travel again, and there's a clear mission group across expeditions and exoplanet colonisation. Clear mission goals for each pathway and structure on different location types. Increased collaboration, communication, item sharing, consensus & surveyor (introduction through missions) and post cards, sharing to `posts` table (new) and external networks. New design for `StarnetLayout`

It would probably also be a good idea to go through each defined #MissionGroup in #Jira and make any appropriate updates