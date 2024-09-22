---
connie-publish: true
sticker: lucide//focus
connie-page-id: "31227905"
---
# Simple instructions
Upon starting the app (for the first time)
1. Minimal background, "choose your starter" CTA, three options
2. Different background, option for additional context when you select each one. 
3. "Animation/effect" when selecting your starter, give it a name
4. Survey modal -> "what do you want to work on?"

Tutorial: check in
"Tap your voidpet & check in! - your garden of consciousness is home to creatures like your friend, Warbly. Why don't you go say hi to start?" - points to the pet
* Modal pops up, with the different buttons, stats for the modal (level, species name, group (e.g. fire)). Right now all we can do is check in (share mood)
* User selects an option, and they get a reward (full modal)

"Tap your sprout to water it. - Growing a lush oasis will make your garden hospitable to visitors. To attract new species of voidpets, you'll want to nurture your plants at least once a day"
* User clicks on the plant (sprout), is directed to it via a pointing hand
* Modal pops up with the main buttons and stats (right now, the plant has a level, icon and name)
	* There is a different background (full-screen, not the modal) when interacting further (i.e. clicking on the main buttons), I think I'll just stick with the overlay layout
* After user describes their emotions, animation to "tap and hold to make it rain"
	* User is given rewards & notifications: "Voidpets nearby. - 3 new visitors approach", increased level (for plant), increased resources (nutrients, experience [which is directed towards a pet])

"Befriend a new pet"
* User is directed to click on an unnamed pet
* Given the option to talk with the new pet, given two possible answers, after doing so they have the option to befriend the new pet
* "New species discovered" modal (and new vivid)

"Plant your first tree. - Different species of Voidpets like different plants. To meet them all, you will need to fill your garden with different types of trees and flowers"
* User goes through the main menu to the "plants" section
* This then highlights the spaces that are currently available to plant new plants
* User chooses a new plant and then moves out of "edit mode"

"Change your plant's colour. - Some rare Voidpets are called vivid variants, and they come in many different colours. To attract more vivid voidpets, it helps to have the vivid trees that match them"
* User is directed to spend some void matter to create a coloured cloud and can then change the coating

"You're all good to go. - Your garden of consciousness will soon be home to all sorts of different creatures, so be sure to check back every day and nourish it well!"


# Conversion of Star Sailors missions/events
Right now, I've got everything defined into a "missions" table, however it would more accurately be described as a list of "first [instances of] events", in that it simply records when the user first did an action, like placing their first structure or using their first automaton to mine things. This is so that we know what mechanics the user has performed so we can understand their familiarity with the mechanics and can determine what components to show to them; i.e. we don't want to show them the modal to build their telescope if they haven't collected any resources (using their automatons) first.

I'm using the Voidpet app as my main source of inspiration for the UI and the onboarding, and I've just gone through it again and made these notes on the onboarding. It introduces the user to the pets, the plants, shows them around the app, and how they "progress" in the game/app. Here are my notes:

Upon starting the app (for the first time)
1. Minimal background, "choose your starter" CTA, three options
2. Different background, option for additional context when you select each one. 
3. "Animation/effect" when selecting your starter, give it a name
4. Survey modal -> "what do you want to work on?"

Tutorial: check in
"Tap your voidpet & check in! - your garden of consciousness is home to creatures like your friend, Warbly. Why don't you go say hi to start?" - points to the pet
* Modal pops up, with the different buttons, stats for the modal (level, species name, group (e.g. fire)). Right now all we can do is check in (share mood)
* User selects an option, and they get a reward (full modal)

"Tap your sprout to water it. - Growing a lush oasis will make your garden hospitable to visitors. To attract new species of voidpets, you'll want to nurture your plants at least once a day"
* User clicks on the plant (sprout), is directed to it via a pointing hand
* Modal pops up with the main buttons and stats (right now, the plant has a level, icon and name)
	* There is a different background (full-screen, not the modal) when interacting further (i.e. clicking on the main buttons), I think I'll just stick with the overlay layout
* After user describes their emotions, animation to "tap and hold to make it rain"
	* User is given rewards & notifications: "Voidpets nearby. - 3 new visitors approach", increased level (for plant), increased resources (nutrients, experience [which is directed towards a pet])

"Befriend a new pet"
* User is directed to click on an unnamed pet
* Given the option to talk with the new pet, given two possible answers, after doing so they have the option to befriend the new pet
* "New species discovered" modal (and new vivid)

"Plant your first tree. - Different species of Voidpets like different plants. To meet them all, you will need to fill your garden with different types of trees and flowers"
* User goes through the main menu to the "plants" section
* This then highlights the spaces that are currently available to plant new plants
* User chooses a new plant and then moves out of "edit mode"

"Change your plant's colour. - Some rare Voidpets are called vivid variants, and they come in many different colours. To attract more vivid voidpets, it helps to have the vivid trees that match them"
* User is directed to spend some void matter to create a coloured cloud and can then change the coating

"You're all good to go. - Your garden of consciousness will soon be home to all sorts of different creatures, so be sure to check back every day and nourish it well!"
---End of voidpet tutorial---

Here is the mission list for Star Sailors (currently):
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

Here's what we cover:
1. Signing up and picking your planet (you have 1 of 6 to choose from)
2. Filling in your profile
3. Travelling to your planet
4. Introduce them to building & deploying structures (note that some structures are given to the user but are not "located" in a particular setting, these structures are "undeployed" until placed onto a planet/setting. Most structures that are created are automatically 'deployed'. Note that this terminology is also used when referring to automatons that are actively collecting resources (i.e. those automatons/rovers are also "deployed"), however, it's completely different.
5. Teach the user how to activate certain items (like automatons, deploying them; or structures, using them to collect the data to classify), and how to make classifications
6. Teach the user how to upgrade their automatons and other structures.

A note that everything in `const missions: Mission[] = [...` is technically an "event", and not actually something that is being shown to the user (i.e. we won't tell them that "collecting rewards for the first time" is a mission they're achieving, missions are sort of groups of events, I'll show some example groupings below:)

 id: 9, name: "Collect resources part 2", description: "Collect resources to build your mining station", rewards: [13]},
    { id: 10, name: "Build mining station", description: "By doing this you can now collect omega resources", rewards: []}, // Not included
    { id: 11, name: "Collect resources from station", description: "You can now build your cloud-spotting telescope!", rewards: []},
    { id: 12, name: "Build Meteorology tool", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 13, name: "Create cloud classification", description: "You can now classify clouds on your planet!", rewards: []},

You need all of these events to be able to make your cloud classification on your meteorology tool

To be able to make a classification on a rover photo, you need to do these actions:
{ id: 14, name: "Collect resources for camera module", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 15, name: "Craft camera module", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 16, name: "Craft camera receiver station", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 17, name: "Collect a photo", description: "You can now classify clouds on your planet!", rewards: []},
    { id: 18, name: "Make classification of photo", description: "You can now classify clouds on your planet!", rewards: []},

To be able to make your thoughts known on the structure of your planet, you need to make a surveyor module and post a classification using it, which is done by completing these events:
{ id: 19, name: "Go mining for surveyor parts", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 20, name: "Build surveyor structure", description: "You can now classify clouds on your planet!", rewards: []}, // Not included
    { id: 21, name: "Make surveyor classification", description: "You can now classify clouds on your planet!", rewards: []},


## Mission logs
Choose a planet (mission 1):
> Start your journey here. Choose a planet that you think looks fun and interesting. You'll start building your base and discovering the planet as you go, and you'll be able to visit other planets later

We're moving the `<ProfileFillIn />` mission (/ mission 2) too a later stage

Travel to planet (mission #3):
> Jump in your spacecraft and pilot it to your new home to start building and exploring the surroundings

Building automaton & collecting resources (missions #4, #5 & #6):
> Build an automaton to explore the planet and collect resources to build your telescope