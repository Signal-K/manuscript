---
sticker: lucide//package-open
banner: Pasted image 20240929235113.png
tags:
  - Mechanics
  - Chapter-2
  - Chapter-1
---
(a note that this doc also contains stuff that may be added into #Chapter-1 later on, and content/mechanics that are part of the sprint to integrate it into #Chapter-2 )

## SSG-2/new epic finish
1~~. Spaceship component
2. Launchpad component
	1. These will start with a bit of free fuel
3. New (simplified, for now) #PlanetSwitcher component~~

Get Rhys to help with mapping missions.

Set up mission routes for first research, first researched module. Add some documentation and more dialogue. Go through Fred's #characters notes
.....

5. ~~Travelling between planets~~
6. Resource collection
7. Terrariums
	1. You'll have to "take care" of your planet/base as you start to increase the population and add more "stuff" on there
	2. Show and display your discoveries
8. A limited #starnet feature
	1. Limited to sharing content, asking for feedback/support and viewing discoveries

Obviously, since in #Chapter-2 our users will only be on one of the #Solar-System planets, we'll make the terrariums represent "sectors" on their #planet . For now, it will be 1 #sectors  per user per planet. 

The main new structures produced will be related to resource collection and travelling. #Crafting / refining won't be introduced yet. I also want to add the missing citizen science mechanics (e.g. #nestquestgo  from #zoodex ) that I "removed" temporarily (see [[Components removed from Chapter 1 (02)]]) to get the current build out. 

For the #Generator / terrarium, users will slowly uncover their planet.

## Minimal narrative
Users will start on their planet and have to build up some structures. Fortunately, they can just start where they left off, make some classifications, and then build some tools/ #Structures to find and collect resources (automatons?).

After doing this, users will find the #Starnet option (maybe we need to build an orbiting satellite to establish communications. Add an animation here?).

Then, users go through resource collection, sharing their discoveries and viewing theirs' and others', commenting & adding votes, and then they can find their own exoplanet (again, #sectors ).

### Starnet
Will be a similar modal-layout to #Structures , will also house documentation. Users will be able to view the #marketplace here as well, but it won't be accessible until later in-game.

#Starnet will eventually serve as a semi-manual verification system for #Classifications 

Users will be requested to fill in a profile when they first access #Starnet 

We'll add lore and backstory to each module/component, and start adding some backstory to the user and to the "galactic community" (but not too much that we box ourselves in or limit the user's own character lore)
	It should at least be based on the real source/team behind a module

Do we give users the option to see their "progress" to completing certain milestones do become an "explorer" or "surveyor" based on the number and variety of their classifications (i.e. give dedicated, explicit pathways to "mastery" or usage of structures/disciplines)?

#Starnet will be where #community-events are displayed, so that might be when we start bringing back "available missions for structure/module" - but until we start working with research projects or have a more direct data source/connection, this is not required.
### New classification methods
1. If I can find a volcanic project, I'll integrate this onto #Earth #Io #Venus [[In-Game Locations]]
	1. Question -> would this slot under #LIDAR or a new structure?
2. #zoodex upload & search method
3. Fishing in #zoodex -> #Europa #Earth #Enceladus 
4. Star hunting or weather events

We need to come up with a plan to make the data sources more realistic for the planet the user is on...simulations? - customise how data sources are displayed/loaded in based on #Surveyor stats.

#Starnet will introduce something like a #field-guide from #Zooniverse -> for now, I'll just copy the documentation sources & assets and then try and build out a design. One for the future
#### Rover classification
1. We will integrate with an API route (either #Flask or #nextjs-api) to generate mineral deposits from user classifications - and we might integrate it with the planet type and their previous (other-type) classifications as well
	1. To start with, we'll just base it on the planet type followed by a randomiser e.g. rocky/terrestrial + distance from parent star

Resource collection -
1. I want to add some more movement and animations - see [[Automaton interactions & structures]]

### New structures
1. #Greenhouse - will just show a list of discoveries for now related to #zoodex . Later on, it will determine the number of animals and plants you've classified and show those as icons (as well as linking them in with the terrarium/growth mechanic)
	1. Do we make this as a separate structure or a module/component of #zoodex ?

### #Generator 
1. Let's get 4 profile pictures/gifs for each #Solar-System planet from Godot (and figure a way to automate/deploy it, later on)
2. We can compare/merge it (overlay) with the generated (in .ts) sphere
3. We'll just show a list of discoveries for now, next sprint/week we'll build in the rest of the frontend
4. Users will be able to share their discoveries in #Starnet 
5. Figure a way to "draw-on" -> [[Components removed from Chapter 1 (02)]]
6. We can also add some basic parameters from [[Generator Post-Card component]], but that will be down the line

![[Pasted image 20240930144227.png]]

By default, the generator will fade slowly to show the planet with its orbitals and buildings and a small menu that brings up the context area.
Users will also be able to see a similar view (without buildings/structures) by changing the view of the #PlanetView , which brings the top section down and expands it.

The generator will eventually serve as a minimal representation of everything on a planet, you'll be able to connect them together to generate trade routes and other relationships between players/NPCs, and then obviously see how #terraforming affects the planet (again, this is down the line)
![[Pasted image 20240929235113.png]]

Biomes and other entities in the generator will be based on the #Surveyor 

Users will be able to connect signals like from the SETI AWA project to their planet to show "messages" their planet has received (the theory is that civilisations will contact similar planet types first searching for "life as they know it"). We can also compare signal originating position/constellation to the location of the TIC/KIC candidate and bring that in as an additional data source for the Terrarium. We just need to find a data source relevant to alien intelligence for #Solar-System #Anomalies e.g. fish hunting on #Europa , microbe fishing on #Mars, etc.

To start with, we can just show the population of the #planet and then split it by man-made and natural...obviously with a bit of fictional content there :)

The more classifications and content the user adds to their planet/terrarium (which then extends to any entity/anomaly in-game), the more they can do with it.

** #Generator **
1. Show image of planet (based on number of classifications)
2. Show their classifications
	1. We don't need to filter these by `classificationConfiguration.activePlanet` yet as users will only be on #Earth , so that makes it a little simpler
3. Trees and other things can be integrated
Sectors ("instances" of planets owned by users) will represent your unique discoveries and adaptations/buildings on your planet, and will allow different things to spawn in.
	Sectors will be introduced in #Chapter-3 

(go over other notes, too) #Greenhouse #terraforming , can add #Terrain maps (terrain affects *certain things??*?

Later ideas:
* Show a graph view of their classifications (later)


## Extra
There's a few things in [[Components to-do]]that are a while away, but I'll keep those in mind...