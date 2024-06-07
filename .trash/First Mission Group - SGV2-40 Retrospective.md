---
tags:
  - Star-Sailors
  - Sprints
  - Retrospective
  - "#Sprint-Planning"
Jira:
  - SGV2-40,
  - GP-18
  - GP Board 2
_links:
  - https://signalk.atlassian.net/jira/software/projects/GP/boards/2
Deployments:
  - https://starprotocol-47x82dzzm-gizmotronns-projects.vercel.app/,
  - https://starprotocol-47x82dzzm-gizmotronns-projects.vercel.app
connie-publish: true
connie-page-id: "19103844"
---
# Initial thoughts
There were a few things that we need to go over that weren't quite finished, however, I'm pretty happy with how this sprint went. It was my first sprint that I was actively managing and attempting to get sorted out on time, and it was also one of the few with a strict and achievable goal in a short time frame.

The goals were pretty simple:
> Create the frontend components required for the first 5 (frontend) "missions" to be able to be completed

The two biggest things of note:
1. We failed to complete every single backend process/cleanup (e.g. classification/mission blocking)
2. There really isn't a coherent UI that explains what to do

But from a functionality, the main objective was completed.

# Things that weren't finished
There were a few things that probably should have been finished as their components/architecture was actively being worked on as part of this sprint, however I don't feel it's going to hurt too much to move these around.

See the [Bugs & Things to fix](https://signalk.atlassian.net/wiki/spaces/SSV/pages/edit-v2/1769476) Confluence page for more info, [Sprint retrospective Confluence](https://signalk.atlassian.net/wiki/pages/viewpage.action?pageId=19136529) .

Listed immediately below are things that I'm not sure if we need to fix to achieve the goals of the next two sprints. E.g. the `classifications` table may not need to be updated until the third mission group or the subsequent sandbox-y mode. We'll conduct further reviews in the new sprints

- Initial classification model for [https://signalk.atlassian.net/browse/SGV2-40](https://signalk.atlassian.net/browse/SGV2-40) first mission group is looking good. I’ve removed some key components e.g. the rich text editor which is something we can bring back once we expand the behaviour, context and potential information for the posts/publications (and potentially the place where we store this content) → [https://signalk.atlassian.net/browse/SGV2-29](https://signalk.atlassian.net/browse/SGV2-29)
    - Essentially, we need to expand upon the overall classification behaviour, but for now (end of First Mission Group sprint), we have everything we need, as well as from the front-end perspective.
    - I also think that overall we won't need to adjust much for the second mission group except for the anomaly type

* Currently, we aren’t removing items from the inventory when they are used in crafting functions/actions. So we can limit what can be done based on the crafting (e.g. can’t craft an item unless you have the required items), however we can’t prevent users from being able to go and create the same thing over and over again (as we’re not taking away the ingredients).
	* We’ll need to update crafting recipes again → [CPW-16](https://signalk.atlassian.net/browse/CPW-16)

- [CPW-16](https://signalk.atlassian.net/browse/CPW-16) 
* Profile/Planet context is taking too long to load.
- We’ll need to update the location and owned fields: [SGV2-25](https://signalk.atlassian.net/browse/SGV2-25) 

- [SGV2-49](https://signalk.atlassian.net/browse/SGV2-49) → We just need to determine what the user will actually be doing. The more I think about it, the more important I think things like profile components will be early-game, especially in developing an attachment between the user and their character. key focus/word is on character
    - Capt’n Cosmos has been relegated to V2.1 or beyond



# Deployments

1. Fleek → [https://app.fleek.co/#/sites/snowy-unit-3436/overview?accountId=gizmotronn-team](https://app.fleek.co/#/sites/snowy-unit-3436/overview?accountId=gizmotronn-team)

# Next steps
## Mission Group 2 Sprint
The next sprint will start on the 9th of June and have the following goals:
1. Successfully build functionality for the next 5 frontend-facing missions
2. Funnel users back to the index route between the first and second mission groups (i.e. users have the option to go back to the "pick object to classify; classify; repeat" game flow we had in V1 last year)

### Things to fix/do from this sprint
1. Automatons currently only pick up coal. No sectors. → [SGV2-14](https://signalk.atlassian.net/browse/SGV2-14) 
2. Take a look at undeployed items: I think there’s still some work that may need to be done, however as of now all items that can be undeployed (i.e. not attached/detached from anomalies table (FK)) are accounted for as of: [SGV2-55](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-55)

Fix the component that shows completed missions: [SGV2-51](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-51)
    - Maybe we could start off with just an identifier if all missions [in a group?] are done? [SGV2-57](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-57)
    -  We just need to add the foreign key for the items added to inventory from completing a mission → [SGV2-50](https://signalk.atlassian.net/browse/SGV2-50)

#### Things to create
* Update the `classifications` table so that we can specify the anomaly type being classified

## UI Cleanup Sprint
This sprint will start on the 16th of June and have the following goals (subject to change):
1. First two mission groups should be clear and easy for all new users to follow
2. Update components from those mission groups to fit in more with the new Figma-voidpet design
3. Improve all other operations & services being interacted with in the current form(at)

### Things to fix/do from this sprint
1. Scrolling issue still persistent (on index page)
2. Improve Grid UI for index route: Grid not quite perfect on index route, but it will suffice for now: [SGV2-35](https://signalk.atlassian.net/browse/SGV2-35) 
3. Have another go at building the Skill tree → [SGV2-45](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-45)
4. We need to update [SGV2-46](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-46) to go from a page to an overlay/sliding panel
5. We need to link this in with the “GoToPlanet” component and improve the size & context/behaviour of the launchpad: [SGV2-54](https://signalk.atlassian.net/browse/SGV2-54) & [SGV2-47](https://signalk.atlassian.net/browse/SGV2-47) 