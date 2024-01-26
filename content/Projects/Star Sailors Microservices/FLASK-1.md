---
title: Flask Microservice Creation
tags:
  - Star-Sailors
  - Flask
  - Content
  - Building
  - Structure
---
Goal -> a working Flask application, deployed, that is able to serve as the discriminator for crafting methods and can then be extended upon for other microservice capabilities as well as the data science & visualisation methods.

Tech stack ->
I'm using Railway.app to manage the deployment. I kickstarted things using their standard flask boilerplate/template, which does use HTML templates. I am going to experiment with standard CRUD responses (i.e. no frontend template, just an API response element via Postman/Insomnia) and see if that will work well.

# Overview of `sytizen` repository
Taking a look at the data [+ schemas/structures], routes & functions and seeing what we can salvage & archive.

`./app.py`:
* Global auth state -> for now our microservices will just take the `session` token from the client so we don't need this
* I do believe that this was housing the APPEARS project from the SpaceApps hackathon...a lot of the useful content there has already been lifted into the mars rover classification method

Possibly we should make microservice repos like `signal-k/papyrus` into a git submodule for `signal-k/sytizen`.

`kurve-pass.py` has been added as a script to investigate for visualisation & data extrapolation

We did have a planet generator (well, actually multiple) that might be able to be salvaged for use in visualisation. 

`data/appeears` should be investigated for further citizen science modules (which will be based on structures again)

I will review other branches later, right now I'm on `GP-8-Supabase-Unity...` for `sytizen`.