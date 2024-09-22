---
sticker: lucide//dog
tags:
  - Planets
  - Anomalies
  - Structures
  - Citizen-Science
  - Classifications
  - Data-Sources
  - Data-Population
  - Gameplay
  - Lightkurve
  - Jupyter
  - Modules
  - Star-Sailors
  - Transit
---
# #Onboarding 
User is given a random `activePlanet` from the "base planet" set, these have lightcurves attached manually in the database.

# #Chapter-1 
I think the simplest way to begin to integrate this will just be to get some more planet candidates manually added to the `anomalies` table.
At some point I'll create an automation that will fetch TIC/KIC ids and then strip out the lightcurve, and upload the file and row data to #Supabase 

Should we have more complex graphs during [[01 Chapter 1]] e.g. #phase-folded or #pixelpoint?

# #Chapter-2 
I'd like (at some point) to have some sort of interactive deepnote or jupyter editor in the telescope. For now, though, we have to do it manually :(