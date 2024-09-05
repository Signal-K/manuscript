---
sticker: lucide//gem
tags:
  - Mining
  - Missions
  - Chapter-1
---
Current order of operations:
1. ~~Display mineral deposits on the active planet~~
2. ~~User selects a deposit, followed by configuring the rover they want to use to collect the resource~~
3. ~~User can monitor the collection process in the subsequent dashboard~~

Tiny Space Program operations:
1. Display deposits
2. Click on deposit, see stats/properties
3. Select method of acquiring parts of the deposit
4. Send out the entity to gather the resources, this includes an animation
5. Receive the resource from the deposit after a set time has elapsed
> I think it's fair to say that all of these have been ticked off (well, I'm not happy with the animation, but functionally it's all there)

There will need to be a limit for the number of deposits that can be "discovered" on a planet before existing ones have to be mined.

### Mining methods
#### Automatons
Rovers/automatons can be used to mine through the deposits, their efficiency and availability is dependant on:
1. Rover capacity
2. Rover mining speed
3. Rover modules
	[[Automaton - Rover configuration|Automaton - Rover configuration]]
Some modules that are available to a rover would allow it to build, dig, test, and some modules allow it to mine stronger/rarer materials (e.g. a "diamond cutter")
#### Mining stations
1. These mining stations will produce resources over time, allowing rovers to be used for other things
	1. A note that for chapter 01, all mining & resource collection operations should be able to be easily completed using just the rovers, we won't be implementing stations/structures until #Chapter-2


### Motives
**Why does the user want to collect minerals?**
1. To build new structures, which are used to collect data used for citizen science missions/modules
2. To upgrade existing structures, settlements, vehicles, modules, automatons & tools (e.g. upgrading your spaceship)
(Note that other resource types, with their own motivations, do exist)

### Integration with rover photos
1. Based on the options the user gives, this creates a multiplier that determines the deposits (similar to a draft lottery system). E.g. dried up lakes will likely have silicates **How to prevent abuse**

Having said all that, it would also be a good idea to initially populate the user's early-game deposits with some resources that will give them a slight head-start in the early construction (see [[Timeline|Timeline]], [[Basic recipes|Basic recipes]])

# What will be in Chapter 1?
1. ~~Automatons will be used for mining~~
2. Limited upgrades will allow the users' automatons to collect all the resources required for the "base structures" for all the "base citizen science modules" e.g. #zoodex 
3. Users will be able to directly proceed to the building [structures] process after collecting resources
4. Users will also be presented with a [rovers] action panel, which allows the user to choose to search for more photos, mineral deposits, build ("coming soon", etc)
	1. Will initially just be a junk/transitional animation, with no control, will add context later
	2. [Dribbble design](https://dribbble.com/shots/10752052-Mars-Rover-AR-Navigator-App)
	3. Add topographical map

# UI Components
1. ~~Panel for all mineral deposits~~
2. ~~Panel for user to deploy their rovers and collect resources~~
3. ~~Limited inventory UI~~
	1. Automaton/roover [ui] panel on the right
		1. Move automaton configuration/control to bottom right
4. ~~Automaton configuration UI~~
(and of course put it all together nicely)

Static components (e.g. deposit list [grid], inventory) on the left, interactables on the right

# Other to-do
* https://signalk.atlassian.net/browse/SGV2-162?focusedCommentId=10662 - Fix this context by updating rovers' activePlanet when mining begins, link them to an automaton structure as well

# Questions
See [[01 Chapter 1|01 Chapter 1]]

# Other people tickets
1. `MineralDeposit` & `MineralDeposits` component - get Rhys to help organise into squares
2. Background images for planet sections - [[Tickets|Tickets]]
3. Discuss (p19) guidebook and terrarium, "complex" design (and overall page route, what is being shown where)

# Move to own section
1. What is the story behind the narrative? What do the characters get by users contributing scientific data? - this determines what we show, when users perform actions, if there's space for PvP/E mechanics