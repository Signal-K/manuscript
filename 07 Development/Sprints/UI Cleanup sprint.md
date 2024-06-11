---
tags:
  - Sprint-Planning
  - Sprints
---
# Things to look into
[Pre-Sprint 2 | Questions](obsidian://open?vault=Liam's%20vault&file=02%20Design%2FQuestions%2FPre-Sprint%202) 
1. Entity switcher -> overflow for more than 2/3 automatons/structures
2. Rich-context background images
3. Context vs Parent menu items

I think the first thing we'll want to do will be to set up the overlays
# State of the user - where are we at?
Now that our users have made a handful of classifications and have started to populate their world, I want to start introducing the feed/content reading views and some options for them to expand their world, while of course also fixing the UI issues & solving problems that have been described and discovered/caused as part of the first two sprints.

# Components to update
* Travel format - animation, show destination & distance
* Create a crafting grid/dedicated crafting component that will take the resources in the inventory and the structure to be crafted
* See full list at [[First Mission Group - SGV2-40 Retrospective]]

# Missions to update
## Mission 2
### Mission 2.2 -> Mining Station
> I want to be able to declare it with an option value, called "target" Target will specify the desired resources that the user needs to get to the next stage. For example, when calling this component for the first time in the app, we need to have a row in the `inventory` table where `owner` = session.user.id, `anomaly` = activePlanet.id, `item` = 11, and `quantity` > 0 The component should fetch the user's inventory at the start, and if they have the required row, then it returns an extra bit of text in the main modal/component, a button saying "you have the required resources" If the user doesn't, it makes a note of how many resources are required to get to the target (here, we need 1 piece of coal), and then when the user deploys the station, it calculates how long until the 1 piece of coal is mined (should be less than a minute). Once it determines the station has been deployed long enough for the resource to be generated, it says "resources ready".

Currently there's no context on the `MiningStation` structure component.

This sprint will start on the 16th of June and have the following goals (subject to change):
1. First two mission groups should be clear and easy for all new users to follow
2. Update components from those mission groups to fit in more with the new Figma-voidpet design
3. Improve all other operations & services being interacted with in the current form(at)