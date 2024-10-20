---
sticker: lucide//divide
tags:
  - Telescope
  - Telescopes
  - planet
  - Planets
  - planetsets
  - Modules
  - Lightkurve
  - Transit
  - Missions
  - Chapter-2
  - Chapter-3
  - Chapters
---
Mission flow: after users progress through the rest of #Chapter-2 , users are then able to discover and classify their first planet -
1. Build the telescope and unlock the TESS/planet hunting mission
2. Go through the tutorial (if you haven't yet completed the mission) and then make a classification of the lightcurve that has been presented
3. Make a classification, produce an output, and we can then calculate the rough planet type
--
Fuel collection mission
..
4. User visits the planet and chooses their first activity (based on current user path)

So we need to determine the planet type based on initial data (pre-filled), and then what the user proposes ( #Surveyor ). Down the line we'll get star temperatures and other data to add to the pre-fill content, and also generate lightcurves & TIC ids dynamically and add them to the `anomalies` table.