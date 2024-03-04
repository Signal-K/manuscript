5. Create plan for microservices, integration into `sytizen`, workflow for Unity (including action), discuss plan for integrating new UI & actions with microservices, automated tests.
	1. d3.js v0.dev based on lightcurves?
7. Close 10 branches; if tickets are still open, add to quartz and provide link to pull request
8. Create a(n admin) page to view all data & components
9. We also need to re-check the "exploration start" mechanic for sectors
10. Attempt to fix the database password issue -> compare with other supabase instances. Perhaps setting up supabase studio (finally) with all the required sql statements (for setup) could be a good option.

### Microservices
1. Method for generating lightcurve, integrating into d3
2. Method/route for populating anomaly/entity data -> sample, point to old routes in `signal-k/sytizen` repo

Investigate a new set of planets & stellar/cosmic data.
Additional components:
Radial Velocity  
~~Unity/Flask randomisation write-up~~ (as well as creation of broader documentation service, export for integration into notion alternative down the line)  
  
Data schema write-up for habitability & NPCs  
What does habitability look like in terms of colonisation, user creations etc. future narratives  

Wireframes

Moon architecture

Coordinates & improved galaxy map positioning

### Talon admin
Notion documentation setup: Git-based issues (including gitea/radicle, custom server maybe), actions & other ci/cd pipelines
Are the [plane.so](http://plane.so) pages able to be published/hosted? Link something in with a tool like gitpod?

### Copernic
Possible components:
1. Discussion board, based around bucket/node
	1. Discussion board would be divided into Lens & other protocols (for now, off-chain)
2. News feed for nodes
3. Metadata/custom tags (e.g. linking to a "proper" dsl node)
4. Documentation area -> just do it here on quartz for now
	1. Should include videos/tutorials on how to use our platform
5. Physical data tracker -> could be especially useful for copernic passports?
	1. Can extend out to essentially any data point in a dataset e.g. wildlife tagging
6. Ask gpt for another 5.

Focus on minimal/incomplete UI, the priority is reasoning, brainstorming, documentation and minimum functionality for presentation

CREATING ART OUT OF SCIENCES

In short ->
1. Everything in science is data
2. Everything in nodes is composed of data points
	1. Divided into datasets & codebase for research, community alterations/submissions & contributions, actual notation, additional metadata
3. Because there is no fundamental limit to how narrow our approach, we can adopt a formula from low-level to high-level that essentially functions as a protocol or standard


Zima board for hosting api, development previews -> hosting dev testing apis, so no need for 100% uptime