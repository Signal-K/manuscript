---
tags:
  - Editing
  - Sprint-Planning
  - Structures
  - "#Narrative"
sticker: lucide//twitter
banner: Pasted image 20240826204019.png
---
# A NOTE TO GO THROUGH TAB GROUP MINING (CHAPTER 1 V2.2)


# Onboarding
A note that structures are not visibly shown (or even initialised in the database) until Chapter 1 begins
**Data sources**
1. Lightcurves (`lightkurve` pip package) - Exoplanet candidates (`anomalies`: type: `planet`) }| Structure: "Telescope"
2. Roover photos (NASA `APPEEARS` database) - Landmarks "on-planet" and mineral deposits (`mineralDeposits` and `anomalies`: type: `roverImg`) | Structure: "Rover Structure?"

For the onboarding, that's it (for now. Is there any content we should add? Because this gives us the basic information required to "generate" the planet/instance. However, users will be using lightcurves to determine planet features e.g. mass, orbital period; this obviously can't be done AFTER they visit the planet. So do we just have a narrative note for the user for the base set to solve this plothole?)

# Chapter 1
**Citizen Science Modules**
1. Finding/classifying animal entities
	1. #zoodex 
2. Discovering more about "your planet"
	1. #Clouds #APPEEARs  #Surveyor (need to implement another Zooniverse project?)
	2. Roover photos - terrain
3. Finding new planets:
	1. #Lightkurve
	2. Telescope
4. Sunspots - affect some planet properties

Which of these structures should be based where (out of the "four" sections?)
What do satellites do? How do we avoid duplicating functionality? (just have a requirement, "child" structures/entities?)


Potentially we'll direct all rover findings & administration, customisation to the Automaton Structure (resurrecting from the dead!)

# Related
[[Sprint notes]]

# Notes
Was originally at [[Narrative]]