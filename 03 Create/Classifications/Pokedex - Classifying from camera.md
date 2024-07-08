---
tags:
  - Modules
  - Citizen-Science
  - Classifications
connie-publish: true
sticker: lucide//bean-off
connie-page-id: "34242561"
---
We'll need to change the layout on desktop so that it's an upload image button.
Images need to be stored/upload to supabase 

We're going to need to implement some functions so that images above `512*512` are adjusted and not uploaded directly (due to costs) but also not removed from the pipeline either

The minimum requirement is getting user data (the supabase session) linked with a submission. We can probably just roll with the original placeholder for everything else, if push comes to shove.

*Update*:
Minimum requirements have changed. I'll create a module/structure that allows users to upload a photo, tag a location and animal type, and submit it, as well as view all their previous submissions. Everything will be on-Supabase (postgres). I'm going to work with Rhys for the RL application setup and will put the API keys into my next invoice...



