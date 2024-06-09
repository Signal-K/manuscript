---
tags:
  - Sprints
  - Sprint-Planning
  - Star-Sailors
  - Editing
connie-publish: true
connie-page-id: "19103901"
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
1. Deploying their automatons to collect resources
2. Constructing a "Meteorology tool" and then using it, making their classification (Mission 1)
3. When the automaton finds a rich resource vein, the user will have the option to start a mining operation, this way they don't need to deal with pesky automatons and their limited (for now) capabilities. The mechanism of reward collection will remain roughly the same, however
4. Building their camera module for their automatons (I think we'll do retrospective upgrades to automatons, and maybe structures i.e. if you develop a module, then all the previous 'parent items' now have it. Probably more relevant/useful for automatons. And will only be the case per-anomaly(setting)). This plays part of the "expanding observatory network" storyline
5. Collect specific surface-level information about your planet using the Surveyor tool. 

I think that maybe mission 2 or mission 5 should be locked behind another TIC lgihtcurve classification.

Potentially we could have a component that shows your current "power" or "network" sort of like an Obsidian graph?

## Component-by-component
1. For now, all classification data points will be manually added. There will be no automaton included. This is because the quantity of anomalies & data points to be added is relatively low, I feel, and spending time focusing on building automated workflows takes valuable time away from building out the real components.

# Things to do/fix
1. Automatons currently only pick up coal. No sectors. → [SGV2-14](https://signalk.atlassian.net/browse/SGV2-14) 
2. Take a look at undeployed items: I think there’s still some work that may need to be done, however as of now all items that can be undeployed (i.e. not attached/detached from anomalies table (FK)) are accounted for as of: [SGV2-55](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-55)

Fix the component that shows completed missions: [SGV2-51](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-51)
    - Maybe we could start off with just an identifier if all missions [in a group?] are done? [SGV2-57](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-57)
    -  We just need to add the foreign key for the items added to inventory from completing a mission → [SGV2-50](https://signalk.atlassian.net/browse/SGV2-50)

I'm taking a look at our Unity stuff and I'm thinking that it might be a good idea to bring back [CPW-2](https://signalk.atlassian.net/jira/software/projects/CPW/boards/1?selectedIssue=CPW-2) 

***Should the TIC ids being observed be related to the starting planet or random?***


(My question to `gpt`):
> [[Sprint GPT Questions]]



#### Things to create
* Update the `classifications` table so that we can specify the anomaly type being classified