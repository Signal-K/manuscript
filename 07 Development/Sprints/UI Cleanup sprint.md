---
tags:
  - Sprint-Planning
  - Sprints
sticker: emoji//1f429
---
# Things to look into
[Pre-Sprint 2 | Questions](obsidian://open?vault=Liam's%20vault&file=02%20Design%2FQuestions%2FPre-Sprint%202) 
[[Second Mission Group]]
1. Entity switcher -> overflow for more than 2/3 automatons/structures
2. Rich-context background images
3. Context vs Parent menu items

I think the first thing we'll want to do will be to set up the overlays
# State of the user - where are we at?
Now that our users have made a handful of classifications and have started to populate their world, I want to start introducing the feed/content reading views and some options for them to expand their world, while of course also fixing the UI issues & solving problems that have been described and discovered/caused as part of the first two sprints.

(From [[Second Mission Group]]):
> So I think we'll take them back to the home page initially and maybe have a toolbar there with some info along the lines of "you've completed your first part of the tutorial! You can now go [here] to do the next part!". Additionally, we can also give our users the option to just classify TIC Ids if that's all they want to do for now. This means we'll have to add in a function that fetches random lightcurve images, as currently the api only pulls in pre-defined images that are matched to the TIC ID [configuration] value of the anomaly in the `anomalies` table.

So I think we should add this toolbar/ribbon as a priority. Let's make it responsive

# Components to update
* Travel format - animation, show destination & distance
* Create a crafting grid/dedicated crafting component that will take the resources in the inventory and the structure to be crafted
* See full list at [[First Mission Group - SGV2-40 Retrospective]]
* Create unified feeds for all citizen science modules & update

# Missions to update
## Mission 2
### Mission 2.2 -> Mining Station
> I want to be able to declare it with an option value, called "target" Target will specify the desired resources that the user needs to get to the next stage. For example, when calling this component for the first time in the app, we need to have a row in the `inventory` table where `owner` = session.user.id, `anomaly` = activePlanet.id, `item` = 11, and `quantity` > 0 The component should fetch the user's inventory at the start, and if they have the required row, then it returns an extra bit of text in the main modal/component, a button saying "you have the required resources" If the user doesn't, it makes a note of how many resources are required to get to the target (here, we need 1 piece of coal), and then when the user deploys the station, it calculates how long until the 1 piece of coal is mined (should be less than a minute). Once it determines the station has been deployed long enough for the resource to be generated, it says "resources ready".

Currently there's no context on the `MiningStation` structure component.

This sprint will start on the 16th of June (2024) and have the following goals (subject to change):
1. First two mission groups should be clear and easy for all new users to follow
2. Update components from those mission groups to fit in more with the new Figma-voidpet design
3. Improve all other operations & services being interacted with in the current form(at)

> There should be an interface design sketched out for what the long-term UI could look like (imagine a 2d Minecraft forge design). Additionally, we will also create a related ticket for a card gallery/carousel for the components - SGV2-65



```
"use client";

  

import React, { useEffect, useState } from "react";

import { useSession, useSupabaseClient } from "@supabase/auth-helpers-react";

import { useActivePlanet } from "@/context/ActivePlanet";

  

import { Button } from "@/components/ui/button";

import { CreateCloudClassification } from "@/Classifications/ClassificationForm";

  

interface OwnedItem {

id: string;

item: string;

quantity: number;

notes?: string;

time_of_deploy?: string;

}

  

interface UserStructure {

id: number;

item: number;

name: string;

description: string;

cost: number;

icon_url: string;

ItemCategory: string;

parentItem: number | null;

itemLevel: number;

};

  

interface MiningStructureModalProps {

isOpen: boolean;

onClose: () => void;

ownedItem: OwnedItem;

structure: UserStructure;

};

  

export function MeteorologyToolPlaceable() {

const supabase = useSupabaseClient();

const session = useSession();

const { activePlanet } = useActivePlanet();

const [userStructure, setUserStructure] = useState<{

ownedItem: OwnedItem;

structure: UserStructure;

id: number;

time_of_deploy?: string;

}[]>([]);

const [loading, setLoading] = useState<boolean>(false);

  

async function activateStation() {

if (userStructure.length > 0) {

const { data, error } = await supabase

.from("inventory")

.update({ time_of_deploy: new Date().toISOString() })

.eq("id", userStructure[0].ownedItem.id);

  

if (error) {

console.error("Error activating station: ", error);

return;

}

  

console.log("Mining station activated: ", data);

  

// Update the state to reflect the new time_of_deploy

setUserStructure((prevState) => {

const updatedState = [...prevState];

updatedState[0].ownedItem.time_of_deploy = new Date().toISOString();

return updatedState;

});

}

}

  

async function claimRewards() {

try {

if (

userStructure.length > 0 &&

userStructure[0]?.ownedItem?.time_of_deploy

) {

const deployTime = new Date(

userStructure[0].ownedItem.time_of_deploy

).getTime();

const currentTime = new Date().getTime();

const timeDifference = currentTime - deployTime;

const rewardQuantity = Math.floor(timeDifference / 1000) * 2; // Convert milliseconds to seconds

  

if (rewardQuantity > 0) {

const { data: insertData, error: insertError } = await supabase

.from("inventory")

.insert([

{

owner: session?.user.id,

item: 11, // Assuming the item ID for rewards is 11

quantity: rewardQuantity,

anomaly: activePlanet?.id,

notes: `Reward from mining station id: ${userStructure[0].ownedItem?.id}`,

},

]);

  

if (insertError) {

throw insertError;

}

  

console.log("Rewards inserted: ", insertData);

  

const { data: updateData, error: updateError } = await supabase

.from("inventory")

.update({ time_of_deploy: null })

.eq("id", userStructure[0].ownedItem.id);

  

if (updateError) {

throw updateError;

}

  

console.log("Station deactivated: ", updateData);

} else {

console.log("No rewards to claim.");

}

}

} catch (error: any) {

console.error("Error claiming rewards: ", error.message);

}

}

  

const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL;

const imageUrl = `${supabaseUrl}/storage/v1/object/public/citiCloud/${activePlanet?.id}/cloud.png`;

  

async function fetchData() {

if (session && activePlanet) {

try {

const { data: ownedItemsData, error: ownedItemsError } = await supabase

.from("inventory")

.select("id, item, quantity, notes, time_of_deploy")

.eq("anomaly", activePlanet.id)

.eq("item", 26)

.eq("owner", session.user.id); // Ensure we fetch only items owned by the current user

  

if (ownedItemsError) {

throw ownedItemsError;

}

  

if (ownedItemsData && ownedItemsData.length > 0) {

const ownedItem = ownedItemsData[0];

  

const { data: structureData, error: structureError } = await supabase

.from("inventory")

.select("*")

.eq("item", ownedItem.item)

.limit(1);

  

if (structureError) {

throw structureError;

}

  

if (structureData && structureData.length > 0) {

const structure = structureData[0];

setUserStructure([{ ownedItem, structure, id: structure.id }]);

}

}

} catch (error: any) {

console.error(error);

}

}

}

  

useEffect(() => {

fetchData();

}, [session, activePlanet]);

  

return (

<>

{userStructure.length > 0 && (

<div className="bg-white text-gray-900 p-8 rounded-xl shadow-lg max-w-4xl mx-auto">

<div className="grid grid-cols-1 md:grid-cols-2 gap-8">

<div>

<div className="bg-gray-100 p-6 rounded-xl grid grid-cols-2 gap-6">

<span className="font-medium">On planet</span>

<div className="flex items-center gap-3">

<GemIcon className="w-7 h-7 text-indigo-500" />

<span className="font-medium">Coal</span>

<div className="text-right text-lg font-medium">250</div>

</div>

<div className="flex items-center gap-3">

<CuboidIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Silicon</span>

<div className="text-right text-lg font-medium">500</div>

</div>

<div className="flex items-center gap-3">

<LeafIcon className="w-7 h-7 text-green-500" />

<span className="font-medium">Organics</span>

<div className="text-right text-lg font-medium">100</div>

</div>

<div className="flex items-center gap-3">

<BoltIcon className="w-7 h-7 text-yellow-500" />

<span className="font-medium">Energy</span>

<div className="text-right text-lg font-medium">75</div>

</div>

</div>

</div>

<div>

<div className="bg-gray-100 p-6 rounded-xl grid grid-cols-2 gap-6">

<span className="font-medium">In Production</span>

<div className="flex items-center gap-3">

<GemIcon className="w-7 h-7 text-indigo-500" />

<span className="font-medium">Coal</span>

<div className="text-right text-lg font-medium">0</div>

</div>

<div className="flex items-center gap-3">

<CuboidIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Silicon</span>

<div className="text-right text-lg font-medium">0</div>

</div>

<div className="flex items-center gap-3">

<LeafIcon className="w-7 h-7 text-green-500" />

<span className="font-medium">Organics</span>

<div className="text-right text-lg font-medium">0</div>

</div>

<div className="flex items-center gap-3">

<BoltIcon className="w-7 h-7 text-yellow-500" />

<span className="font-medium">Energy</span>

<div className="text-right text-lg font-medium">0</div>

</div>

</div>

</div>

</div>

<div className="mt-8 bg-gray-100 p-6 rounded-xl grid grid-cols-2 md:grid-cols-4 gap-6">

<div className="flex items-center gap-3">

<GaugeIcon className="w-7 h-7 text-blue-500" />

<img

src={imageUrl}

alt={`Active Planet ${activePlanet?.id}`}

className="w-full h-auto"

/>

<CreateCloudClassification assetMentioned={imageUrl} />

{userStructure[0].structure.name}

</div>

<div className="flex items-center gap-3">

<CuboidIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Storage Capacity</span>

<div className="text-right text-lg font-medium">1000 units</div>

</div>

<div className="flex items-center gap-3">

<WrenchIcon className="w-7 h-7 text-gray-500" />

<span className="font-medium">Equipment Level</span>

<div className="text-right text-lg font-medium">3</div>

</div>

<div className="flex items-center gap-3">

<PinIcon className="w-7 h-7 text-indigo-500" />

<span className="font-medium">Tech Level</span>

<div className="text-right text-lg font-medium">2</div>

</div>

</div>

<div className="mt-8 bg-gray-100 p-6 rounded-xl grid grid-cols-2 md:grid-cols-4 gap-6">

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

<DrillIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Mining Drill</span>

</div>

<Button size="sm" variant="outline">

Upgrade

</Button>

</div>

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

<CombineIcon className="w-7 h-7 text-gray-500" />

<span className="font-medium">Conveyor Belt</span>

</div>

<Button

onClick={activateStation}

disabled={loading || !!userStructure[0].ownedItem.time_of_deploy}

size="sm"

variant="outline"

>

{userStructure[0].ownedItem.time_of_deploy

? "Station Active"

: "Activate Station"}

</Button>

</div>

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

{/* <TruckIcon className="w-7 h-7 text-blue-500" /> */}

<span className="font-medium">Transport Truck</span>

</div>

<Button size="sm" variant="outline">

Upgrade

</Button>

</div>

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

{/* <BuildingIcon className="w-7 h-7 text-indigo-500" /> */}

<span className="font-medium">Storage Facility</span>

</div>

<Button onClick={claimRewards} disabled={loading} size="sm" variant="outline">

Collect rewards

</Button>

</div>

</div>

</div>

)}

</>

);

}

  
  

export default function MiningStationPlaceable() {

const supabase = useSupabaseClient();

const session = useSession();

  

const { activePlanet } = useActivePlanet();

  

const [userStructure, setUserStructure] = useState<{ ownedItem: OwnedItem; structure: UserStructure; id: number; time_of_deploy?: string }[]>([]);

const [loading, setLoading] = useState<boolean>(false);

  

async function activateStation() {

if (userStructure != null) {

const { data, error } = await supabase

.from("inventory")

.update({ time_of_deploy: new Date().toISOString() })

.eq('id', userStructure[0]?.ownedItem.id);

  

if (error) {

console.error('Error activating station: ', error);

return;

};

  

console.log('Mining station activated: ', data);

  

// Update the state to reflect the new time_of_deploy

setUserStructure(prevState => {

const updatedState = [...prevState];

updatedState[0].ownedItem.time_of_deploy = new Date().toISOString();

return updatedState;

});

};

};

  

async function claimRewards() {

try {

if (userStructure.length > 0 && userStructure[0]?.ownedItem?.time_of_deploy) {

const deployTime = new Date(userStructure[0].ownedItem.time_of_deploy).getTime();

const currentTime = new Date().getTime();

const timeDifference = currentTime - deployTime;

const rewardQuantity = Math.floor(timeDifference / 1000) * 2; // Convert milliseconds to seconds

if (rewardQuantity > 0) {

const { data: insertData, error: insertError } = await supabase

.from("inventory")

.insert([

{

owner: session?.user.id,

item: 11, // Assuming the item ID for rewards is 11

quantity: rewardQuantity,

anomaly: activePlanet?.id,

notes: `Reward from mining station id: ${userStructure[0].ownedItem?.id}`,

},

]);

if (insertError) {

throw insertError;

}

console.log('Rewards inserted: ', insertData);

const { data: updateData, error: updateError } = await supabase

.from('inventory')

.update({ time_of_deploy: null })

.eq('id', userStructure[0].ownedItem.id);

if (updateError) {

throw updateError;

}

console.log('Station deactivated: ', updateData);

} else {

console.log('No rewards to claim.');

};

};

} catch (error: any) {

console.error('Error claiming rewards: ', error.message);

};

};

  

const [requiredResourcesQuantity, setRequiredResourcesQuantity] = useState<number | null>(null);

const [hasRequiredResources, setHasRequiredResources] = useState<boolean>(false);

  

async function fetchData() {

if (session && activePlanet) {

try {

const { data: ownedItemsData, error: ownedItemsError } = await supabase

.from("inventory")

.select("id, item, quantity, notes, time_of_deploy")

.eq("anomaly", activePlanet.id)

.eq("item", 30);

  

if (ownedItemsError) {

throw ownedItemsError;

}

  

if (ownedItemsData && ownedItemsData.length > 0) {

const ownedItem = ownedItemsData[0];

  

const { data: structureData, error: structureError } = await supabase

.from("inventory")

.select("*")

.eq("item", ownedItem.item)

.limit(1);

  

if (structureError) {

throw structureError;

}

  

if (structureData && structureData.length > 0) {

const structure = structureData[0];

setUserStructure([{ ownedItem, structure, id: structure.id }]);

};

};

} catch (error: any) {

console.error(error);

};

}

}

  

useEffect(() => {

fetchData();

}, [session, activePlanet, supabase]);

  

return (

<>

{userStructure.length > 0 && (

<div className="bg-white text-gray-900 p-8 rounded-xl shadow-lg max-w-4xl mx-auto">

<div className="grid grid-cols-1 md:grid-cols-2 gap-8">

<div>

<div className="bg-gray-100 p-6 rounded-xl grid grid-cols-2 gap-6">

<span className="font-medium">On planet</span>

<div className="flex items-center gap-3">

<GemIcon className="w-7 h-7 text-indigo-500" />

<span className="font-medium">Coal</span>

<div className="text-right text-lg font-medium">250</div>

</div>

<div className="flex items-center gap-3">

<CuboidIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Silicon</span>

<div className="text-right text-lg font-medium">500</div>

</div>

<div className="flex items-center gap-3">

<LeafIcon className="w-7 h-7 text-green-500" />

<span className="font-medium">Organics</span>

<div className="text-right text-lg font-medium">100</div>

</div>

<div className="flex items-center gap-3">

<BoltIcon className="w-7 h-7 text-yellow-500" />

<span className="font-medium">Energy</span>

<div className="text-right text-lg font-medium">75</div>

</div>

</div>

</div>

<div>

<div className="bg-gray-100 p-6 rounded-xl grid grid-cols-2 gap-6">

<span className="font-medium">In Production</span>

<div className="flex items-center gap-3">

<GemIcon className="w-7 h-7 text-indigo-500" />

<span className="font-medium">Coal</span>

<div className="text-right text-lg font-medium">0</div>

</div>

<div className="flex items-center gap-3">

<CuboidIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Silicon</span>

<div className="text-right text-lg font-medium">0</div>

</div>

<div className="flex items-center gap-3">

<LeafIcon className="w-7 h-7 text-green-500" />

<span className="font-medium">Organics</span>

<div className="text-right text-lg font-medium">0</div>

</div>

<div className="flex items-center gap-3">

<BoltIcon className="w-7 h-7 text-yellow-500" />

<span className="font-medium">Energy</span>

<div className="text-right text-lg font-medium">0</div>

</div>

</div>

</div>

</div>

<div className="mt-8 bg-gray-100 p-6 rounded-xl grid grid-cols-2 md:grid-cols-4 gap-6">

<div className="flex items-center gap-3">

<GaugeIcon className="w-7 h-7 text-blue-500" />

<span className="font-medium">Production Rate</span>

<div className="text-right text-lg font-medium">25 units/hr</div>

</div>

<div className="flex items-center gap-3">

<CuboidIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Storage Capacity</span>

<div className="text-right text-lg font-medium">1000 units</div>

</div>

<div className="flex items-center gap-3">

<WrenchIcon className="w-7 h-7 text-gray-500" />

<span className="font-medium">Equipment Level</span>

<div className="text-right text-lg font-medium">3</div>

</div>

<div className="flex items-center gap-3">

<PinIcon className="w-7 h-7 text-indigo-500" />

<span className="font-medium">Tech Level</span>

<div className="text-right text-lg font-medium">2</div>

</div>

</div>

<div className="mt-8 bg-gray-100 p-6 rounded-xl grid grid-cols-2 md:grid-cols-4 gap-6">

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

<DrillIcon className="w-7 h-7 text-amber-500" />

<span className="font-medium">Mining Drill</span>

</div>

<Button size="sm" variant="outline">

Upgrade

</Button>

</div>

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

<CombineIcon className="w-7 h-7 text-gray-500" />

<span className="font-medium">Conveyor Belt</span>

</div>

<Button onClick={activateStation} disabled={loading || !!userStructure[0].ownedItem.time_of_deploy} size="sm" variant="outline">

{userStructure[0].ownedItem.time_of_deploy ? 'Station Active' : 'Activate Station'}

</Button>

</div>

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

{/* <TruckIcon className="w-7 h-7 text-blue-500" /> */}

<span className="font-medium">Transport Truck</span>

</div>

<Button size="sm" variant="outline">

Upgrade

</Button>

</div>

<div className="flex flex-col items-center gap-3">

<div className="flex items-center gap-3">

{/* <BuildingIcon className="w-7 h-7 text-indigo-500" /> */}

<span className="font-medium">Storage Facility</span>

</div>

<Button onClick={claimRewards} disabled={loading} size="sm" variant="outline">

Collect rewards

</Button>

</div>

</div>

</div>

// <MiningStructureModal

// isOpen={true}

// onClose={() => {}}

// ownedItem={userStructure[0].ownedItem}

// structure={userStructure[0].structure}

// />

)}

</>

);

};

  


```