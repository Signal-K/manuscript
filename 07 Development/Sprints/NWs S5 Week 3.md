---
tags:
  - Active-Sprint
  - Star-Sailors
  - Sprints
  - Sprint-Planning
sticker: lucide//circle-equal
connie-publish: true
connie-page-id: "33292289"
---
Nights & Weekends (by `_buildspace`) Season 5, Week 3 sprint

Sprint goals are very clear:
> 1. Reduce load on server  
> 2. Implement new api frameworks  
> 3. Implement an earth-based citizen module  
> 4. Responsive layout & other UI improvements
> 5. Continue planning out pre-release stages  
> 6. Implement user feedback (where appropriate)


What isn't working?
1. No inventory block
2. No spaceship block
3. Refresh not working well
See [[Finished tutorials & unlimited data]] for more information

The big 6:
1. Improve classification process
	1. [[#^040856]]
	2. Add classification feed -> via action button
2. Add the pokedex module
	1. Add content to a local database
	2. AI can help with other classifications too
	3. Serves as a starting "engine" or backbone for the "collection"/portfolio concept
	4. Can build an api here - make standalone, add content, etc
3. Improve responsiveness & improve UI, implement feedback ^43038b
	1. Next-pwa does not need to be implemented yet as I already have it, so that's the main thing!
4. Reduce load on server with electric
	1. Don't necessarily need to get it all working, priority is features and UI. 
	2. The priority matrix for these backend tickets relates a lot to the number of users and the subsequent load on the server
5. More data -> fun sandbox ~~mechanics~~
	1. (Starting to plan out with [[PostCards (CPW-2)]])
6. Give users more to do after the tutorial - implement an open-ended mechanic/loop
	1. Also explain certain mechanics/improve context better for [[#^43038b]], e.g. mining information
	2. Maybe it would be a good time to implement the post card (`FCDB-2`?) ticket/feature request again...

Some other things (if we have time):
### To-Do
1. Cross-reference this planning document with the new Jira epics - in progress
2. Update layout to show off-world operations
3. Implement non-terrestrial features & layout (i.e. there's no surface to land on, so how do we display structures and how is the gameplay affected?)
4. Go back to the old v1 builds and look at the features/extra contex/nt we had for planets
5. [SGV2-64]: [Check what was removed](https://signalk.atlassian.net/browse/SGV2-64?focusedCommentId=10518) 

# Current bugs
1. Can't upload media to classification form
# Open tickets
## Star Sailors Visuals
**Clean minerals mechanic**
1. All items (apart from structures, utilities & automatons) will be accessible at any time to the user, no matter their location | This is a design mechanic based on Crashlands. It may be changed based on testing and user feedback
2. Update inventory so that we create a new row for every raw material in the user's `inventory` table, all additions/removals (crafting/receiving materials) will occur on that row. Therefore, tagging the `anomaly` will not be possible. 
3. I need to ensure that crafting removes items from the user's inventory ^e92a3f
4. Getting the user inventory sorted out so there's less rows I think is something that should be focused on and shouldn't be too hard - just set up an initialisation function for their inventory at a certain point, and all the raw materials will have a place to stay.
5. This just means we'll have to re-route the components that give users raw materials to *comment out* the `anomaly` field and put them into the row matching the `id` field

**Crafting update**
1. We should create an "action button" component that allows the user to craft things manually (i.e. without being prompted). This allows them to follow their own path after their first classification (confirming the legitimacy of their first planet will be required for every user, but if people don't feel like playing the space modules, they can just stay on their first planet forever and never need to worry about those modules/mechanics again)
2. [[#^e92a3f]] -> I have confirmed that the `<CraftStructure />` component does not deduct the original materials after crafting a structure, however obviously the new item is created and deployed/arranged successfully
3. For the deduction to occur, we have to use `<CreateStructureWithItemRequirementinfo craftingItemId={24} />` . However, this component does not show the required/remaining materials for crafting to occur.
4. That component does also reduce the materials by `x`, not the entire row; so this is a good sign

A note for crafting items & getting resources from automatons:
```tsx
const getAvailableItems = () => {

if (missionCompletionStatus.has(21)) {

return items;

} else if (missionCompletionStatus.has(8)) {

return items.filter(item => [11, 13, 15, 16].includes(item.id));

} else {

return items.filter(item => item.id === 11);

}

};
```

### Structure interactions
**Spaceship structure**
1. Will allow for more information when changing location/planet, rather than just "winging it" and changing your location
2. Allows you to select some structures/automatons to transport? - to implement later
Key question: what is the benefit of the spaceship vs just using the arrow keys? Or do we simply require a spaceship to use the arrow keys (like I think we currently do)?

## Star Sailors Backend
(Note: I may create a new board for this, or just put it all into `SGV2` board for now)

**Set up SMTP**
1. This will allow much more emails to be sent for things like authentication

**Change email confirmation message**
1. Can we move Supabase to our own domain?

**Files & Assets**
1. All images should be saved locally and hosted in the `public` directory. 

**Local db for user inventory**
Key questions: ^f8dea0
1. How do we implement this so that it can still "phone home" to the cloud database?
2. Will there be lags/exploits/issues where actions access a table in supabase/cloud db and the local db?

**Context management**
Key questions:
1. Is the hang time going to be improved by shifting some of the context/burden to [[#^f8dea0]]
2. What are the files/components causing the console errors? We can look there to see the order of operations and why `activePlanet` is being called as `undefined` , and possibly if this is just updating but still printing to the console

# Classifying planets
**Classification feed**
1. Simple feed that shows the anomaly, post/classification type, user, content, and a comment form (maybe a comment form)
2. Implement a tutorial block and explain to the user how mechanics like voting will be implemented in subsequent releases
3. This will also require the user to fill in their profile (hello, [[UserProfileFields.tsx]] [[Voidpet onbording experience]])

**Improve classifying process**
If we can give users the option to click buttons and have their classification post be "written" automatically, rather than them having to find the words themselves, it could fix the complexity issue brought up to me by some of our (very) early testers, and therefore help with user acquisition. ^040856

We need to improve the tutorial text/information - not just in the sidebar, but the actual classification process. 

Do we update the `classifications` table to use a `configuration` field for the multiple-choice, and support the full textual component there as well?

Users will be able to submit their classification either as a full-form post or with a multi-select:

> Choose one or more of the above, write some comments if you'd like

For lightcurves,
1. No dips at all
2. Repeating dips
3. Dips with similar size
4. Dips aligned to one side
5. etc
[[Python - Jupyter]]

For rover photos,
1. Craters
2. Rocks
3. Riverbeds/empty water"ways"
4. etc

For cloud photos - tbd