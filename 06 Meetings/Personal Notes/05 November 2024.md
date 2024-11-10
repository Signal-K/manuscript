---
sticker: lucide//copy
---
1. ~~Onboarding window~~
2. ~~Instruction/dialogue window~~
3. And obviously the Starnet configuration
4. Layout & OOO for mining, atmosphere view (expanding out of the sections in the structure view)

# 06 November 2024
1. ~~Final missions~~
2. Invite to Starnet
3. Design & drawing of my configuration (w/ alien, plus config pattern & OOO for eventual full integration. Includes description for each step/component and icon/sub-terrarium). 

All in all, if we have a way to do every action and project, and it's relatively straightforward, that's a win. `user_anomalies` as assets...

To draw - upload flow for adding custom content, and the method to vet other user's/users' uploads
# 08 November 2024
Clean up the Jira   
1. ~~Move everything to a new Create backlog~~
2. ~~Bring forward tickets that have been completed and create duplicates/pre-cursors for ones in-progress that have been completed for this new #Chapter-1~~ 
3. Create a mission that identifies vetting/consensus and inventory items, not just entries in `missions` table. Add some items other than fuel in the mining scene. Add a "locked"/coming-soon section for missions and unlockables, maybe some achievements or something. Add mining and sharing concrete missions. Then add an icon export, from structure that would later open up terrarium representation, and get feedback on that flow.
4. Add mining w/ topography, weather, so users need to make a classification in the mining scene to add deposits.
5. Close branch/sprint
Fix mobile interface for new pathway

The new #Create-Sprint will be based on the new tickets & creative functionality that builds from the missions and rich-data introduced in this new #Chapter-1 implementation


# 09 November 2024
1. Release notes
2. New images/assets, maybe some audio
3. Close PR & continue create stuff, new missions, share

Working tree - 
1. ~~SSM-46~~
2. ~~SSG-63~~
3. ~~SSM-41~~
4. ~~SSM-55~~
Let's do [SSG-59](https://signalk.atlassian.net/browse/SSG-59) in research

Add planet verification mission in `guide.tsx`

# 10 November 2024
1. After fixing the mobile view, I'm going to do a walk through on new accounts on both mobile & desktop, ensure that everything is clear and visible for both viewports
2. After this, I will create the release notes, identify any missing missions, and prepare for the integration of `SSG-58` branch, the goals for the next release & sprint [tickets], and finally move the notes into the correct directories here in obsidian/make.md 
# Extracting key notes
What we're finding:
[[SSC-34 -> New Projects]]-> 
1. Everything is done on #Earth , users can go to other planets to set up community data sources (essentially community stations) and structures for resource manipulation. Then users can do colonisation with the original structure set - there would be some other multiplier/reward for users to say use a #Telescope on #Mars or their #newplanet
Multi-tenancy for #Earth 

[[Chapter 3 & 4 Mission List]]:
1. #Weather-Map is based on user #Classifications 
2. Sky & orbital #map view
> So the implementation of these views and models is paramount for the success/merging of this sprint. Okay.


[[SSG-61-> Combining automaton & surface structure containers]]
1. Improve dialogue & mission window size
So community stations will allow:
1. Anomalies and items to be transferred
2. List of missions or next steps for the current location. Ability to research new projects, missions. Upload content
3. Early customisation of anomalies
Users will need to work together and wait on other users or themselves to complete other pathways. So community stations will serve as a reference for content or items/anomalies that are missing or research that needs to be performed. E.g. once a new system is found in #Disk-Detective , users can browse for these in their #Structures , but will need to find a matching #PlanetHunter anomaly too. A planet will need to be mapped before mines can be placed on it; this would require clouds to be discovered and matched.
# Next steps
Ability to view the anomaly from the #starnet in your structure - anomalies will have a structure, we open that and then the view (e.g. `Transiting` function).

SSM-21 - share screenshots, post form - new `posts` table
[SSM-55](https://signalk.atlassian.net/browse/SSM-55) - overhaul the "add" item/structure, add to the "unplaced" section in the grid building, then for SSG-53; add properties & modal to grid
[SSM-57](https://signalk.atlassian.net/browse/SSM-57) - add research UI, quick panel
<details> <summary>SSM-54 - Community stations will be used for establishing settlements on other planets while we don't have the full customisation features yet. </summary> Community stations will allow users to unlock new projects & data (under the “Projects” header), find dedicated missions for projects (e.g. “find x anomaly type” or “place y anomaly type”, “map this terrain”). Mining will also be a part of the community stations, showing maps, etc.
 Update the pathway/mission list so that the new missions will introduce the user to the different mechanics, help them start building and bring the sharing network into the mission requirements </details>
 [SSC-34](https://signalk.atlassian.net/browse/SSC-34) - Where do physics labs come in? Maybe users need to discover and create landmarks for this...we need to have a community mission/anomaly expedition for each project, maybe this is where [terraforming & simulation comes into play](https://signalk.atlassian.net/browse/SSC-34?focusedCommentId=11319) . Users could be able to add their own media to anomalies, which [would include the post cards and customisations made](https://signalk.atlassian.net/browse/SSP-15?focusedCommentId=11320).

> So we strip it all back, fix the mobile & responsiveness, propose new missions and content, inc. #Starnet , let's get it done, draw the design for the toolbar and the flow for the uploads & screenshots, and we'll be good

## #Bugs
I have identified that projects/missions appear to be available on structures (at least for the #Telescope ) regardless of research state. I think a key goal for the upcoming sprint will be to make the #Structure #Configuration dynamic and fix this issue, additionally integrate it with #SSG-53 (the structure grid view)

Making the classification should engineer a confirmation message and then return to the first modal view or the main structure view.

The structure close field should also be changed to ensure that all methods of exiting/closing the structure allow it to be re-opened

Change the "Research a new module" mission to be based on whether the user has a structure with at least two modules activated, or at least two structures with one module activated.

We need to add a mission to find the deposits first (based on survey probes), and integrate "Rover A"/"Rover B" into the actual inventory. For now, these two ^^ missions have been commented out.

"Table entry" from missions no longer seems to be working. So let's get to work to fix that.

## Changes/Suggestions
I also believe we either need to change the behaviour of the (inner) structure modal dimensions, or to increase the size of the tutorial & classification components (especially on desktop!)

Perhaps there should be a field in the annotation/text area for outliers or key points (whether in graphs or otherwise), so that we don't have to add an entire llm network to decode users' suggestions.