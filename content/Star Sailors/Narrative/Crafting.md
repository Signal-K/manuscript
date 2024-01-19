---
title: Crafting
tags:
  - Star Sailors
  - Narrative
---
> Raw material [combination] → base building block → tool/structure/vehicle or other entity

# Item List
## Minerals / Raw materials
* Coal -> #11
* Silicates -> #13
* Iron
* Alloy
* Fuel
* Copper
* Chromium
* Nickel
* Water

Some notes ->
1. Silicates should either be composed of, or smelt into, silicon
2. Alloy currently consists of a combination of multiple trace metals for simplicity
3. Fuel will be explored more in subsequent versions
	1. As an example, you can't just mine fuel from a sector IRL, you'd need to mine raw materials, as well as collect them from the atmosphere, refine them, etc

## Structures
### Exploration
Structures/items relating to gathering more data
1. Telescope Signal Receiver -> #12
		This tool is used to receive transmissions from your transiting telescope and decode them into readable data
2. Transiting Telescope -> #14
		The first telescope you build - can do short-range transiting scans of your base planet
		Parent item -> #8
### Automation

### Processing / Refining

### Construction

### Vehicles

## Archive
1. Potion -> #1
2. Sword -> #2
3. Armour -> #3
4. Axe -> #4
5. Hoe -> #5
6. Shovel -> #6
7. Pencil -> #7
8. The Golden Telescope -> #8
9. Golden Telescope -> #9
10. Aerocamera -> #10

# Crafting recipes
## Notes
These will all be updated & modified as we add more materials to `inventoryITEMS` table. That reminds me, building this new microservice will make editing the recipes so much easier on my end.

I think we're also going to need to update the method for how sectors are created and viewed. Especially the UI.

As of v2 for the crafting microservice, we will have multiple items share the same crafting recipe, this is for simplicity when creating sectors so we don't have to create dozens of sectors.
## V1 recipe(s)
I believe there was a function that would allow the user to craft a telescope item with either a single piece of coal or iron.

## V2 recipes


# References
[Ore resources on Mars](https://en.wikipedia.org/wiki/Ore_resources_on_Mars)