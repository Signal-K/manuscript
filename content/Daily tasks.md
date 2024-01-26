1. Come up with todo list & structure by the hour -> including for the hours we're having our coffee
5. Create plan for microservices, integration into `sytizen`, workflow for Unity (including action), discuss plan for integrating new UI & actions with microservices, automated tests.
	1. d3.js v0.dev based on lightcurves?
6. Continue with migration to Quartz
7. Close 10 branches; if tickets are still open, add to quartz and provide link to pull request
8. Create a(n admin) page to view all data & components
9. We also need to re-check the "exploration start" mechanic for sectors
10. Attempt to fix the database password issue -> compare with other supabase instances. Perhaps setting up supabase studio (finally) with all the required sql statements (for setup) could be a good option.

### Microservices
1. Method for generating lightcurve, integrating into d3
2. Method/route for populating anomaly/entity data -> sample, point to old routes in `signal-k/sytizen` repo

As I discovered last night, there is no discriminator in `client` forcing the use of any crafting recipes. For `GP-10` to be closed, we need to have sectors being created with the capacity for any `mineral` row in `inventoryITEMS`. We need to simplify the number of components in files/scripts like `StructureCreate.tsx`. A better design/layout for creating structures, and then displaying the inventory as well. `GP-11` ticket can be closed once we have the api being linked, with a toggle option -> i.e., unless I can get flask to be deployed perfectly with 99.9%+ uptime, just have an override function to create whatever structure I want.

This also requires us having multiple new rows to `inventoryITEMS` table created and fully instantiated & initialised. 

### Nordkurve
Phase 1 ->
1. Registration, migration and schema setup
2. "Backend" portal (really a frontend, though, technically) for admins/board to view all data

I think we should re-use the `saas-starter-kit` & then the admin [frontend] schema for user management. Extend that frontend schema with a dashboard template

### Keepup
What we have now ->
1. Bottom bar
2. Main area/content grid

Minimum viable product ->
1. Push notifications
2. Method to create a feed
3. Posts will be pushed from a local dictionary for now -> no server-side action for this component
4. Ability to "favourite" posts/messages, these will be saved in runtime state
5. Post category

Post features:
1. Content
2. Avatar, title/user sender metadata
3. Favourite, user-determined metadata

Component list ->
1. Timer - deliver one new "post" from off-chain, off-db (aka locally-hosted) dictionary. Make it every 6.14 seconds as an example discriminator
2. MVC model for all items dictionary
3. Visible authentication model -> for now, let's keep it entirely local, so realistically any password combination would work. We can, however, re-use the WASP(-12b) login layout, or (preferably, due to simplicity of creating the layout) duplicate a daisyUI/tailwindCSS form and then have an input lead to a page/route -> change
4. Method to add a "server" to the "database" -> the idea is that you would choose from a pre-defined list of "servers", which comes from the local dictionary. Once they have been added, we can then add them to the feed.

So in short, essentially one page, no settings required, page state & schema depends on (micro/faked)-auth status

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



### Travel
Key dates:
1. May 18 -> Bayer Leverkusen vs FC Augsburg (11.30pm melbourne)
2. May 22 -> Europa League Final (Dublin) **
3. May 25 -> DFB Pokal Final (Berlin) **

So some options ->
* Go for the week
* Go for first two
* Go for second two

Zima board for hosting api, development previews -> hosting dev testing apis, so no need for 100% uptime