---
connie-publish: true
sticker: lucide//ghost
connie-page-id: "28639294"
---

See [[Structures]] for more info

Each structure will have a context, action system, and in/output. Let's get started

### Telescope Signal Receiver
* Content: Icon for the structure, textual description
* Context: List of telescope modules that are added on top (e.g. Transiting Telescope).
* Action buttons: allows the user to navigate to the derivative modules or build new ones

### Transiting Telescope
* Content: Pulls a lightcurve for a specified/random (depending on mission progression) exoplanet candidate, as well as the structure icon   
* Context: Lightcurve image depends on the status of mission `8` for the user - if they've already classified their own/base planet, it gives them new ones
* Action: Classification form, which takes the image of the lightcurve, the option for additional media uploads/context, and also a button that shows all classifications made with that telescope (right now it only shows the base anomaly)

### Vehicle Structure
* Content: Structure icon, a list of automatons in the same setting (i.e. planet)
* Context: Allows the user to create a new automaton for free if they don't have one (at all). It also shows the automaton upgrades (via the automaton upgrade module)
* Action: Allows the user to navigate to any of the modules, or create a new automaton (if they currently don't have one)

### Surveyor
* Content: Structure icon, planet name, planet information
* Context: Identifies an area of the planet information that has not been filled in, and gives the user an opportunity to make a classification to complete it
* Action: A classification form allowing the user to fill in a value (currently gravity)

### Meteorology tool
* Content: Structure icon, image of a cloud, some basic meteorological information (to be implemented)
* Context: Takes the anomaly id as an identifier, however all of the cloud images are of Mars. So we need to come up with a way to make the anomalies more Mars-like, or maybe manipulate the cloud images to be more representative of the planets being observed...or build in a mission to Mars (lol). It also gets a random cloud image from the storage bucket and allows the user to classify it (note: we need to come up with a better decisioning engine)
* Action: Classification form allowing the user to discuss what they think is going on with the cloud

### Camera
* Content: Shows the structure icon
* Context: shown when looking through your upgrade station
* Action: It's a passive module, having it allows the automatons to "send" photos randomly to the Camera Receiving Station, which is part of the telescope network. This then has the real action (see below). Right now the only action is using it to build the CRS

