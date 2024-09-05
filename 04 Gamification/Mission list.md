---
sticker: lucide//brain-circuit
tags:
  - Missions
  - Tickets
  - Components
  - Gameplay
---
# Mission log
This will show all available missions, that are part of the chapters. These are organised into mission groups, for example "Mission Group 1" which refers to the missions/tasks part of the [[01 Onboarding|01 Onboarding]]

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
[[02 Citizen Modules|02 Citizen Modules]]
## Related
[[Timeline|Timeline]]
[[Tickets|Tickets]]