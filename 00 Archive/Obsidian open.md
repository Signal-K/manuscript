---
color: var(--mk-ui-text-secondary)
sticker: ""
---
Link everything with open tickets in Jira

# Mission list
```ruby
const [missions, setMissions] = useState([

{ name: "Pick your home planet", completed: false },

{ name: "Build your first rover", completed: false },

{ name: "Collect your first resources", completed: false },

{ name: "Build your first structure", completed: false },

{ name: "Make your first classification", completed: false },

]);
```

Note - this should be part of the main menu area.

So I think we can come up with some tasks that make up missions, and provide rewards to get the users up to speed with the gameplay. I'm thinking about making an API route for `/missions` but that may be a bit pointless compared to how we're currently doing it. Maybe a context field that keeps track of the missions the user has completed.

For now, the home planet is the user's `profile.location`, however this changes based on where they are viewing/visiting. So maybe we could create a component like a beacon that defines where the user wants to mark as their main base (it can be moved, but will keep track of the coordinates/sector/anomaly it was previously on).
# Planets
* Ring layout -> Could be used to display structures in orbit
	* This is dependant on the classification models that will be available in V2.0, potentially we won't need to launch anything into space and therefore we can hold off on this for now.
# Automatons
 * Rovers will start on a planet and then be deployed (multiple times) to a sector to explore (gain information), **collect resources, aide in construction, or collect info to review (e.g. photos). > SGV2-20 **
 * * SGV2-20: I will set rovers to be craftable using 1 piece of iron, this will be a placeholder crafting recipe (see [[Crafting]]) and will not use the crafting microservice/API route during this phase of development. Items will be collected just by the rover, there won’t be any special modifications/'rover arms' etc. for now.
* Rovers need to be craftable - currently they are just created without any requirement. So we need to go back to the "onboarding button" ticket, so that users start with some assets. Or maybe by visiting their first anomaly (planet) they get given some items as a reward. Or maybe their ship crashes and they get the parts for their rover as "salvage" (this could be part of the broader narrative)

# Sectors
Sectors won't be pages, they'll be individual overlays, I think starting off as a popup list that shows the basic information. The interactions in-game are occurring on a planet-scale for now (e.g. deploying rovers, building/interacting with structures) so I don't think we need to have any write-actions for sectors at the moment

* Background images & maps/portions of maps could be useful though
* Generate complete make-up/composition when creating a new sector, including confirming that the rover images change each time
* Potentially integrate the python runtime to create more dynamic & accurate/realistic sectors

Could we potentially show the sectors as part of the frontend (i.e. hexagons replace the grid pattern, that's where things are deployed to?). This is something we need to urgently decide because we don't want to go all in on the "no sectors" plan for V2.0 and have to re-write a lot of code.
We just need to determine if they can be placed into the `anomalies` table, if so, I'm leaning towards having sectors in-place for V2.0.

# Pages
> Outside of the two external pages (see the VP top navigation menu), this is probably a good start.

Let's start work on the external pages next week. For now, I'm going to write some ideas.

In Voidpet, the pages are as follows:
1. Shows the missions -> (bottom-to-top overview) bottom bar of challenges, CTA button, description, configuration, character/visual assets (on top of a background, which fades into a solid colour below), some information, and a header with title, question mark (rhs) and "monster type" (lhs), back button (lhs)
2. Shows the monthly event, a solid background colour

Everything else is an overlay where the top 15% of the display is still visible.

Obviously we'll be able to switch between the different planets by swiping across (for now, by clicking the arrow buttons), this could update the `activePlanet` context by changing `profiles.location` field for the user. Maybe we have a mission/event log (recent deployments, for example) on one page, and the other page could show your full inventory and a small craftery? 
For a full log, we'd probably need to create a table to keep track of every deployment. Which may be overkill. So we'll see what our users have to say.

# Anomalies
* When a new anomaly is created, a new folder inside `anomalies` storage bucket (Supabase) should be created, named after the PK of the new anomaly. (When we move to IPFS )



