---
tags:
  - Planets
  - PostCards
  - Classifications
  - Anomalies
sticker: lucide//git-branch-plus
---
See [[NWs S5 Week 4 & 5]] for more info

# Base Planets (set 1)
1. Kepler-69c -> Super-Earth
2. Kepler-186f -> Terrestrial Earth-like
	   Seed: `2739775663`
		#faffff
		#c7d4e1
		#3729ec
		#4fa4b8
		#4c6885
		#0021ee
		#e1f2ff
		#c0e3ff
		#5e70a5
		#1f41e3
3. Kepler-442b -> Terrestrial Super-Earth
		Seed: 
1. Kepler-22b -> Water world
2. Trappist-1f -> Terrestrial Earth-like
3. TOI-700d -> Terrestrial Earth-like

The algorithm should produce a seed, which could be as simple as an encryption of all the values of the overall classifications/model, with a second, smaller weighting attached to the user's unique classifications. 

Colour would be based on the following:
1. Height of plane/triangle (biome/area colours)
2. estimated Equilibrium Temperature (pattern/biome types); semi-major axis, orbital period
3. Radius of planet (determines biome types and overall planet type)
4. Metallicity of planet (determined by stellar type, age and distance)

So the weighting of the colours would be:
1. Planet temperature
2. Planet size/radius
3. Planet mass (eventually)
4. System metallicity (the star's metallicity will default to be roughly the same value for each of the base set, and will then be tweaked further by the type. Eventually we'll have a sufficient calculation/data source for star system metallicity)

Cloud coverage will be shown once we have classifications from the Martian cloud network, we will then augment this with the mechanical values from the exoplanet's configuration (e.g. predicting the spectroscopy/wind values. New algorithms will need to be provided for this, however)

As of now, we have the following planet types:
1. Terrestrial dry
	1. Small, between 0.7-2.0 Earth radii
	2. Temperature likely in excess of >50°C
	3. No liquid solvents
	4. Metallicity: 1
2. Terrestrial lush
	1. Small, between 0.7-2.0 Earth radii
	2. Temperature between -10 and 50°C (equilibrium temperature is above freezing)
	3. Liquid solvent - Water
	4. Metallicity: 1
3. Super-Earth (rare, more likely to be [below])
	1. Between 2.0-4.0 Earth radii (need to double check)
	2. Temperature > 0°C (as it would likely have an atmosphere sufficient to maintain a temperature above freezing)
	3. Liquid solvent - Water
	4. Metallicity: 1
4. Terrestrial frigid
	1. Small, between 0.7-2.0 Earth radii
	2. Temperature < -10°C
	3. Liquid solvent - Water ice, liquid methane (depending on equilibrium temperature)
	4. Metallicity: 0.8
5. Water world
	1. Between 2.0-5.0 Earth radii (need to double check)
	2. equilibrium Temperature between 0°C-50°C
	3. Liquid solvent - Water
	4. Metallicity: 0.5
6. Ice world
	1. Between 0.7 and 2.0 Earth radii
	2. Temperature < 0°C
	3. Solvent - Water ice
	4. Metallicity: 0.8
7. Ice giant
	1. Between 5.0-12.0 Earth radii (need to double check)
	2. Temperature: ?
	3. Makeup: Gaseous methane/ammonia (what is the standard for "cold/hot Neptunes" or "Super Neptunes" outside our solar system?)
	4. Metallicity: n/a (fuel, and eventually H/He (maybe CH4 as well?) will be able to be harvested. For now, only space station settlements, no landing parties. Cloud data will be able to be assigned from the Martian network)
8. Gas giant
	1. >12.0 Earth radii (need to double check)
	2. Temperature: ?
	3. Makeup: Gaseous H/He
	4. Metallicity: n/a (fuel, and eventually H/He will be able to be harvested. For now, only space station settlements, no landing parties. Cloud data will be able to be assigned from the Martian network)
9. Dwarf planet
	1. <0.7 Earth radii (unlikely to be able to hold onto an atmosphere, eventually we will provide calculations that provide an atmosphere for dwarf planets without neighbouring planets or having to deal with a solar wind)
	2. Temperature: <0°C (due to the lack of atmosphere)
	3. Metallicity: 0.9

To determine the planet types, we need to go through both the `anomalies` table and the `classifications` table contents

Generating sectors/planet content & mineral deposits:

# Pipeline
1. Planetary grid, minimal spaceship UI, user then has their structures generated on their planet
2. Pointer for each structure, modal with first action (classification) and tutorial, plus a deactivated "coming soon" button
3. Pointers disappear as each structure is ticked off, create a mission set for each chapter, then move on
4. Once all structures have been used, point to automaton, collect fuel (for now no process to "find a deposit"), and then fuel up the spaceship
5. Once that's done, direct users to the old Mission Group 1 (until the second tutorial is done); as well as some more content/tutorial context that will build into the second chapter. Also allow users to keep classifying on their current planet
6. See the progression for the first chapter (we'll use missions for now, there will be a counter showing the total classifications across all users for the anomaly (e.g. cloud, planet [validity]) and for the planet itself (every anomaly on the planet), as well as the user's individual totals)
	1. This requires me to go through the `parentAnomalies` and `user_anomalies` field/table


This allows the user to go through the process of classifying through every structure, experience resource management, and get the post card (step 6) to share. Some of the post card values will be generated based on their classifications (e.g. border colour based on words used), but we'll also introduce something to be customised - just what?