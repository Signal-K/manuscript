---
sticker: lucide//loader
tags:
  - Chapters
  - Chapter-1
  - Retrospective
  - Tickets
  - Tasks
---
## What really is left
1. Take sample dialogue from [[Chapter 1]]and introduce it into the `guideBot.tsx` file, get mission order correct
2. Go through dialogue dos & don'ts with Fred in [[15 September 2024]]
3. Any other `activeMission` configuration for [[Researching]]
4. Styling bug for #Automatons #Mining - we got rid of the 2x2 grid but still have the 1x3 for the controller/map scene
5. UI issues #Bugs -> #CaptnCosmos stretches too far to the left

## Archive

1. ~~All remaining #Tickets  (in SGV2 board)~~
2. ~~All remaining #Dialogue~~ 
	1. ~~Link ticket with [SGV2-132](https://signalk.atlassian.net/browse/SGV2-132)~~
	2. Add any missions to the API route and related mission component to match up with dialogue (`SGV2-129`)
3. Transition scene for loading [[01 Chapter 1]]
4. Transition scene for first classification in [[01 Chapter 1] + Repairing #Structure #Structures 
5. Transition scene into mining, repairing & then choosing your next thing to classify
	1. ~~Simplified mining OOO?~~
6. Anomaly ~~completion chart~~ & explanation [[Planet Generator]
7. Any onboarding/layout issues remaining in #Tickets 
8. ~~Final icons, background assets and more visuals~~
9. ~~Profile form [[01 Onboarding]~~
	1. This has been moved into the cleanup for [[01 Chapter 1]]
10. ~~Mission log -> clearer~~
11. ~~Thin notebook novelty ideas
	1. Greenhouse to show your discoveries (initially animals but later all #Anomalies )~~
12. ~~Component to show your classifications (by structure and overall)~~
	1. Show all of a certain type (example everything ALL your telescopes have discovered?)
13. ~~Popup menu/modal~~
	1. ~~Classification list~~ -> Ref `SGV2-195` ticket
	2. ~~Mission log~~
	3. ~~Inventory~~
		~~I think we'll just configure it all to just be a circular button which spins out into a menu, maybe with a bit of text to highlight it to new users~~...maybe Capt'n Cosmos's speech comes out of it?
14. ~~Get the dialogue to come out of the popup menu component~~
	1. Cosmos
15. Data source & ~~purpose (both narrative & IRL)~~
	1. Show "why" we're doing things in-game, IRL and the IRL source
16. ~~Fix how mineral deposits are created (create a limit, increase the quantity value not the number of rows. One deposit per mineral type)~~

**questions**
1. ~~What do we show/how do we show everything on mobile~~
2. ~~What is the relevance of planet searching using #Telescope in #Chapter-1~~ 

**to-do** (code-wise)
1. ~~Directory for all dialogue, put all dialogue under Capt'n Cosmos speech bubble~~
2. ~~Directory for comps used only in specific #Chapters  (e.g. #Chapter-1 Intro component)~~
3. ~~Put [[Mission list]] grouped together~~ 

~~Test:
1. Test active structure after completing a mission, researching a new module and then ensuring the `profiles.activeMission` and `activeStructure` are set correctly.~~

**smaller**
1. Loading time/spinner for Rover photos
2. Fuzzy effects e.g. comets
3. ~~Get `<MissionLogStarter...` to appear in the correct location on-screen~~
	1. ~~Decided to move this to the popup-menu~~
4. Method to change `<ActivePlanet />` and choose when to do so towards the end of Chapter 1, as well as determining "planet type" (introduce a surveyor chip)

**Bug reports**
1. ~~`ProgressBar` in #Onboarding window component~~
2. ~~Images not saving during [[01 Onboarding]] chapter - I think we'll just move to an automatic saving method like we have in #Chapter-1~~ 
3. Structures can't be opened, closed and then opened again without a refresh
	1. Do we just reset the state (not db field) for "activeStructure" when clicking out of the modal?
4. Inner modal not resizing correctly, I also think we should add a colour gradient or other decorative scope to make it stand out a bit more
5. "What do you think about..." form component
6. If there are multiple rovers on a user's [instance of a ] planet, the mining scene won't work
7. ~~Fix duplicate "burrowing owls" discriminator in the #zoodex structure modal~~

**Narrative issues**/tickets
1. Why are we classifying animals? Where do they come from?
2. Actually, why are we doing anything? This needs to be explained to the users specifically
	1. When the user chooses each mission, we need to explain to them exactly where the data comes from (from an in-game/narrative lore perspective, not in a literal sense), why they're classifying it, etc
3. Explain to the users their ability to keep classifying using their existing structures, move on to new ones, again why...from a "completing our understanding of your planet" perspective #Generator 
*Scope/content for the narrative*
```ts
{

id: 1370201,

name: "Initialise chapter 1",

description: '',

chapter: "1",

classificationModule: 'Mining' // Update this

},

{

id: 1370203,

name: 'Choose your first classification',

description: 'Fill me',

classificationModule: 'General',

chapter: '1'

},

{

id: 1370204,

name: 'Complete your first (chosen) classification',

description: 'As part of Chapter 1',

classificationModule: 'General',

chapter: '1'

},

{

id: 1370205,

name: 'Go mining - first iron',

classificationModule: 'Mining',

chapter: '1',

},

{

id: 1370206,

name: 'Repair the research structure',

description: 'As part of Chapter 1', // Also creates it

classificationModule: 'General',

chapter: '1',

},

{

id: 1370207,

name: 'Research a new technology',

classificationModule: 'General',

chapter: '1',

},

{

id: 1370208,

name: 'Second classification (different structure)',

classificationModule: 'General',

chapter: '1',

},

{

id: 1370209,

name: 'Transition to chapter 2',

chapter: '1',

},
```

From a structure perspective, here's what's going on with the missions:
```ts
const missions: UserActiveMission[] = [

{

id: 1,

name: 'Initialise Chapter 1',

starterMission: 1370201,

},

{

id: 2,

name: 'Choose your first classification',

starterMission: 1370203,

},

{

id: 3,

name: 'Complete your first (on-planet) classification',

starterMission: 1370204,

// structure: null, -> should point towards active structure based on what the user chose, which I believe is being done with the <Stats .../> component

},

{

id: 4,

name: 'Go mining', // Create an automaton structure if the user doesn't already have this

starterMission: 1370205,

structure: 3102,

createStructure: 3102,

mineralDepositToCreate: 15,

},

{

id: 5,

name: 'Repair the research structure',

starterMission: 1370206,

structure: 3106,

createStructure: 3106,

},

{

id: 6,

name: 'Research a new technology',

starterMission: 1370207,

structure: 3106,

},

{

id: 7,

name: 'Perform a second classification (second classification type)',

starterMission: 1370208,

},

];
```

List of structures:
```ts
{

id: 3102, name: 'Automaton station', description: 'View, control and upgrade all your automatons and rovers here', cost: 1, icon_url: '/assets/items/AutoController.png', ItemCategory: 'Structure', parentItem: 30, itemLevel: 1, locationType: 'Surface'

},

{

id: 3103, name: 'Telescope', description: 'Space-based observations & classifications', icon_url: '/assets/Items/Telescope.png', ItemCategory: 'Structure', locationType: 'Surface'

},

{

id: 3104, name: "Zoodex", description: "Populate your planet with some animals to gain an understanding of animal behaviour on your planet and aide local research back home", cost: 1, icon_url: "/assets/items/Pokedex.png", ItemCategory: "Structure", parentItem: null, itemLevel: 1, locationType: "Surface"

},

{

id: 3105,

name: "LIDAR",

// description: 'This tool is used to scan the surface of your planet and create a 3D model of the terrain', -- This is cool, but not what we're using lidar for yet (thanks copilot)

description: "Collect and study weather events and entities",

icon_url: "/assets/items/Scoper.png",

ItemCategory: "Structure",

locationType: 'Surface',

},

{

id: 3106,

name: "Research Station",

description: "Unlock new technology and research",

icon_url: "/assets/items/Research.png",

ItemCategory: "Structure",

locationType: 'Surface',

},
```


There should be a function created that when we open the Cosmos Compendium, it checks for any missions that haven't been added properly and then performs them.
We'll need to add some additional configuration for classifications so that we can differentiate between those done during #Onboarding and those done during #Chapter-1 / #Chapters 