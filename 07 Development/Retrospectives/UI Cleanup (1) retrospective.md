---
sticker: emoji//1f441-fe0f
connie-publish: true
connie-page-id: "28606490"
tags:
  - Editing
---
> The goal of this sprint was to get the missions all done in the index route, make things clearer and easier to follow. We achieved most of that and now have a plan for the final steps for a soft launch.

We need to introduce a hot refresh of the components every time a mission is completed so that we don't have to manually refresh the pages.

Rocks, soil, atmosphere

I'd recommend taking a look at [[Global & Internal To-Do]] for some things that are left over...

# The big issue - the tutorial/onboarding
[[Finished tutorials & unlimited data]]
The issue that I have is we're targeting this as a game, so we can't make a tutorial like a typical citizen science product would have, as that's way too complex with too much boilerplate and it won't be engaging. However, there is still a lot of information we need to provide to our users:

We start off with the users picking their planet, filling in their profile, etc.
Here's the full mission list, which sort of serves as a guide to their first steps in the game:

```ts
const missions: Mission[] = [
    { id: 1, name: "Pick planet", description: "Select your starting planet", rewards: [29] }, // Possibly the user should get something, but really they're already getting a planet, so... | After further consideration for the order of missions, I think that giving the spaceship and then the rover will be a good option
    { id: 2, name: "Complete profile", description: "Fill in your profile data", rewards: [22] }, // Give them a rover/automaton without a location, we'll create a button that keeps track of the item that was created and show the user an option to "place" un-locationised items/structures
    { id: 3, name: "Go to planet", description: "Land on your home planet", rewards: [12] }, // Empty/stub mission, purely to determine if the user visits their planet. | Will give the user a base telescope.
    { id: 4, name: "Build vehicle structure", description: "Now you do this, you'll be able to create automatons", rewards: [] }, // Empty/stub mission, purely for the user to make the Vehicle Structure. Will give them an automaton, however, as we currently don't have a crafting recipe for it. Actually, we don't need to do this, as the first automaton is always fee (see Automaton.tsx)
    { id: 5, name: "First automaton", description: "Build your first automaton to explore your planet", rewards: [13, 13, 13, 16, 16] }, // Give them the resources required to build the Telescope Signal Receiver
    { id: 6, name: "Deploy automaton", description: "Deploy an automaton for the first time", rewards: [13, 13, 15]}, // User will receive the components required to build item id 14, as well as whatever the automaton finds
    { id: 7, name: "Build telescope", description: "Build a telescope & subsequent modules to learn more about your planet", rewards: [13]}, // Meaningless/stub reward
    { id: 8, name: "Make classification", description: "Classify the validity of your planet by looking at your TIC ID", rewards: [13, 13, 13, 16] ,}, // Gives the user the constituent parts to make a surveyor module for their telescope
    { id: 9, name: "Collect resources part 2", description: "Collect resources to build your mining station", rewards: [13]},
    { id: 10, name: "Build mining station", description: "By doing this you can now collect omega resources", rewards: []}, // Not included
    { id: 11, name: "Collect resources from station", description: "You can now build your cloud-spotting telescope!", rewards: []},
    { id: 12, name: "Build Meteorology tool", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 13, name: "Create cloud classification", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 14, name: "Collect resources for camera module", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 15, name: "Craft camera module", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 16, name: "Craft camera receiver station", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 17, name: "Collect a photo", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 18, name: "Make classification of photo", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 19, name: "Go mining for surveyor parts", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 20, name: "Build surveyor structure", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 21, name: "Make surveyor classification", description: "You can now classify clouds on your planet!", rewards: []},
];
```

However, users may just only want to classify planet candidates, so after mission 8, we give them the option to just continue classifying planets.

Users need to understand the basics of building structures to get data to classify, deploying automatons to collect resources, etc

Once users have finished mission 8, their automatons can be deployed where they can choose the item they're mining (by default they just mine coal).