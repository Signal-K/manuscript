---
tags:
  - Sprints
  - Sprint-Planning
  - Star-Sailors
connie-publish: true
connie-page-id: "19103901"
---
See [SGV2-40](obsidian://open?vault=Liam's%20vault&file=07%20Development%2FRetrospectives%2FFirst%20Mission%20Group%20-%20SGV2-40%20Retrospective) for information on the previous sprint

# Things to do/fix
1. Automatons currently only pick up coal. No sectors. → [SGV2-14](https://signalk.atlassian.net/browse/SGV2-14) 
2. Take a look at undeployed items: I think there’s still some work that may need to be done, however as of now all items that can be undeployed (i.e. not attached/detached from anomalies table (FK)) are accounted for as of: [SGV2-55](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-55)

Fix the component that shows completed missions: [SGV2-51](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-51)
    - Maybe we could start off with just an identifier if all missions [in a group?] are done? [SGV2-57](https://signalk.atlassian.net/jira/software/projects/SGV2/boards/8?selectedIssue=SGV2-57)
    -  We just need to add the foreign key for the items added to inventory from completing a mission → [SGV2-50](https://signalk.atlassian.net/browse/SGV2-50)

#### Things to create
* Update the `classifications` table so that we can specify the anomaly type being classified