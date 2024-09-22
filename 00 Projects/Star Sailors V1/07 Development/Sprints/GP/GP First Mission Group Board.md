---
tags:
  - Star-Sailors
  - Sprints
  - Retrospective
  - Create
---
Currently, this board is incomplete and I think may need some adjustments. It will probably need to have content from the `CPW` board added as well. 

## Current tickets
Let's take a look at the current tickets and how they relate back to the current state of things:

**Create `jsonb` column for anomalies' ownership - differentiate between `profiles.location` ** 
* I'm currently debating whether this is defined in `profiles` or `anomalies` table
* We can have owned entities deployed to anomalies that are *no longer* the `activePlanet` value, but...
* In the interests of reducing complexity and hacky work-arounds, I'm just going to bite the bullet here
We're going to need to set up a "level of ownership" structure. See [here](obsidian://open?vault=Liam's%20vault&file=01%20Backend%2FDatabase%2FAnomaly%20Ownership) 
Users can build anything on anomalies they "own" (not really ownership, in a practical sense it's more like an entity they have a stake in).


**Export of cloud data**
This has already begun, the goal for tomorrow (Saturday 8.6.24) is to create a model for how this can be worked into the next step (at component-level). See [here](obsidian://open?vault=Liam's%20vault&file=03%20Create%2FClassifications%2FCloud%20Data%20Export%20Model) 
Links in with `CPW-14` (creating component to view anomaly data)

**Rich-text & multiline component for post-editing & creation**
After a lot of thinking and also some updates in the #nk12 project, I am deciding we're going to be migrating this. This will be part of a subsequent sprint.
Let's see if removing sprint values from tickets is stored in the history of the ticket. Either way, there should be a reference.


**Content population**
> Populate the following data:
> Sector resources & other content (e.g. mineral deposits)
> Other planet data (like formula for mineral deposit, but on planet-scale)

Obviously we'd then need to build the frontend components to fit in with this.

Now that I'm considering adding sector & sector calculations back into the workflow/app in Sprint 2, this is now relevant.  I guess we can start with something simple like the new sector button, but add some more complex/robust calculations for the mineral deposits. 

I think we will set up some stubs for calculating the mineral deposits (and other params, see [Game Canvases](https://signalk.atlassian.net/wiki/spaces/AGP/pages/3047427/Game+canvases?search_id=69683e3e-5554-427e-8c5d-d5c832b86b90)), however we can just have the mineral deposits be randomly generated for now. This is because we don't have a full list of items/minerals yet and I don't want to have the flask/supa/next docker configuration [completion] be a part of the next sprint.