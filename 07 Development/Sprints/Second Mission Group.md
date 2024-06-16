---
tags:
  - Sprints
  - Sprint-Planning
  - Star-Sailors
  - Editing
connie-publish: true
connie-page-id: "19103901"
sticker: emoji//1fad0
---
See [SGV2-40](obsidian://open?vault=Liam's%20vault&file=07%20Development%2FRetrospectives%2FFirst%20Mission%20Group%20-%20SGV2-40%20Retrospective) for information on the previous sprint

# User flow
So where did the user finish after completing their first set of missions?
* They've now got an automaton, telescope with module `14` attached, and they've made their first classification.
* 

I think I would define the narrative goals for the second mission group as follows:
> setting up your colony on your new planet and getting resources so you can expand your network

So I think we'll take them back to the home page initially and maybe have a toolbar there with some info along the lines of "you've completed your first part of the tutorial! You can now go [here] to do the next part!". Additionally, we can also give our users the option to just classify TIC Ids if that's all they want to do for now. This means we'll have to add in a function that fetches random lightcurve images, as currently the api only pulls in pre-defined images that are matched to the TIC ID [configuration] value of the anomaly in the `anomalies` table.

After that, we'll lead them into some open-ended widgets, which will consist of them doing the following:
~~1. Deploying their automatons to collect resources~~
~~2. When the automaton finds a rich resource vein, the user will have the option to start a mining operation, this way they don't need to deal with pesky automatons and their limited (for now) capabilities. The mechanism of reward collection will remain roughly the same, however (Mission 1)~~
3.  Constructing a "Meteorology tool" and then using it, making their classification (Mission 2)
4. Building their camera module for their automatons 
		(I think we'll do retrospective upgrades to automatons, and maybe structures i.e. if you develop a module, then all the previous 'parent items' now have it. Probably more relevant/useful for automatons. And will only be the case per-anomaly(setting)). This plays part of the "expanding observatory network" storyline
5. Collect specific surface-level information about your planet using the Surveyor tool. 
		Is there something we can come up with that relates each classification type/structure creation together? E.g. can the photos help with understanding the behaviour/setup of the planet/anomaly (cross reference Mars photo data with data from that anomaly?)?

I think that maybe mission 2 or mission 5 should be locked behind another TIC lgihtcurve classification.

Potentially we could have a component that shows your current "power" or "network" sort of like an Obsidian graph?

## Component-by-component
1. For now, all classification data points will be manually added. There will be no automaton included. This is because the quantity of anomalies & data points to be added is relatively low, I feel, and spending time focusing on building automated workflows takes valuable time away from building out the real components.
2. We also need to update the `<span>Unlocked</span>` value/processor

# Inventory
## Post-MG1
Here's what the user will have in their inventory after completing [[First Mission Group - SGV2-40 Retrospective]]:
* 29
* 22
* 23
* 12
* 14
* ~~16 * 2~~
* ~~13 * 6~~
* ~~11~~
* ~~15~~

So we'll remove items `11`, `13`, `15`, and `16`.

## Crafting mechanics
I was considering removing the crafting mechanic from the game and just basing all construction around the completion of individual missions, but I then realised that that sort of renders the concept of collection of resources pointless.
We need to sort out the crafting mechanic ASAP.

Maybe we create a function that identifies all "minerals" item types in `inventory` table at the completion point of a mission group and clears them? Because the rewards we're giving are those that are required to build the next structures, they're not rewards that will be long-lasting (for now)?
This could just be a test function until we figure out a better implementation. Or maybe we move them to another planet/un-deploy them (that could be the next step. We need to figure out the undeployment/redeployment, maybe when a mission group is complete, everything remaining is "undeployed" and you either have to "fetch" your undeployed items or find new ones)

> This is mainly to clean things up from my perspective when building out the app, but I also don’t want to have the users not need to fetch other resources since they’ll already have coal for the crafting of the mining station structure. We can fix this by increasing the complexity of the recipe, but for now this is a simple way to sort this out

## Structure modals
I think that what we can do is only show parent/root structures on the index route/grid panel. In the root structure, you'll be able to select the different modules you've installed onto that root structure (like in Voidpet when you click on a tree/plant and then perform an action).
This does mean we'll need to create an identifier of parent structure in `inventory` if this hasn't been done already.
> This has been done (for mineral deposits to identify the automaton of origin), now we need to set this up for structures as well.

We also need to block certain structures from being created on the same setting (otherwise the `.lim` discriminator could be considered to be wrong when identifying the base/root structure when creating the module structure. )
# Things to do/fix
1. Automatons currently only pick up coal. No sectors. → [SGV2-14](https://signalk.atlassian.net/browse/SGV2-14) 
2. Take a look at undeployed items: I think there’s still some work that may need to be done, however as of now all items that can be undeployed (i.e. not attached/detached from anomalies table (FK)) are accounted for as of: [SGV2-55](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-55)
3. We should add a new base set of anomalies (planets) that are habitable, interesting, and aren't all 100% confirmed (i.e. candidates)
4. Start setting up the character? Which would require an update to the profile form mission...
~~5. Update the `classifications` table so that we can specify the anomaly type being classified~~ 

Breaking this down a bit further:
1. 9, 10, 11 DONE
2. 12 in progress (12 points to using meteorology tool, 11 is crafting/building it)

Fix the component that shows completed missions: [SGV2-51](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-51)
    - Maybe we could start off with just an identifier if all missions [in a group?] are done? [SGV2-57](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-57)
    -  We just need to add the foreign key for the items added to inventory from completing a mission → [SGV2-50](https://signalk.atlassian.net/browse/SGV2-50)

I'm taking a look at our Unity stuff and I'm thinking that it might be a good idea to bring back [CPW-2](https://signalk.atlassian.net/jira/software/projects/CPW/boards/1?selectedIssue=CPW-2) 

***Should the TIC ids being observed be related to the starting planet or random?***


(My question to `gpt`):
> [[Sprint GPT Questions]]



#### Things to create
* Update the `classifications` table so that we can specify the anomaly type being classified

# Final steps
* `app/missions` dir will be replaced by the mission overlays, which will be dependant on the status of SGV2-51 & SGV2-33