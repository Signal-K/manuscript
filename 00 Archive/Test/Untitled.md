I am currently creating a citizen science web application with NextJS, Flask, Thirdweb & Supabase. It's essentially a clone of Zooniverse, focusing on space science, with some minecraft, no man's sky, and voidpet elements thrown in.

I'm using Github to store my code, Jira for ticket management, Confluence for my docs, and I want to use Obsidian for my local notes and then sync them up with Confluence.

I want you to create a folder structure for my notes.

Here's the current high-level overview of my game:
1. NextJS application (currently in progress)
2. Flask APIs (mainly used to generate citizen science data and things to classify, and to handle user classifications)
3. Supabase & backend (Lens Protocol, IPFS, maybe some web3 components soon)
4. I'm wanting to create a CLI and maybe a stand-alone mobile application at some point
5. Maybe also an SDK so users can fork it and add their own datasets (everything will be on the one social graph, sort of like ActivityPub or Lens Protocol)

For the application/frontend, the gameplay is split into the following:
1. Automatons/Robots -> Collect resources & build structures
2. Structures -> Creative building (later), right now they're used to find objects to classify (e.g. unconfirmed transit planet events through lightkurve python package) or build other things (e.g. we have a structure that builds robots)

The next few months of development are centered around the following:
1. Getting more things to classify for the user
2. Handling the classification & data presentation process
3. Gameplay component e.g. crafting/building structures
4. UI elements
5. Integrations & partnerships to onboard users

This is a copy of my `package.json`:
    "@ducanh2912/next-pwa": "^10.2.6",
    "@headlessui/react": "^2.0.4",
    "@lexical/react": "^0.15.0",
    "@material-tailwind/react": "^2.1.9",
    "@radix-ui/react-icons": "^1.3.0",
    "@radix-ui/react-scroll-area": "^1.0.5",
    "@radix-ui/react-slot": "^1.0.2",
    "@supabase/auth-helpers-nextjs": "^0.10.0",
    "@supabase/auth-helpers-react": "^0.5.0",
    "@supabase/auth-ui-react": "^0.4.7",
    "@supabase/supabase-js": "^2.42.7",
    "@supabase/ui": "^0.36.5",
    "axios": "^1.6.8",
    "beautiful-skill-tree": "^1.7.1",
    "class-variance-authority": "^0.7.0",
    "clsx": "^2.1.1",
    "daisyui": "^4.11.1",
    "framer-motion": "^11.1.9",
    "lexical": "^0.15.0",
    "next": "^14.2.3",
    "next-pwa": "^5.6.0",
    "react": "^18.3.1",
    "react-dom": "^18.3.1",
    "react-html-parser": "^2.0.2",
    "sass": "^1.77.4",
    "tailwind-merge": "^2.3.0",
    "tailwindcss-animate": "^1.0.7"


I currently have Jira boards set up for the following:
1. Generating planets & content -> anything to do with generating content for classifications, storyline content, and generating anomalies (things to classify, e.g. planet candidates)
2. Classifying planets -> the actual classification process
3. Visuals -> Frontend components. Most of the stuff/tickets I do are in here for now, as well as where I create my sprints, as the main thing I'm actively developing right now is the nextjs frontend.

I have the following pages at the top-level of my confluence space/obsidian vault now:
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


---
# List of structures

As of the time of writing, we’ve got the following structures defined in inventoryITEMS:

| **id** | **Name**                                    | **description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Parent                 |
| ------ | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| 12     | Telescope Signal Receiver                   | The base telescope. Provides a base that can then have other add-ons built on top, as well as serving as the base for all off-planet observatories                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | /                      |
| 14     | Transiting Telescope                        | An add-on to your telescope base (12) that allows users to view transits                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | 12                     |
| 22     | Vehicle Structure                           | Allows vehicles to dock to them, provides a method for deployment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | /                      |
| 24     | Surveyor                                    | This tool clips onto your telescope receiver and allows you to unlock complex stats about your anomaly<br><br>(side note: how do we get all this data? I guess the Configuration column in `anomalies` table allows us to add more fields without modifying the direct schema, e.g. if scientists decide a new field is helpful/required [for a standard] when discussing exoplanet candidacy, e.g. e.g. if temperatureEq wasn't included in V2.0 and we wanted to introduce it in V2.1). But the main question is how do we get all this data when a lot of it won't actually be known? At V2.1 I want users to be able to vote on data to be added, e.g. if `temperatureEq` isn't known when it's created. This also comes back to the creation/population process...)<br><br>> We'll determine what stats the transitting module gets and what this new survey module gets | 12                     |
| 26     | Meteorology tool (rename)                   | Will form the basis for all observations of atmosphere-related studies on the current planet (i.e. the planet it's situated/placed on).<br><br>Potentially will link in with telescopes for some initial observations on nearby/other anomalies (but will eventually require this tool on that anomaly. How do we link everything together?)<br><br>Has multiple modules.<br>At the start, it can return one cloud spotting each day -> you can augment it to return other things, and to increase the efficiency                                                                                                                                                                                                                                                                                                                                                             | /<br><br>Related to 24 |
| 27     | (what tool is used to find/explore clouds?) | First module, specialising in cloud-spotting.<br><br>Could be introduced in V2.1?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | 26                     |
| 28     | Camera                                      | Is placed onto a vehicle structure, all vehicles created from that structure now have a camera.<br>The automatons will return from their journeys with photos (1 photo per day to begin with, across all automatons created with that camera-vehicle structure), classifying a photo will unlock an additional reward (let's say 3x rewards).<br><br>We might need to create a multiplier for rewards db-side.                                                                                                                                                                                                                                                                                                                                                                                                                                                                | 22                     |
|        |                                             | Provide 2 more citizen science minigames (and the required structures) from `CPW-17`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                        |
|        |                                             | Probably will require a structure for the construction & deployment of spaceships (i.e. a launchpad)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                        |
|        |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                        |
|        |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                        |
|        |                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                        |

Structures will be split into the following categories:

1. Those that provide citizen science data → read/write (they will provide a platform to fetch/request data, return it, and then allow the user to make the classification).
2. Those that provide utility for resources -> allow the user to collect resources (e.g. mining drills), upgrade items (e.g. "enchanting table"), store resources (e.g. "chest"), etc.
	1. Some of these structures may allow the user to upgrade how fast/well they can do something


## Global rules:
1. For every structure type (basic citizen science modules), if a user does not have one, they will be able to create one for free (i.e. if they do not have a TSR (12) ANYWHERE, they can create their first for free)
	1. This means we'll need to update the structure creation modal to make a list of all the structures they have so that we can have this free model in place. Currently, structures don't cost anything to create (in test versions) and I originally scoped it out so that the first structure of ANY sort would be free.
2. A note that structures that were launched will have a static command module that will stay on the anomaly's surface (or whatever synonym for surface is applicable for non-planetary anomalies). I do not think this will be a mere cosmetic decision

# Telescopes
Method:
### 12 -> Signal Receiver
This is the first structure that users will create for observatory-style citizen science interactions. It will initially be a pretty simple modal, showing a diagram of the telescope and a list of all parts that can be created.
I'm thinking long-term we have an interactive control panel with a live view of each component and being able to click onto each one, for now I think we'll just have a list view of components and their "status".
i.e. right now there's only one module to add to a telescope, which is `14`. If the planet AND AND user have this, then we can mark it as green. Otherwise, mark it as red and give them the option to build one.
Users will be able to create `14` without `12`, but it will give them a warning if they don't already have `12`.  This persistent creation method (rather than alternate creation methods based on structure hierarchy) is ideal because it makes my life easier :P

Space-based telescopes WILL require a launchpad

- While theoretically (judging by the Kepler Space Telescope, at least) one space telescope would be enough, the narrative would be that the first telescope that is launched is quite low-powered and can only observe near-field objects and generate their light curves. Once users begin collecting multiple planet anomalies, they could "connect" their telescopes to create an interactive network

### Data collation
I think that each base planet will have just one lightcurve graph, which would be potentially a binned graph. Users will have to launch instruments into orbit (i.e. space telescopes) to collate more information and build better lightcurves. This could help with the "customisation" issue but as there would be more total lightcurves (and as a rule, more methods of viewing the same anomaly of any type), that could introduce strain on our storage capacity.

# To-Do

For each type of citizen science interaction, there will be the following steps:
1. Click on a structure
2. Request data -> this may be instant or may require a time delay (e.g. sending the rover out to collect resources from a sector's deposit [Tiny Space program] will also result in it taking some photos, however these won't be received until it docks again)
3. Return the data -> this may be instant or with a delay (based on step 2). Some structures may only look at a single target and therefore not require any configuration (so Steps 2 & 3 are combined), or they may need a varying level of configuration
4. Make the classification -> this may be as simple as the text-box method we had in V1.0 and the alpha versions of V2.0, however there may be some multiple choice options or other ways to "write" the data

We will therefore need a layout for each of these options

We might want to take a look at state management for users' inventories, so we don't need to keep making requests back (i.e. make a local version/copy)?

**I also did just realise that activePlanet being used as a discriminator will be a problem when users have multiple planets...**

# Classifications
* Right now we have a global `classifications` table which I think will be where all entities/anomalies are classified (so every type of citizen science interaction publication/classification will occur here). Currently the classifications are differentiated based on the `activePlanet.id`, which is fine as now we technically only support lightkurve features, however we will need to update this (sector/structure based as well) to support other content
* We may want to have classifications (on a certain anomaly/about (for non-planet/body anomalies)) as a requirement for certain structures...

### Planets/Telescopes
* Users could share their lightcurves that are generated as a result of their findings? Potentially the telescope screen allows them to put together custom instructions for notebook snippets?
- New classification methods will need to be dreamed up so that users don't need to write a paragraph explaining data every time they want to perform an action

We'll need to plan out the category[/ies] that the items will fit into.

# (Put into GP-11)
## And make sure to mark it as a blocker of SGV2-20

Crafting
Crafting will be an important concept for the creation & utilisation of items, both in this next sprint (planned to start on Monday 29th January 2024) and the long-term vision for Star Sailors. For now, I propose we follow a simple crafting structure:
 Raw material [combination] → base building block → tool/structure/vehicle or other entity
Down the line, I think we'll insert a tertiary step between "base block" and the final product. We'll also set up things like refineries, smelters, etc and recycling items.
For now, refineries/smelters will just exist as a crafting station that don't do anything for simplicity.
Recipe list
We'll try and keep things simple (especially early-game/early-development), but realistic, and based on the materials that can realistically be gleaned from the sort of terrestrial planets we'll be exploring. Down the line we'll insert things like gas planets & transport of rare materials between planets, for now every planet will have multiple sectors for every raw material.
For the telescope, which is the initial structure, I propose the following:
1. 1x Coal
2. 1x Iron
3. 1x Alloy (made up of gold, palladium, silver, etc → essentially trace "metals"). (I know that IRL these sorts of alloys are unlikely/impossible to form due to the nature of purity of Au, however this is just an early-stage setup to simplify the number of sectors users will have to explore. Potentially we will insert 2 materials per sector).
4. 1x Silicon (for circuit board, glass for the mirrors/reflectors)

Once a telescope has been built, it will be slightly operational (will double the range of sector exploration) land-based, and we can add functionality later for ground-based observations. A launchpad will be required to launch the 'scope and get the full functionality:
1. 1x Fuel (refined from 'water' → hydrazine). (Will provide unlimited fuel in effect, for now instances of launch pads will not have a fueling utility or column/variable)
2. 1x Iron

A telescope receiver will also be required:
1. 1x Silicon
2. 1x Alloy
3. 1x Iron

I'm unsure how crafting will occur, I think for simplicity we might base it around client-side for now (i.e. client app would check inventory and deduct values, rather than setting the recipes in the db and deducting them that way).

Raw materials
Every item that will be part of this first collection:
1. Silicon. Will be labelled as "Silicates" due to its extra utility/combinations i.e. quartz, glass, etc
2. Alloy
3. Iron
4. Fuel
5. Water
6. Coal
Components


---
# Current boards
Talking about overlap between tickets and boards (e.g. the currency system consists of things from backend, frontend and narrative) reminds me we probably need to overhaul the labels and confluence labels at some point very soon...
## Generating Planets & Content (GP-)
1. Containerise next & flask in Docker (GP-19)
		If we end up requiring Flask for V2.0 (and this is still not confirmed yet), we will need to containerise it all, so this ticket should be reviewed. Ideally we also do Supabase right from the start
		Currently experiencing issues with getting Flask routes to be accessible when we run it through a docker container so we will need to review that
		This should probably be moved into a new board
2. Basic currency system setup (GP-7)
		Should probably be moved into a content or narrative board
		I don't think we require a currency system (beyond a # of classifications) for V2.0 to fit the criteria I laid out (I do want the rest of the team to review the criteria however)
3. New globe component (GP-16)
		I think it's in the correct board for now
		I do need to chat with Rhys about how we work this. Potentially it's the same format as the ringed layout? Maybe something to build in later
4. GP-14 & GP-15 can be archived.
5. 

---



I want you to provide me with a list of directories to create to organise my notes, a list of properties for my obsidian vault e.g. tags, type, ticket (a link to a jira ticket), component (list of frontend/nextjs components), anomalies (list of citizen science modules mentioned/relevant), categories (e.g. frontend, backend, design, UI, deployment), modules (e.g. supabase, tailwind, flask), Projects (Epics/Projects)

Keep in mind I'll be documenting all my research, plans, designs, questions, jira tickets, sprint retrospectives, bugs, qa testing, etc here