---
connie-publish: true
connie-page-id: "16678914"
banner: "https://resources.afl.com.au/photo-resources/2024/06/07/66ff7c48-e1d3-4ea7-a675-08b36b75d8ec/Sunday-teams-R13.jpg?width=902&height=536"
---
Current Mission List:
```tsx
const [missions, setMissions] = useState([

{ name: "Pick your home planet", completed: false },

{ name: "Build your first rover", completed: false },

{ name: "Collect your first resources", completed: false },

{ name: "Build your first structure", completed: false },

{ name: "Make your first classification", completed: false },

]);
```

Right now, we have components for the following:
1. Choosing your home planet: `pages/onboarding/index.tsx`. After signup, users click a button that assigns them a planet (`profiles.location`), and then this updates their `activePlanet` value. Thus, this mission is completed when `profiles.location !== null`
2. Building your first automaton -> we simply need to look in `inventory` table for at least one row where `owner == session?.user?.id && item == 23 && notes == First Rover Created By User using Vehicle Structure...` (a reminder that the `notes` column does have some extra stuff. We also need to ensure that there is no way to build an automaton without having the "Vehicle Structure" (id: 22) and either the crafting materials required (currently not set) or having no automatons (we also need to update `item == 23` to include other PKs of different automaton types defined in `api/gameplay/inventory`))
3. Collect your first resources -> I think this should be moved around, as we can't deploy our rovers without having a "Vehicle Structure" on `activePlanet` (or rather, the `anomaly` the rover is currently on). 
4. Build your first structure -> we don't want our users to be tasked with performing citizen science classifications right away, we want to have some more gamified content first. So the first structure should be the "Vehicle Structure". As long as `inventory` does not have any entries for "Structure" types, we can build the first "Vehicle Structure" item for free
5. Make your first classification -> we need to broadly increase the scope of classifications, but for now we just need to have some text linking to a data point (`anomalies` table row). We can expand on this later (and bring it classifications from Star Sailors V1[.0])

We had a point in [OpenNotes](obsidian://open?vault=Liam's%20vault&file=Tickets%2F!Open%20notes) for the "external pages", so maybe we start work on that as part of the onboarding flow. Create a scrolling page where you first pick where you start, build your first automaton, etc. Sort of like swiping between different sections, you have to finish a mission before swiping to the next one.
We could group missions into categories/(insert better term here; i.e. chapters), so there's better understanding of where the user is at.
We could also have different mission [groups] for different anomaly types, but I think that can be held off for now

I think we should add some new context fields:
1. Create a list of item ids for "Automatons", "Minerals", "Structures" so that we can sort through `inventory` table more easily
2. Create a list of "firsts" that the user has/has not achieved (e.g. has placed first structure/automaton)
I'm debating as to whether we include the missions as a table, or as context (e.g. we define a list of missions in `/api/gameplay/missions` (like inventory definitions/dictionaries), but then a list of completed missions in `missions` table, or whether it's all nextjs-side global context). We don't have to worry about limiting the calls to the database side, so it's more a matter of what's easiest/simplest from a functional perspective. I think we do both -> a list of missions completed, but save the completed ones (for the authenticated user) in client-side context/storage (for now).

# Second mission group
1. **Discover Cloud Formations**
    - Objective: Use the Meteorology tool to identify and classify different cloud formations on your home planet.
    - Completion Criteria: Successfully classify three unique cloud formations using the Meteorology tool.
    - Reward: Unlock the Cloud Spotter module for the Meteorology tool, allowing for more accurate cloud identification.
2. **Establish Resource Mining**
    - Objective: Locate and establish a resource mining operation on your home planet.
    - Completion Criteria: Deploy a rover equipped with a resource scanner to locate mineral deposits.
    - Reward: Access to a new mission to construct a mining facility.
3. **Construct Mining Facility**
    - Objective: Build a mining facility to extract resources from mineral deposits.
    - Completion Criteria: Gather the necessary materials and construct the mining facility structure.
    - Reward: Start generating resources passively from the mining facility.
4. **Expand Observatory Network**
    - Objective: Expand your observatory network to improve anomaly monitoring capabilities.
    - Completion Criteria: Build a Transiting Telescope structure adjacent to your Telescope Signal Receiver.
    - Reward: Enhanced anomaly detection and monitoring capabilities.
5. **Research Anomaly Survey**
    - Objective: Conduct a comprehensive survey of anomalies using the Surveyor tool.
    - Completion Criteria: Deploy the Surveyor tool and gather data on at least three anomalies.
    - Reward: Unlock advanced anomaly analysis tools and insights.
      
      Specifics -> go over the findings from the surveyor of the basic planet/anomaly stats and cross-reference.

 > Come up with mission relating to building telescopes & getting data from each telescope module. Then write up a pipeline for other structure [modules]. Include info on how we structure the classifications (maybe we tie them to a structure. You can view all classifications from an anomaly, but they can be separated by topic, which is defined by the structure, and structure module)
 
Maybe we go through all the telescopes in mission 3?
