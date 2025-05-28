---
sticker: lucide//skip-forward
---
> Simple goal: User actions produce a response from the system, which produces an opportunity for the user to respond, etc
> 
> Give something back to #scistarter / #Zooniverse this month

Continuing on from [[SSG-185]] && [[SSG-176]]

# Structure alerts
## Events
### Notification about upcoming storms
#SSG-179 , #Storms #Weather #WeatherEvents #Weather-Balloon 

Step 1:
Identify which storms or other weather events relate to each project

Step 2:
Formula for aggregation between #relatedClassifications & #WeatherEvents 

Step 3:
One weather event per week per planet. #Weather-Balloon shows these. This also fits into #SSG-182 ( #PlanetHunter completion rate)


We'll probably also need a formal, functional follow-up/finalisation of #SSM-139, to have something actually result from these storms.
1. If #biomass at appropriate level, opportunity for #Lightning #Storms 
2. Update #biomass and add #life


### Planet completion rate
#SSG-182
Firstly, identify which planets/terrariums are owned by the user (let's figure out ownership differences later, i.e. if you participate in a #Surveyor or a #Comments but not the original discovery). Component: #MySettlementsLocations 


Next:
1. Structures & construction on #PlanetGenerator 
2. Stardust counter in navbar, maybe? With tech points. Show inventory limits? Upgrade menu inside #Research #ResearchStation ?


> THREE.WebGLRenderer: Context Lost.

Issue - compare base/borderline pgen.

NOTE: revist #PostCards page, #toolbar #component 

# Terrariums/Customisations
## SSM-174: Planet aggregations
#SSM-174 #Terrarium #aggregator 
e.g #Planet #classificationConfiguration:
```json
{

"createdBy": null,

"planetType": "Terrestrial",

"structureId": null,

"temperature": "It's a real planet (Kepler-22b), apparently in the inner edge of its habitable zone, so let's say ~310K? , 310K",

"activePlanet": 4,

"commentInput": "Based on current scientific consensus, Terrestrial > Water world",

"exportedValue": {

"mass": 8.6,

"type": "",

"biome": "Rocky Highlands",

"radius": 1,

"density": 47.39,

"hasRings": false,

"salinity": 0.35,

"soilType": "rocky",

"landmarks": [

{

"type": "Mountain Peak",

"events": [],

"category": "terrestrial",

"image_link": "",

"coordinates": {

"x": 0.5,

"y": 0.8,

"z": 0.3

},

"visual_effect": "None",

"influence_type": "mountain",

"influence_radius": 0.5,

"classification_id": "LM-001",

"influence_strength": 0.7,

"influence_roughness": 0.5

},

{

"type": "Great Storm",

"events": [],

"category": "gaseous",

"image_link": "",

"coordinates": {

"x": -0.9931714278592942,

"y": -0.09067853925240746,

"z": 0.07340243458483099

},

"visual_effect": "Turbulence",

"influence_type": "vortex",

"influence_radius": 0.9621397649948124,

"classification_id": "LM-139",

"influence_strength": 0,

"influence_roughness": 0.6184464276642203

}

],

"cloudCount": 30,

"liquidType": "water",

"waterLevel": 0.65,

"soilTexture": "rough",

"temperature": 288,

"waterHeight": 0.65,

"biomassLevel": 0.2,

"liquidEnabled": true,

"mountainHeight": 0.6,

"plateTectonics": 0.8,

"terrainErosion": 0.3,

"surfaceRoughness": 0.5,

"volcanicActivity": 0.3,

"atmosphereStrength": 0.8,

"precipitationCompound": "water"

},

"Repeating dips": true,

"Dips with similar size": true,

"Dips aligned to one side": true

}
```

Composed of:
1. #comments relating to #surveyor values
2. Sub-classifications of

## SSP-74: Planet generator with events/landmarks
#SSP-74 #Generator #PlanetGenerator 
### SSP-66 - Landmarks, Events, Blotches
#SSP-66
We now have landmarks including events, the next step is the ability to create landmarks/events from each other. As well as converting the #WeatherEvents to follow the format of the #Landmarks 's #events .

Do events change points/textures in landmarks?

We can gradually increase the accuracy of the landmark/event texture as per #SSP-77 

### SSP-75: Multiple biomes
#SSP-75
Colours & shapes, more cloud shapes
Eventually improved textures for land vs ocean (SebLague)

Let's just add a biome value to each #Landmarks . Follow-up... - biome value is determine by the overall biome of the planet [parent] plus the effects of the specific landmark.
#### SSP-76
#SSP-76
Add #biomass value with image urls to the `landmark-types.ts` file:
```ts
export interface Landmark {

id: string

name: string

type: LandmarkType

biome?: string;
biomass goes: here...;

position: {

x: number // 0-1 normalized position on map

y: number // 0-1 normalized position on map

}

size: number // 0-1 normalized size

elevation: number // Elevation value at this point

description?: string

color?: string // Optional custom color

};
```
It should take in the full, [new] normalised biomass method from the terrarium, which identifies all #life (aka #biomass ) and identifies which biome it should flow from.

# Stardust
## Checkbacks
When rovers come back? What are they exploring/reviewing?

Landscapes - characters & content that pops up. Maybe something to do with mining? Construction of upgrades? Bring those #landscapes into #Landmarks ...propose a plan there

## Navbar
#SSG-181 #component #Components #Navbar #Navigator #Navigation 
We need to show the #MySettlementsLocations component somewhere...

## Research/unlockables (from milestones)
### What's going on here?
First, identify stardust across all missions, and then divide between categories.
Then, identify some common-sense things to upgrade, and how we show them.
Finally, propose ideas for showing all of this, and tying into the workflow of exploration, uploads, etc

### What are options for upgrades?
1. More frequent events - upgrade #Weather-Balloon 

So we need to show #Stardust, divided into categories, and then show upgrades, current info & a reason (justification) to upgrade.

### What do users start with by default?
1. The choice between a #Telescope , #Greenhouse & a #Weather-Balloon 
2. They are given a starter #Automatons and a starter #Probe which has no available customisation for now (see [[V3 Ideas Megadoc]]) #Far-Future #FutureTickets 
3. A spot on #Earth

Can we do something like a 'focused' or 'guide' mode (like in Voidpet) without compromising on user freedom?

![[Pasted image 20250417120551.png]]
![[Pasted image 20250417120601.png]]

### Tech tree - starter
Again, we go back to the idea of #Timer s and limits. So the first thing is seeing how many anomalies have been classified (I think this is the key metric, not the number of actions the user will make, because the anomalies are things that are found by the user).

Everything related to #upgrades goes into #researched table
#### "Weekly review"/"Weekly starter kit"
Cameras for #BiodomeStation s will always be activated, just for lore reasons (come on, if we're able to have near-instant travel, we can surely keep the cameras on), but we'll start users off with one set of sensors for each station.
> Let's link this in with the ideas around 'visual clutter' on the structure content e.g. 'camera count'

Telescopes can be set to 'interpret' receipts from, let's say, two source types (maybe Sunspots & Planets, or Planets/Lightkurves and Asteroids (Daily Minor Planet project)). They can send out probes to find data.

Weather balloons can (for now, at least) interpret weather signals on all terrariums, but can only identify one event per week (to-do: find lore reason for this)
- [ ] Determine lore reason for why weather balloons can only identify one event/terrarium/week at the start 🔽
Later, users will be able to interact with landmarks on other planets through specialised upgrades of their balloons (future).

![[Pasted image 20250419114639.png]]


## Structure upgrades
### Determining cameras in biodomestations
#cameras #Research #researched 
```tsx
New task:

create table public.researched (

id serial not null,

tech_type character varying(50) not null,

tech_id integer not null,

created_at timestamp without time zone null default CURRENT_TIMESTAMP,

user_id uuid null,

constraint researched_pkey primary key (id),

constraint researched_user_id_fkey foreign KEY (user_id) references profiles (id)

) TABLESPACE pg_default;
```
> I want you to create a component that identifies if the user...

Next thing to do - add stardust for completed milestones, alerts...
Does research take time?
Update -
1. We now have the ability to determine overall number of completed milestones (at least, for individual milestones)
2. Let's finish it off with 'community milestones too'
3. Then, let's show available upgrades in the tech tree...greyed out, for now
	1. Draw some ideas for appendages/upgrades - task [[]]
	2. Also, working on adding structure templates to landmarks...then maps, then mining and construction can begin! As well as flat/3d terrain views...bit by bit.
# Post-Classification pop-up
#classification #Classifications #ClassificationForm 

Let's give users a review of what they've done & earnt, any output (e.g. a new event), and some recommended next steps (statically set based on project, I think).

# Post-sprint
#Far-Future #FutureTickets #Tickets 
1. An Earth page showing greenhouse structures/stations
2. Integrate rover images into play with #AI4Mars ... #APPEEARs #Roverimg
3. Aggregations for other entities/anomalies e.g. #Asteroids 
4. The ability to trigger weather events
5. We also need the aggregators 100% working.
6. Can we do something w/ this? https://warpcast.com/keccers.eth/0x9a83c924
7. #edit/planets route should have the comments area so we can do surveyor comments
8. #PlanetGenerator events/time:
		
```
const formatTime = (timeInSeconds: number) => {
```

#Far-Future 
Look at the modular layout in PSS for ship building & research

## Definite
- [x] Update TotalPoints with new missions ⏫ ✅ 2025-04-22
- [x] Stardust needs to show points breakdown 🔼 ✅ 2025-05-05
- [ ] Message to users about what to do next - e.g. #PlanetCompletion
## To put into 'proper place' in this doc (later)
[Weather generator/events update with landmark templating](https://v0.dev/chat/fork-of-animated-weather-overlay-9lzHe34tRjK)