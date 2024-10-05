---
sticker: lucide//map-pin
tags:
  - Locations
  - Settings
  - Planets
  - Anomalies
  - Narrative
---
I'm thinking that we make different classifications available for real (and understood, in the context of different modules) space bodies, and we can then extend it to find similar objects and colonise those. E.g. users start on Earth, where they get a little bit of everything (as all data goes to Earth), but to get more resources or more (specialised) data, they have to go to other planets or asteroids. Then, we can treat those bodies as the "training" bodies and also have a set of extra-solar bodies for other specialties, and go from there with giving users more bodies to classify and "colonise".

I do want to think about how this affects the narrative regarding alien life, player factions (if everyone comes from Earth) and how we can treat multiple users on the same planet (maybe introduce sectors or have everyone on a shared space?). The key question is where do other planets come into it?

Something interesting that does pop up is an answer to the question about the relevance of using #Telescope to discover things on the planet you're on - it would be like launching satellites, you'd get more usable data on an "airless" world like Mars than you would on #Earth . It does remind me as well that I would like to determine a relevance of each anomaly discovery to the current anomaly.


### Ideas
When visiting other planets, you may need to orbit the planet or find a natural satellite to begin your initial classification, observation & initialisation (this is especially true for gas giants).


# Structures/missions for each "training body"
`anomaly-set`: `solar-system`
Remember, everything can be done on #Earth , just with limited scope/frequency

## Venus
1. Volcanoes?
## Mars
1. Rover photos
2. Martian clouds - exclusive? Or just for planet types?

## Jupiter
1. Juno Radio
2. Jupiter cloud pics?

You'd be stationed on (that small moon that's really close to Jupiter)

### Io
1. Volcanoes?

### Europa
1. Fish observations (alien towards the end-game, "man-made, divided colonies" early-game)
## Moon
1. Craters/landmarks?

## Space station
1. Specialist bio modules?

# "Planet" types
## #Solar-System 
### Terrestrial
Lush (potentially lush outside of solar system)
1. Earth

~~Hellhole~~ Volcanic/Hot (can we work the pressure/tectonic activity in?)
1. Venus

Arid/Airless
1. Mercury
2. Moon

Frozen
1. Mars (need to replace with a better category name)

### Gaseous
Gas giants
1. Jupiter
2. Saturn

Ice giants
1. Uranus
2. Neptune

## Classification options
### Always available (any type)
1. Finding new planets
2. Greenhouse/zoodex-read (when colonisation occurs)
3. Finding asteroids, sunspots, other stellar objects
4. Researching

### Requires lush (Earth)
1. Zoodex-read (any)
2. Zoodex-upload
3. Specific Earth-based LIDAR projects

A note that if the planet is #Earth (i.e. if `anomaly` = "69"), then all classification options are available (again, just the frequency (or some other discriminator) is reduced)

### Requires "Frozen" (Mars)
1. Martian clouds
2. Rover photos - or could this be extended to any terrestrial?

### Requires Gas giants
1. Juno radio
2. Jovian cloud patterns/bands


Users will then have to organise planets they discover (using the #Telescope ) into groups referencing those in `solar-system` `anomalies.anomalySet`.
We have to find research projects that are specifically for the body, or fudge it (in the case of Volcanoes for Io) that it's close enough to realistic, maybe we just come up with some filters that could be applied to content (say, from) Venusian Volcanoes to make them feel like they're on Io.