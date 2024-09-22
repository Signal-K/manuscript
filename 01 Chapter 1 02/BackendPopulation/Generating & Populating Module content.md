---
sticker: lucide//box-select
tags:
  - Data-Sources
  - Data-Population
  - Database
  - Jupyter
  - Lightkurve
  - Pip
---
# Planets
Formula:
1. Extract `TIC ID` values from `exofop.csv`
2. Compare with the values we already have in `anomalies` #Database table
3. Generate the `lightkurve` image, create a new folder in the `anomalies` bucket and a new entry in `anomalies` table

Example `anomalies.configuration` value [[Configurations]]:
```bash
{"mass": 1.039, "ticId": "Trappist-1", "radius": 1.045, "smaxis": 0.03749, "ticId2": "TOI 6838.05", "density": 5.009, "orbital_period": 9.21, "temperature_eq": 217.65}
```

So the `anomalies.configuration` value should be set to something like:
```bash
{"mass": null, "ticId": "TIC ID", "radius": null, "smaxis": null, "density": null, "orbital_period": null, "temperature_eq": null}
```

A question we need to figure out (see [[Database Tickets]]) is how we organise user's #Surveyor results

Later on, we'll introduce dynamic #Jupyter notebook #Code-Snippets so the user can try out more complex graphs with #phase-folded values based on custom #user-input

Perhaps we update the #Classifications #PostForm to have some additional values

# Adding to the database
I think we should add new rows to the database when we add storage items, taking the primary key/file name and making sure they're the same for each #Anomaly