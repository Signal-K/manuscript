---
tags:
  - Sprint-Planning
  - Code-Snippets
  - Components
sprint: obsidian://open?vault=Liam's%20vault&file=07%20Development%2FSprints%2FSecond%20Mission%20Group
---

Some questions that need to be answered:

#### How do we show > 2/3 automatons/structures at a time
For sprint 1 & 2, we will suffice with a ⌘ button (i.e. click this to see overflow). We don't have enough entities to make this problematic.
Or, we could have an arrow system, similar to the anomaly switcher in the header.
We can look into a long-term solution for this in sprint 3.

#### How can we create rich context-background images? 
* We will require new icons too for the structures & automatons
* Need to determine orientation & screen-sizes

Let's look into other frontends/games that do this well.
Sprint 3 is for UI improvements & clean-up. So we can think about this before then, but no development needs to start on it until then

#### Where can we show sectors?
* I will investigate sectors and how they relate to our sprint goals (i.e. requirement for missions) this weekend

The first guess is we show them in the bottom panel of the grid UI. Will create UI components in Sprint 2 or 3. So from a UI perspective, pretty open & shut. However, we also need to have a look into how this will be used/required for automatons & structures (both deployed and undeployed).

#### Natural things to interact with (not aliens, for now)
**Moving to Sprint 2 or Sprint 4, depending on scope of mission group 2.**

#### How can we show structures in orbit?
Sprint 2 has in-orbit structures. We will prepare for the launch of a space-based observatory/lab, which will include other structures, so that is the initial scope. This then gives us clarity for the orbital/ring layout. 
Additionally, it will require a page for space, could behave like anomalies currently or a different 'mode'; maybe user scrolling changes perspective/view on the frontend.

However, we don't have any structures that will be in-orbit (as of now) for Sprint 2, so this can be migrated to Sprint 4.

#### What shall be part of the context menu & what should be part of the external/parent menus?
Because we're shifting the overlay panel back to Sprint 3 (UI), I think we can move this back to then.

#### What goes between automatons & structures?
* Nothing?
* Natural formations?

Determine DURING sprint 2/4 if any data points or other interactable entities are appropriate or relevant. Potentially nothing needs to be there? It's a big space. Maybe a reference to other locations (e.g. other space, in-orbit...maybe things like the moon mirror/laser pack?)

#### Where can we get reasonable unconfirmed entities from?
Sprint 2 & 4.

#### Visual context for location of entity/anomaly/structure?
Coordinates will be part of Sprint 2, we'll have a rudimentary "random number" generator for now. Sprint 4 will investigate a full, valuable coordinate structure and potentially create some UI components representing distances [between entities] (depending on the overall scope of this sprint)

#### Tags for posts/classifications
Initial thought is no tags for Sprint 1 or 2. For on simplicity. Will revisit in sprint 4.
This obviously means we'll need to take another look at the post[card] UI then, as well. 