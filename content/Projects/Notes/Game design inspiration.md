Main inspiration:

1. Hades Star -> Resource, tech tree, base building
    
2. NMS -> Base building, tech tree, exploration
    
3. Zooniverse (duh)
    
4. Voidpet -> Characters, resource, exploration, UI, missions
    
5. SimpleMMO -> Characters, missions, UI
    
6. Eve Online -> Missions, exploration
    
7. Pixel Starships -> Missions, characters, resources
    
8. Tiny Space Program -> Missions, resources, exploration
    
9. My Singing Monsters, Dragonvale, Gizmonauts, etc...
    
10. Pokemon Go -> Exploration, resource, characters
    
11. ET Green Planet
    

Main inspiration for the next sprint:

1. Voidpet
    
2. SimpleMMO
    
3. Hades' Star
    

Could we create a base structure (similar to the faction idea)?

### VP Order of operations:

1. User signs up
    
2. Starts off with a choice of character, could extend that to home planet
    
3. Every entity has a set of traits (e.g. "sad" or "untradable") and also variables (e.g. "health")
    
4. User saves their avatar
    
5. User then explores their surroundings, find items
    

### Simple MMO OOO:

- Very simple, text-based exploration
    
- Take one step/journey at a time
    

### Proposed OOO for Star Sailors

For Star Sailors, it could look a little something like this:

1. User signs up and is sent into a UI where they choose their preferred rover type, favourite planet, favourite star, and play style
    
2. We then match them with some starter missions based on their choices, which will allow them to grow their collection and research even more technology, eventually allowing them to connect with other players & NPCs
    

In terms of the visual scenes/content, we could either go down the simple MMO route, where we are predominantly text & image-based, or we could explore a slightly more complex codebase with a 3d world that the user can explore. We could perhaps implement a galactic map/path in Unity and then have different scenarios (e.g. new planet candidates to explore) pop up.

However, I'm not entirely sure how we'd represent the planetary candidate data in Unity (we could create a representation of a planet in Unity very easily, simply by modifying our existing models. But how do we represent the lightkurve data in Unity? Could we write some code that will extrapolate a period variance rating that will change the orbital motion of the entity? (Because in theory we don't need users to classify the light curves as AI could just do it - but then again, there are some complex light curves that we may not be able to automatically extrapolate. Again, we need an answer to the question about the full merits/benefits of citizen scientists as to their output in Star Sailors). Would just showing the graph be enough?

We need to find a way to make the graph/data more exciting. Perhaps adding this sort of user experience (in terms of the walking/travelling) could be enough, or maybe we need to use the data from the graph to make other representations? This could be done manually (by the dev team/contributors) based on a set of pre-defined parameters, or perhaps we could automate analysis of light curve graphs.

Alien life will be based around avatars, which are presented based on Earth-like parameters (e.g. around certain planet types we would see a representation of an earth-like creature/flora to allow us to understand its parameters/behaviour). We need to come up with an appropriate structure for how intelligent life-forms and ecosystems will develop/have developed and make sure it is flexible enough that it can be adapted based on discoveries (either discoveries in SS or elsewhere).

A big part of the initial pull will be discovering aliens/life and progressing the narrative (I think that was one of the issues with user retention). So if the initial planet candidates presented are centered around entities that are likely to be habitable, it allows us to build a narrative and then provide excitement to the next set of candidates, many of which won't be as exciting (e.g. hot jupiter after hot jupiter, or just continuous Mercury candidates)

## Star Types

1. **G-Type Star (Similar to our Sun):**
    
    - **Planet Type:** Terrestrial, Earth-like
        
    - **Abundant Resources:** Water, metals, organic compounds
        
    - **Habitability:** High (Earth-like conditions)
        
    - **Average Planet Temperature/Orbital Period:** Moderate, Earth-like
        
    - **Size, Temperature & Composition Score of the Star:** Similar to the Sun
        
    - **Earth-Like Animal:** Dolphin (intelligent marine life)
        
2. **M-Type Star (Red Dwarf):**
    
    - **Planet Type:** Rocky, with frozen oceans
        
    - **Abundant Resources:** Water, minerals
        
    - **Habitability:** Moderate (potential for habitable zones)
        
    - **Average Planet Temperature/Orbital Period:** Varied (depends on atmosphere)
        
    - **Size, Temperature & Composition Score of the Star:** Smaller, cooler
        
    - **Earth-Like Animal:** Arctic Fox (adapted to cold environments)
        
3. **F-Type Star:**
    
    - **Planet Type:** Super-Earth, oceanic
        
    - **Abundant Resources:** Hydrogen, complex hydrocarbons
        
    - **Habitability:** Moderate to High (depends on atmospheric conditions)
        
    - **Average Planet Temperature/Orbital Period:** Varied, potentially within the habitable zone
        
    - **Size, Temperature & Composition Score of the Star:** Larger, hotter
        
    - **Earth-Like Animal:** Albatross (adapted to long ocean journeys)
        
4. **K-Type Star (Orange Dwarf):**
    
    - **Planet Type:** Desert planet with subsurface water
        
    - **Abundant Resources:** Water, minerals
        
    - **Habitability:** Moderate to High (with adequate atmosphere)
        
    - **Average Planet Temperature/Orbital Period:** Varied, potentially within the habitable zone
        
    - **Size, Temperature & Composition Score of the Star:** Moderate
        
    - **Earth-Like Animal:** Camel (adapted to arid conditions)
        
5. **A-Type Star (Blue-White):**
    
    - **Planet Type:** Gas Giant with floating microbial life
        
    - **Abundant Resources:** Helium, trace gases
        
    - **Habitability:** Low (extreme atmospheric conditions)
        
    - **Average Planet Temperature/Orbital Period:** Varied
        
    - **Size, Temperature & Composition Score of the Star:** Larger, hotter
        
    - **Earth-Like Animal:** Algae Blooms (photosynthetic organisms)
        
6. **Binary Star System:**
    
    - **Planet Type:** Tidal-locked, rocky with interconnected cave systems
        
    - **Abundant Resources:** Varying by proximity to each star
        
    - **Habitability:** Moderate (caves provide stable conditions)
        
    - **Average Planet Temperature/Orbital Period:** Extreme variations
        
    - **Size, Temperature & Composition Score of the Stars:** Varied (two stars in orbit)
        
    - **Earth-Like Animal:** Bats (adapted to low light environments)
        
7. **Pulsar (Neutron Star):**
    
    - **Planet Type:** Rocky, with magnetically shielded biospheres
        
    - **Abundant Resources:** Heavy metals
        
    - **Habitability:** Low (intense radiation)
        
    - **Average Planet Temperature/Orbital Period:** Varied (rapid rotation)
        
    - **Size, Temperature & Composition Score of the Star:** Extremely dense, hot
        
    - **Earth-Like Animal:** Radiation-Adapted Microbes
        
8. **W-Type Star (Wolf-Rayet):**
    
    - **Planet Type:** Volcanic moon with unique extremophiles
        
    - **Abundant Resources:** Metals, volcanic minerals
        
    - **Habitability:** Low
        
    - **Average Planet Temperature/Orbital Period:** High temperatures
        
    - **Size, Temperature & Composition Score of the Star:** Very hot, large
        
    - **Earth-Like Animal:** Heat-Resistant Microorganisms
        
9. **Exoplanet in the Habitable Zone:**
    
    - **Planet Type:** Terrestrial, with a diverse biosphere
        
    - **Abundant Resources:** Water, minerals, fertile soil
        
    - **Habitability:** High
        
    - **Average Planet Temperature/Orbital Period:** Earth-like
        
    - **Size, Temperature & Composition Score of the Star:** Similar to our Sun
        
    - **Earth-Like Animal:** Arboreal Mammals (tree-dwelling)
        
10. **Black Hole System:**
    
    - **Planet Type:** None (no stable orbits)
        
    - **Abundant Resources:** Gravitational forces
        
    - **Habitability:** None
        
    - **Average Planet Temperature/Orbital Period:** N/A
        
    - **Size, Temperature & Composition Score of the Star:** Extremely dense, high gravitational pull
        
    - **Earth-Like Animal:** None (metaphorically, a phoenix - resilient to extreme conditions)
        

Life-types based on stellar types

1. F-Type
    
    1. Slightly larger than the sun
        
    2. Massive increase in UV output -> requires denser UV shielding (ozone), or could life evolve without the limitations of DNA?
        
    3. KOI-4878.01 is an example of an incredibly earth-like star
        
    4. Orbital distance (for habitable zone) would be about 2.0-3.7 AU (300-550 million kilometers). So we could calculate this based on orbital period & radius, right?
        
2. G-Type
    
    1. It's pretty clear that planets around these stars are ideal for life [as we know it]. Low UV, low percentage of mass coronal ejection events, the habitable zone (for carbon/water-based life) is at a range that doesn't allow for tidal-locking orbits.
        
    

Perhaps we could just start off with base planets around different star types, enough so that there's a good list of different planet types, and explore how citizen research in Star Sailors can be extended/utilised?

# Graph ideas

Perhaps we should colour code the output on the graphs based on star type, or graph type (example binned, phase folded, etc), planet type, etc.

Obviously we'll allow the user to change the colour on their own notebooks.

# Base planet candidates

**F-Type Stars**

```
https://embed.deepnote.com/50ad3984-69a9-496e-a121-efb59231e7e9/9180639a9e5f426395fbf81befe22788/d1ffbaeedbe8423d9d5889071bfeed8c?height=573.1875
```

- KOI-4878.01
    
- KIC 8462852 - Tabby's Star. Interesting, mysterious light dimming
    
    - Could be evidence of potential exomoon activity
        
- Kepler-1445 (Turns out we can use the Kepler instance?). Would be extremely hot -> orbits at around 0.3 Mercury-Sun radii, around an F-Type star.
    

**G-Type Stars**

- Kepler-69. ~80% mass of our sun
    
- Obviously there's Kepler-22
    

**K-Type Stars**

- Kepler-62 (3 candidates), 61
    

**M-Type Stars**

- K2-415
    
- Trappist-1 (obviously)
    
- TOI-700
    

No candidates for A-, B-type stars yet

[https://exoplanets.nasa.gov/discovery/exoplanet-catalog/](https://exoplanets.nasa.gov/discovery/exoplanet-catalog/)

I'm going to continue writing about the other star types once we have an understanding on their habitability potential

What about the habitable zones for silicon/liquid methane-based life? Let's also not forget about the possibility of exomoons and their subsequent habitability. For the purpose of narrative, however, we will not be making up any exomoons.

1. A reasonable initial estimate for the habitable zone for liquid methane around a G-Type star is ~8-15AU, assuming a mass & luminosity very similar to the sun. This estimate is VERY ROUGH and does not take into account any tidal heating that Saturn impacts on Titan, which could extend the overall range out further for stand-alone exo-planets
    

Hypotethetical exomoons:

1. WASP-49b -> Volcanic activity
    
2. ==Tabby's star==
    

Something that is really interesting is that wandering/nomand planets are likely to remain geologically stable and active for billions of years, if they can hold onto their atmosphere during the initial formation phase

Some other take-aways:

1. If we start off with these base planets, we don't need to worry about full pcg or notebook customisation yet!!
    

# Base candidates

For now, we're going to write this new narrative with no aliens or NPCs, narrative components (including factions) yet. We're going to allow users to choose an instance of their preferred base planet, and we'll roll this out in the first alpha of this redesign before sorting out the narrative.

We're going to try and get some variety of different planet types, but this will initially be centered around resources and not based on life forms. Since we won't have too many users exploring this all yet, we don't need to integrate everything we want to at this point (e.g. every different star type, 100% accuracy with regards to composition, location, etc).

We do need to have the base planets be _slightly_ habitable to humans, as we're going to be starting the exploration phase (at this point, anyway) with the player character "adopting" a human phase. "Liquid methane habitable zones" etc therefore don't need to be considered at this point.

We could start off with simple habitation models like what could be set up on Venus if we eventually colonised it (and explore the possibility of interacting with any potential "native" life e.g. microbes, accelerating growth, etc). This would help for planets like Kepler-69c. This also helps because during the initial phase, as long as advanced colonies from off-world can establish operations on the planet, we don't need it to be 100% habitable.

For the sake of simplicity, we're going to start off with Kepler planets due to the wealth of code we have for lightcurves/transitting exoplanet candidates. We should, however, look into radial velocity/microlensing visualisation methods because that could produce relevant and potentially useful data, in the context of user retention.

- Kepler-69c. G-Type star, inner of habitable zone (242 day orbit). Likely to be similar to Venus. 1.7x eRadii, 2.4 eMass
    
- Kepler-186f. 580LY from Earth. M-Type star.
    
- Kepler-442b. K-Type star, 1206LY from Earth. Not tidally locked.
    
- Kepler-22b. Obviously
    
- Trappist-1. M-Type
    
- TOI 700d. M-Type Star, 101.4LY from Earth. Likely to have retained a planetary atmosphere
    

It is important to note that currently no potentially habitable planetary candidates have been discovered around F-, A-, or B-type star systems.

We're not going to introduce fictional planets or fictional representations of existing entities (e.g. a fake Earth) at this point.

# Narrative-component bridging (brainstorming)

Here are the "nextual" components we'll need to mimic a similar order of operations (OOO) to VP

- New signup/authentication model modal
    
- Minimal character slider; modal
    
- Expanded modal for each character (to see traits, for e.g.)
    
- Working avatar upload component
    
- Map/explore component
    

Perhaps we could implement a narrative structure where we have the SimpleMMO step counter for narrative progression, but we need to introduce multiplayer elements quickly and do it in a way that isn't a complete rip-off of sMMO

Mission select -> we'll keep the original missions, but we will need to set up some new missions that are maybe a bit less in-depth where the users will go through just enough to unlock their base planets (and we need to ensure that there is new data/contributions coming)

In conclusion, if we can come up with these components and a suitable, recursive setting, we can have minimal contributions and high user retention. Maybe we could make it mobile-oriented?