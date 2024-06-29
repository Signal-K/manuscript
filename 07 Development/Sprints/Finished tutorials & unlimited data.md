---
connie-publish: true
sticker: lucide//history
connie-page-id: "28672168"
tags:
  - Editing
---

Goal:
1. Finish tutorial. Now that we have no extra pages, everything needs to stay in the index route. Make the tutorial easy to follow, make sure that everything is explained to the user
2. Give the user a helpful guide (sort of like the PvZ almanac?) about every action, item and thing to do
3. API routes so that every current classification can be repeated
4. Pipeline (narrative-wise) for users to go from "completing" their first planet to going to other ones, including finishing "basePlanets" collection

Sectors will not be a part of this sprint.

# Ticket overview (Jira sprint)
## Open
Current open tickets:
~~1. Replace "clean minerals" mechanic~~
2. Update ~~mining structure~~ all resource-collection modals to show requirements
	1. We should probably show a selector tooltip (like on the automaton mining utility), allowing them to choose what they want to craft
	2. Additionally, we should show the context describing what they should do next (we need to determine how to describe what the user can do)
	3. Maybe after they classify the planet, we ask them what they want to classify, and then give them a pipeline after that
		1. This is a good step, however it would still be a good idea to have everything include the selector modal (rather than like now where we automatically show the requirements based on the mission/event completion status)
3. Initialise "edit mode"
~~4. Improve `{activePlanet}` context management~~
5. Feed component and overlay
6. Create spaceship structure
~~7. Prevent user from travelling without spaceship~~
~~8. New layout structure for "pick your planet" and other early missions~~
9. Plan out how we structure the narrative onboarding (semi-complete)
~~10. Improve rewards for missions~~

I think the current layout we have (that was finished at the end of the last sprint) is actually relatively easy to follow. Just one panel/column, three rows, with some information in the middle row. Obviously we need to tell our users what to do, but I don't see the need to go all in on the new layout yet. The focus should be on improving the feature-set while ensuring it's user friendly and accessible for our users. Therefore, we could probably get away with just making small modular adjustments to the layout (i.e. while building new features, we improve the structure modal layout and tweak it slightly so it's more in-line with the new design sketches I drew up (one example of many)). 

Additionally, I think that the current context is actually relatively fast, we don't need to have everything loading instantly and I think that since we're going to migrate to a partially-localised db anyway, I don't see the need to lose sleep over this.

Preventing the user from travelling without a spaceship also requires the fuel component, which means we'll need to introduce a refuelling mechanic and a mission/story for the user to collect and pass fuel in again. I can't see our users getting far enough where they would be constantly flying between our limited number of planets and also there's not enough content for them to currently "abuse" this system.

Improving the rewards for missions is sort of meaningless provided we make things easier to follow with regards to crafting recipes and giving our users access to more granular control over the resource collection process. 

We do want our users to be able to travel as that symbolises the end of their onboarding/tutorial process.

We will include a place to look at the feed of user classifications, as well as some information describing how the voting process & comment system will work in subsequent versions. However, it will be a simple, read-only component.

I'm going to update the clean minerals mechanic with a request to change the process we add items to the inventory, by creating rows and not having multiple rows where `owner` && `item` are the same. I'm thinking we do something like Crashlands where your raw resources are accessible at any time, otherwise we'll have to create rows for every setting. Either that, or maybe we add a configuration column that describes where the 5 coal in a user's inventory are split. That way we don't have to create a column for every setting...but it could be awkward to get started. Right now we won't have enough users for it to be a huge issue, so we can move this ticket. I think what I will do is look into setting up a tool so that we can administer/view this side of the db (inventory) easier. 

## Tickets to add
1. Get rid of extra layout complications
2. Assign all classification/anomaly types to settings (see commit `[main 61bff5c] 🍡🪨 ↝ [GP-43]: Create some snippets and adjust components for pulling data based on active anomaly` (CPW board)


## Tickets to move
After all of that, I am suggesting we move some tickets to subsequent sprints:
1. Improve rewards for missions
2. Prevent user from travelling without spaceship
	1. During some testing today (29/6/24), I got caught out again with this and it was quite confusing because there was no error or anything returned to the user/frontend...so got confused at first
3. Any classification feed/component context that isn't strictly READ-only
4. Improve `{activePlanet}` context management
5. New layout structure for "pick your planet" and other early missions
6. Replace "clean minerals" mechanic

Overall, this leaves us with the following tickets:
1. Assign all classification/anomaly types to settings (CPW)
2. Get rid of extra layout complications (SGV2) - in progress
3. Plan out how we structure the narrative onboarding (semi-complete) - in progress (SGV2)
4. Insert tutorial text into narrative onboarding (in current layout) (SGV2)
5. Initialise "edit mode" - either this, or use 3) & 4) to better describe what to do and leave this for the next sprint/UI update
6. Feed component and overlay - in progress (SGV2, but create a duplicate, linked, in CPW)
7. Update mining structure all resource-collection modals to show requirements - in progress (SGV2)
8. Create spaceship structure - in progress (SGV2)


Additionally, I think post-V2 launch we'll further diversify the boards, and we can close SGV2 project and split up frontend components further (just get sprint dashboards for multiple projects/boards)