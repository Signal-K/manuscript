---
sticker: lucide//candy
tags:
  - Flask
  - Database
  - API
  - Data-Population
  - Data-Sources
  - Sytizen
  - Generator
---
The initial goals for our Flask instance will be as follows:
1. Pull data from #Classifications and #Anomalies tables to generate data/statistics
2. Generate #Lightkurve and any other data formats for #Anomalies 
3. Insertion of anomaly data, content and media into the #Supabase infrastructure

Github action to perform any migrations to cloud #Supabase instance from local migrations

And then close as many branches as possible in `signal-k/sytizen`. Preserve all old content/notebooks

Later on we could add an admin page to make it easier to upload this content?
We also need to figure out the deployment, but for now Flask doesn't require any deployment, so this isn't a priority.

Can we run python code inside the flask api and have it return to the frontend?

We should create a route that identifies the planet type and can "refresh" based on a user's classifications (the user will have to make multiple classifications across multiple days to do this as a rate-limiter). Additionally, users will be able to take all other users' #Classifications into account for this. [[01 Chapter 1 02/Classifications/#Zoodex mission scope|#Zoodex mission scope]]
Flask route to create new #planet #Anomalies and identify when to create new ones (including #Lightkurve s).