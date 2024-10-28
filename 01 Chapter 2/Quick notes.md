---
sticker: lucide//dna-off
tags:
  - Chapter-2
  - Missions
  - Narrative
  - In-Progress
---
After having a brief but productive discussion with Dylan earlier today, I've come up with some new ideas and plans.

Firstly, for #PostCards , #Starnet makes perfect sense as an intermediary step, as it provides users with an opportunity to discuss gameplay, plan out collaborative missions and work on anomalies together. I think one thing I'll add to the current mission plan for #Chapter-2 is setting up a profile for #Starnet and viewing your discoveries. Completing missions or classifications can "unlock" or "activate" the content in the post card and it can then float around or be interactable in the main view.

A mission pathway is another thing that I've been kicking around for a few months. Essentially there's a few playstyles that users can undertake depending on what they'd like to study and other parameters. I think we can begin with some basic ones separated by structure type, like #Data-Sources are, and then provide more in-depth missions and activities. Once we get into dedicated mission pathways, I want to have an audit of the code & infrastructure with Dave, though, to identify the best way to track user mission completion.

Users will need to make some classifications and share their discoveries on Starnet to progress faster. Like Dylan proposed, they can pause their pathway at any time and pick a different path. Depending on the missions completed and their planned pathway, we can then build a mission recommendation tool.

Users will have dedicated planets or planet sectors/scenes for pathway training. I think initially the pathway will be limited to the following:
1. Meteorologist
2. Astronomer
3. Botanist/Biologist
However, there is substantial overlap (e.g. Martian clouds = Meteorology + Astronomy), so we can give users a similar choice to how #Data-Sources are distributed depending on planet type. (also on that, we need to update data sources to have dedicated planet ids as well.).

#Starnet will produce some community missions, some of these should be based around what users would be doing anyway in the early-game so that some of these can have some progress being added and then we direct users towards events/missions not tied strictly to the narrative.

So the priority is to build up a list of mission pathways, connect those to missions and then build a #Starnet component around this and user discoveries, and then determine how to implement a #Surveyor module for all classifications and have those affect the anomaly printing in cards (first thought would be to go through `classifications` for any mentions of `classifications.anomaly` = `anomaly.id` and then reading the configuration).

Anyway, minimal plan -
1. 3 pathways to start with
2. Point missions & structures ( #Research ) towards these pathways
3. Build starnet to show discoveries, cards and recommended missions
4. End #Chapter-2 / #Chapter-3 integration scene, including resource collection.

Some quick notes around terrariums:
1. Users will have a set number of anomalies they're able to request feedback on (will be placed into capsules) until the user is satisfied with the consensus added
2. We'll introduce some generative functions around planet, atmosphere, terrain generation, etc. Users will provide feedback on these algos (users will need to send out automatons to collect this data), 
3. What is a tangible benefit to moving anomalies (animals, etc) to different locations? How do we implement a "modifier" like evolution params based on planet stats/type without relying too much on guess work? How do we provide a citizen science utility here that isn't just able to be complete by algos?
4. For post cards, we'll allow users to customise certain things. Animals can't be customised, however users can upload their own animal pictures and maybe have that customisation outlet in the evolution generator/sim. Users can create terrain and pathing (within reason, similar to the limitations on planet customisation). 
5. If the end-game (both IRL & in-game) is discovering alien *intelligence*, we should link user contributions into an aggregator with SETI signals and allow users to help determine what to look for (biosignatures, evolutionary tendencies, etc)

Users will have to work together to increase the data flow. Sort of like running a collaborative space agency entity where users. We also need to maybe add more tasks to perform to collect data rather than just having it be sent to their scope (this is already being implemented with the #upload mechanism), while still not making it too complex or time-consuming to get that data.

The key thing with things like tamagotchis and terrariums is we need to find the balance between how they aide in the contribution process while also allowing for users to have that customisation & building/construction, creative outlet. Ideally they aide in contributions for that anomaly AND others (increasing the dataflow/connectivity?). As for now, I'm sort of out of ideas. I would like to follow a similar structure to [[PostCards (CPW-2)]] for this.


### Surveyor integration
1. Allow users to edit their posts -> https://signalk.atlassian.net/browse/SSC-24
2. Post cards should show original value, your value/classification, and then an average of everyone's/everything



// Mission ideas
For my game, users will be distributed (by their own choice) into one of three pathways (Biologist, Meteorologist, Astronomer). They'll be able to complete any mission they wish and level up in all the pathways, however we'll start with them choosing one. The pathway they choose determines which missions they'll be given to complete each chapter, biologists will have to complete citizen science projects around classifying animals and plants, astronomers will look at exoplanets, sunspots, and meteorologists will be concerned with weather events (including cloud patterns on other planets, for example). In Chapter 1, they start out on Earth and get introduced to structures, reading data and classifying it, before moving around the solar system to pick up fuel and participate in new projects. At the end of Chapter 2, they have to use the Telescope structure to discover an exoplanet that they want to move to. On that planet, they'll then continue around different classification projects and be introduced to a SETI classification project. Until now, all of the missions have been about reading and classifying data, however I'm working on introducing an upload feature, which is already present for the biologists. Essentially, you upload a file and add it to a dataset (e.g. for biologists, you could upload animal/plant pictures to a general bucket or to a more specific project like if you see burrowing owls). Sort of like Pokemon Go, we'll tag the location and allow you to see all your discoveries (and eventually interact with them). For astronomy and meteorology, it would just be simple (to start off with), like uploading pictures from your telescope or clouds from your phone. You'd still be able to read data as well. Chapter 3 also introduces community missions, like establishing community greenhouses on Mars or Venus. Once a greenhouse has been established, users can then bring animals there. Community missions would be structured like those in No Man's Sky, where you need to investigate things and add your own content so we can understand more about the game/world. You won't need to work together, but there will be the option to. I want you to come up with some community missions concerning astronomers and meteorologists, including data sets that are relatively easy for the average person to upload to (e.g. not everyone has a telescope, so uploading your astrophotography shots won't always be possible :) ). If they could be concerned around a mixture of reading and adding data, and follow the overall gameplay flow, that would be good. Here's a list of projects we currently have in the game: 1. AI for Mars (obstacle avoidance algorithm contribution for mars rovers, helping to train them) 2. Planet 4 (classifying satellite pics of Mars' surface) 3. Rovers of Mars (classifying pictures from Martian rovers) 4. Planet Hunters (TESS/Kepler, eventually radial velocity, microlensing, etc. NINA plugin for discovering exoplanets, for example) 5. Minor planet hunt (searching datasets for asteroid candidates) 6. Disk Detective (hunting for early solar system formations) 7. Martian cloud survey (meteorology) 8. Jovian Vortex/Cloud hunter (meteorology) 9. Cosmic muon hunters 10. Name that neutrino Plus a smattering of animal classification projects for biologists

###### ChatGPT said:

ChatGPT

Your game's structure is fascinating, and the pathways you've outlined for Biologists, Meteorologists, and Astronomers present great opportunities for creating immersive, community-driven missions. Below are some ideas for community missions concerning astronomers and meteorologists, blending data reading and uploads while keeping accessibility in mind.

### **Astronomers:**

1. **Galactic Dust Map Creation** (Community Mission):
    
    - **Objective**: Create a detailed galactic dust map by uploading wide-field night-sky photography or satellite data that tracks light pollution, interstellar dust clouds, or other obstructions.
    - **Contributions**: Players can upload their night-sky photos and tag the quality of visibility, atmospheric interference, and dust density. For players without telescopes, simple sky photographs (using long exposure or mobile apps) can still provide useful data.
    - **Read Data**: Other users review and classify regions of space based on the data to help correlate dust regions with blocked star visibility.
    - **Goal**: Collaboratively piece together an accurate map that could be used for planning future telescope missions or finding optimal observation locations.
2. **Exoplanet Atmosphere Analyzer**:
    
    - **Objective**: Astronomers collaborate to study light curves from exoplanets with the goal of identifying atmospheric compositions.
    - **Contributions**: Using citizen-sourced astrophotography and spectroscopy data (where available), players upload their findings or select from existing datasets (such as light curves from TESS/Kepler). Even amateur astronomers can contribute by uploading images of transits or stars.
    - **Read Data**: Community members classify the absorption spectra in light curves, which helps determine if the planet has water, methane, or other elements.
    - **Goal**: Catalog exoplanetary atmospheres and generate a global resource for future discoveries. Eventually, as new technologies and structures are unlocked, the data could be used to recommend planets for colonization.
3. **Lunar Surface Anomaly Hunt**:
    
    - **Objective**: Players collaborate to discover new features on the Moon, such as potential water deposits, new craters, or lava tubes, by classifying images and data.
    - **Contributions**: Players upload telescope or smartphone photos of the Moon’s surface. They can also analyze NASA and ESA datasets looking for anomalies.
    - **Read Data**: Community members classify and flag unusual formations or signs of change (e.g., impact craters or new features).
    - **Goal**: Build a detailed, up-to-date map of the lunar surface, which could eventually lead to future missions where players help establish moonbases and understand its habitability.

1. **Solar Storm Watch**:
    
    - **Objective**: Collaborate to predict solar storms and measure the Sun’s surface activity.
    - **Contributions**: Players can upload telescope or space weather images, while others participate by reviewing existing datasets of solar flares, sunspot patterns, and coronal mass ejections.
    - **Read Data**: Community members classify sunspots, flares, and solar prominences, predicting where solar storms will occur and their impact on Earth and nearby planets.
    - **Goal**: Forecast solar activity, which could be essential for protecting space missions and structures from solar radiation.
5. **Cosmic Debris Monitoring**:
    
    - **Objective**: Track space debris in Earth's orbit to prevent potential collisions with satellites and spacecraft.
    - **Contributions**: Players upload satellite tracking photos or classify datasets from global space agencies monitoring debris.
    - **Read Data**: Users help track movement patterns of space debris, aiding in mapping dangerous zones that need further attention or potential cleanup missions.
    - **Goal**: This could feed into future missions involving spacecraft equipped with debris removal capabilities.

### **Meteorologists:**

1. **Planetary Storm Tracker**:
    
    - **Objective**: Players collaborate to track and classify weather patterns on different planets, such as Mars and Jupiter.
    - **Contributions**: Users upload photos of clouds or storm formations on Mars, Earth, and other celestial bodies, or analyze data from missions like Juno (Jupiter's atmosphere).
    - **Read Data**: Classify the types of storms or cloud formations. For example, on Mars, users might help track dust storms, while on Earth or Venus, players focus on clouds or rain patterns.
    - **Goal**: Create a shared planetary weather map that could be used for both scientific research and future in-game missions (e.g., establishing bases in low-risk areas).
2. **Cloudscape Classification** (Earth & Other Planets):
    
    - **Objective**: Build a global catalog of cloud types and weather patterns across Earth, Mars, and Jupiter by uploading photos or using pre-existing satellite imagery.
    - **Contributions**: Users upload cloud photos from their smartphones (for Earth) or from telescopes for other planets, with tagged locations and cloud types.
    - **Read Data**: Classify different cloud structures, wind speeds, and formation processes.
    - **Goal**: Provide insights into the weather on different planets, creating an accessible dataset that could later be used for establishing habitable zones or protecting future missions from extreme weather.
3. **Martian Weather Survey**:
    
    - **Objective**: Collaboratively monitor seasonal weather changes on Mars.
    - **Contributions**: Players upload images from rover missions or satellites tracking seasonal changes, dust storms, and temperature shifts.
    - **Read Data**: Classify weather patterns and predict upcoming climate events.
    - **Goal**: Help determine the best seasons for missions and colonization efforts, ensuring structures are built during more stable weather periods.
4. **Global Climate Change Tracker**:
    
    - **Objective**: Track changes in weather patterns on Earth, contributing to a citizen science project designed to understand long-term climate shifts.
    - **Contributions**: Upload images of extreme weather events (e.g., floods, storms, fires), providing geotagged data that helps catalog regional changes in climate over time.
    - **Read Data**: Analyze datasets looking for correlations between increasing storm intensity, global warming, and weather patterns.
    - **Goal**: Build a real-time database of climate events that can be shared with other players and used to understand future environmental risks, both in-game and out.
5. **Atmospheric Composition Watch**:
    
    - **Objective**: Study the changing atmospheres on different planets, contributing to a broader mission to track the chemical compositions of atmospheres.
    - **Contributions**: Players upload data from their own observations (e.g., local air quality, planetary atmospheric conditions from telescopes). On Mars, players could help analyze CO2 levels.
    - **Read Data**: Classify atmospheric changes over time, helping predict which planets might be habitable in the future.
    - **Goal**: This research could ultimately assist in preparing future missions or even in-game atmospheric terraforming efforts.

### **Gameplay Flow Integration**:

- **Chapter 1**: Involves smaller, introductory missions (like classifying clouds or planetary images).
- **Chapter 2**: Focuses on uploading your own contributions (e.g., cloud formations, dust storms, exoplanetary data).
- **Chapter 3**: Introduces collaborative community missions like building greenhouses or setting up space colonies on new planets. Players might need to work together to predict the weather and atmospheric conditions before establishing habitats, creating a blend of cooperative and individual achievements.

These community missions encourage engagement with both uploading and reading data, allow a wide range of players (with or without advanced tools) to participate, and foster collaboration while following the natural progression of the game's storyline.

4o

##### You said:

That's a good start. Can you come up with community missions centered around structures and community infrastructure (upload and reading of data) for the 10 projects I mentioned as well? Bonus points if you can create some significant, and at least semi-accurate relevance to exoplanet data. e.g. if there's any datasets we can use alongside lightcurves to do atmospheric composition surveys, or if we could get stellar parameters from the lightkurve tic id to estimate these values. Also, SETI signal classifications, too!

###### ChatGPT said:

ChatGPT

Here are community missions centered around structures and community infrastructure for each of the 10 projects you mentioned, incorporating both the **uploading** and **reading** of data. I’ve also integrated how some of the tasks could tie into **exoplanet discovery**, **atmospheric composition surveys**, and **SETI signal classifications** to create meaningful connections to real science.

---

### 1. **AI for Mars** (Obstacle avoidance algorithm for rovers)

**Mission**:  
**"Mars Rover Colony Expansion"**

- **Objective**: Build and optimize a **network of rovers** on Mars by training AI models to avoid obstacles in challenging Martian terrain.
- **Upload**: Players upload rover simulation data or real-world tests, including obstacle identification and successful navigation paths.
- **Read Data**: Classify obstacles and terrain from rover imagery (dunes, rocks, craters) and train the AI using community-sourced examples.
- **Relevance to Exoplanets**: Once the AI is trained on Mars, extend its use to **exoplanet exploration**. Players could simulate rover missions on newly discovered exoplanets with varying terrain conditions. Data on terrain mapping could be fed into missions for building infrastructure or finding colonization zones.

---

### 2. **Planet 4** (Classifying satellite pics of Mars’ surface)

**Mission**:  
**"Martian Base Mapping"**

- **Objective**: Help establish **permanent bases** on Mars by classifying satellite images to find ideal sites for community structures (greenhouses, research stations).
- **Upload**: Players can upload their **satellite maps** or rover camera imagery. They could also upload simulated models of proposed structures.
- **Read Data**: Classify terrain features (craters, dunes, ice caps) and assess which regions are most stable for construction.
- **Relevance to Exoplanets**: The same techniques for mapping Mars could be extended to **exoplanet surfaces**, allowing players to contribute to finding colonization points and identifying geographical hazards.

---

### 3. **Rovers of Mars** (Classifying pictures from Martian rovers)

**Mission**:  
**"Habitat Pathfinder"**

- **Objective**: Using **rover images**, help identify potential resources (water ice, minerals) for constructing **community habitats**.
- **Upload**: Players upload their own rover-based imagery (e.g., from Mars missions) or simulations of base construction on specific Mars locations.
- **Read Data**: Classify and tag geological formations in rover images to assess their usefulness for future resource extraction.
- **Relevance to Exoplanets**: This mission could be a prototype for **resource-gathering on exoplanets**, extending the rover classification techniques to new worlds.

---

### 4. **Planet Hunters** (TESS/Kepler)

**Mission**:  
**"Exoplanet Research Hub"**

- **Objective**: Establish a **research outpost** around newly discovered exoplanets to analyze planetary atmospheres and potential habitability.
- **Upload**: Players upload their own **light curve data** from TESS/Kepler missions (or from simulations, telescopes, or NINA plugin). They could also share stellar parameter data from **TIC IDs** to refine models of exoplanet atmospheres.
- **Read Data**: Community members classify light curves to identify **transiting exoplanets** and interpret star/planetary atmospheric conditions (e.g., presence of water, CO2, or other gases).
- **Relevance to Exoplanets**: By combining light curve data with **stellar parameters** (such as from the TIC ID or Gaia data), users could estimate exoplanetary **atmospheric compositions** using models (e.g., by observing light filtering through atmospheres during transits).

---

### 5. **Minor Planet Hunt** (Search for asteroids)

**Mission**:  
**"Asteroid Mining Colony"**

- **Objective**: Identify **asteroids** that could serve as mining targets for future space colonies. Establish mining bases for extracting valuable resources like water or metals.
- **Upload**: Players upload asteroid images or simulations of asteroid encounters, including trajectory data.
- **Read Data**: Classify potential asteroids, tagging those that are rich in resources and suitable for mining missions.
- **Relevance to Exoplanets**: Mining asteroids in our Solar System could eventually be extended to **exoplanetary systems** where asteroid belts could provide resources for building community infrastructure on exoplanets.

---

### 6. **Disk Detective** (Hunting for early solar system formations)

**Mission**:  
**"Protoplanetary Structure Mapping"**

- **Objective**: Classify **protoplanetary disks** to help plan infrastructure (satellite arrays, research stations) around newly forming solar systems.
- **Upload**: Users upload **astrophotography** of protoplanetary disks or simulated disk models.
- **Read Data**: Classify images of disks to locate regions where planets are likely forming, using this information to predict where infrastructure will be most valuable for future explorations.
- **Relevance to Exoplanets**: This project could help identify potential **exoplanet formation zones** around young stars, enabling future missions to study planetary evolution from an infrastructure perspective.

---

### 7. **Martian Cloud Survey** (Meteorology)

**Mission**:  
**"Mars Weather Station Network"**

- **Objective**: Establish a network of **weather stations** on Mars to monitor atmospheric conditions for future missions and colony stability.
- **Upload**: Players upload Martian cloud images or their own **weather station data** from simulations or real-world weather-tracking devices.
- **Read Data**: Classify Martian weather patterns (dust storms, cloud formations) to help determine safe windows for launching new missions or building infrastructure.
- **Relevance to Exoplanets**: The techniques used to study Martian clouds could be extended to studying **exoplanetary atmospheres**, helping predict weather patterns and plan construction on new worlds.

---

### 8. **Jovian Vortex/Cloud Hunter** (Jupiter weather)

**Mission**:  
**"Jovian Atmospheric Research Station"**

- **Objective**: Build a **floating weather station** in Jupiter’s upper atmosphere to study **Jovian clouds** and vortex patterns.
- **Upload**: Players upload images or simulations of Jupiter’s atmosphere (from telescopes or spacecraft data).
- **Read Data**: Classify cloud structures, vortices, and storm systems on Jupiter.
- **Relevance to Exoplanets**: This data can help create models for **gas giant exoplanets** with similar atmospheric conditions. By identifying patterns in Jupiter’s clouds, players could help predict conditions on other gas giants in exoplanetary systems.

---

### 9. **Cosmic Muon Hunters** (High-energy particle tracking)

**Mission**:  
**"Cosmic Particle Detector Array"**

- **Objective**: Set up a **network of particle detectors** on Earth and in space to track high-energy cosmic particles, including muons and neutrinos.
- **Upload**: Players upload particle detector data or simulations of **cosmic ray events** from both Earth and interplanetary missions.
- **Read Data**: Classify cosmic ray and muon events to track how they interact with different planetary atmospheres or interstellar space.
- **Relevance to Exoplanets**: High-energy particles can affect exoplanet atmospheres and potential habitability. This mission could be extended to study **cosmic ray interactions** with exoplanet atmospheres, helping determine which planets are most suitable for colonization based on radiation levels.

---

### 10. **Name that Neutrino** (Neutrino classification)

**Mission**:  
**"Neutrino Observatory"**

- **Objective**: Establish a **neutrino detection station** on Earth or a nearby celestial body to track **neutrinos** from cosmic and planetary events.
- **Upload**: Players upload neutrino detection data (from simulations or detectors), contributing to the global effort to map neutrino interactions with different planetary environments.
- **Read Data**: Classify neutrino interactions and trace their sources (e.g., supernovae, black holes, or planetary cores).
- **Relevance to Exoplanets**: Neutrino tracking can be applied to **exoplanetary science** by studying neutrinos from distant stars, providing clues about the **stellar environments** around which exoplanets orbit.

---

### **SETI Signal Classification** (Bonus)

**Mission**:  
**"SETI Listening Post"**

- **Objective**: Establish a **community listening post** on a remote planet (after Chapter 2) to detect and classify potential extraterrestrial signals.
- **Upload**: Players can upload radio signals detected from Earth-based SETI projects or their own amateur radio telescopes.
- **Read Data**: Classify signals (e.g., fast radio bursts, regular radio transmissions) and analyze their patterns for signs of intelligence.
- **Relevance to Exoplanets**: Players could search for **SETI signals** around exoplanets they’ve helped discover in earlier missions. By combining this data with planetary atmospheric models, they could narrow down the search for extraterrestrial life.

---

These community missions aim to tie together **real science** and **game mechanics**, involving both the **uploading** and **reading** of data to create meaningful contributions. With the potential for **exoplanet** exploration, players can progress from local discoveries (like Mars weather or minor planets) to larger-scale endeavors



----
[[Field Guide]] 
https://chatgpt.com/c/670b2ead-18cc-800b-8e5e-d1bc45b38ec4