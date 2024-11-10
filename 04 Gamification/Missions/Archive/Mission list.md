---
sticker: lucide//brain-circuit
tags:
  - Missions
  - Tickets
  - Components
  - Gameplay
---
# Mission log
This will show all available missions, that are part of the chapters. These are organised into mission groups, for example "Mission Group 1" which refers to the missions/tasks part of the [[01 Onboarding]]

They'll also be organised into classification/module groups, we'll show the first mission for each module and the entirety of a group, have a filter, and then take the user's actions into account

## Syntax
### `CitizenScienceModule`
```ts
const modules: CitizenScienceModule[] = [

{

id: 1, name: "Planet Candidate Identification", level: 1, starterMission: 1372001,

},

{

id: 2, name: "Animal Observations", level: 1, starterMission: 1370202,

},

{

id: 21, name: "Animal uploader", level: 1, starterMission: 1370202,

},

{

id: 4, name: "Cloud identification", level: 1, starterMission: 137121301,

},

{

id: 5, name: "Map the terrain (of your planet)", level: 1, starterMission: 13714101,

},

];
```

Everything to do with animals, for example, has an id that starts with "2.."
[[02 Citizen Modules]]

# Overall mission list
(excluding onboarding missions)
## Classifications
### Telescope
1. Repairing your telescope `1372002`
2. First 'scope classification (after onboarding) `1372001` 
### Zoodex

What missions should **not** be duplicated?
1. `1370202`
2. `1370299` -> Integration point between #Chapter-1 & #Chapter-2 
3. `1370201`

### Init list
#Chapter-1  (after #Onboarding )
1. Start #Chapter-1  -> choose first classification option
2. Make first #Classifications -> 1 of `1370202`, `1372001`, `1372001`, `13714101`
3. First #Mining option
4. First repair (again, is every structure being repaired or is it just the first #Structure the user initialises? If option 2, we need to include this information in the `missions.configuration` instance's)
5. Researching -> initialisation of #Research #Structure and first research ticket
6. Any subsequent missions the user wants to do
7. Finish draft/initial picture of your planet (combine with the #Generator from the #Onboarding  )
8. User picks the next thing they want to do in #Research , end #Chapter-1 and init #Chapter-2  (separate missions)

#### Flow
`1370201` - once (initialise #Chapter-1 )
`1370203` - once (and give them the corresponding research mission, too. Adjust it so that structures need to be researched before their inner modals are functional)
`1370202`, `1372001`, `1372001`, `13714101` - one of; then `1370204` for completing a mission 
`1370205` (user is directed to the broken research structure, they repair it (set this as the active mission))
`1370206` (user researches a new tech) - once. We'll have a list of missions for all research topics (and show their researched items in another modal)
`1370202`, `1372001`, `1372001`, `13714101` - one+ of (has to be a different one to the one they did in step 3)

Show the #Generator and then init #Chapter-2 


##### Pattern for #Dialogue 
[[What's left]]
1. If user has missions: `1370201`:
	1. Set `1370203` as the `activeMission`
	2. Show the component to select their starter classification mission
	3. Show dialogue about choosing their mission, go into enough detail so that the change component in [[What's left]] isn't required
3. If user has missions: `1370201`, `13720203`:
	3. Set `1370204` as the `activeMission`
	1. Show the structures (already done)
	2. Dialogue - just point towards the relevant structure
4. If user has missions: `1370201`, `13720203`, `1370204` :
	1. Set `1370205` as the `activeMission`
	2. Dialogue - point towards Automaton structure (mining scene)
	3. Show structures, showing automaton structure as the active mission (create a mission and configuration in the modules)
5. If user has missions: `1370201`, `13720203`, `1370204`, `1370205` :
	1. Set `1370206` as the `activeMission`
	2. Create item `3106` with a `configuration` of `"Uses": 0`
	3. Set the #Research  #Structure as the activeMission
	4. Dialogue for repairing it with the iron mined in the previous mission
6. If user has missions: `1370201`, `13720203`, `1370204`, `1370205`, `1370206` :
	1. Set `1370207` as the `activeMission`
	2. #Research #Structure is still the `activeMission`
	3. Dialogue explaining to the user that they still need to research another tech and classify using it
7. If user has missions: `1370201`, `13720203`, `1370204`, `1370205`, `1370206` , `1370206`:
	1. Set `1370208` as the `activeMission`
	2. Set the newly created structure as the `activeMission`
	3. Dialogue for the user to go through the new structure
8. If the user has missions: `1370201`, `1370203`, `1370204`, `1370205`, `1370206`, `1370207`:
	1. Set `1370209` as the `activeMission`
	2. Dialogue - user can research other structures, do some more mining, or finish up (note - Fred needs to supply info for what we say here as we don't actually have anything for #Chapter-2 initialisation yet)
	3. Chapter 2 init? ++

Dialogue component in `CaptnCosmos` dialogue box should have a button to "dismiss" or "start the mission", this will update the `profiles.activeMission` value, add anything required to the `inventory` dB table and then set the status of the text-wrapper to closed/null. So we need to create a new object, have the text formatted correctly and then move all current (half-baked) functionality into the new object. We'll also need to link up `/api/citizen/modules` with `/api/gameplay/missions/active`.

Next step to do:
1. Allow users to reset their `profiles.activeMission` value to the same value
2. Create capacity to add `mineralDeposits` entries in missions
3. Add the dialogue

## Related
[[Timeline]]
[[Tickets]]