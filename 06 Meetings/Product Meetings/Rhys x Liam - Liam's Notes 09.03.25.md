---
sticker: lucide//circle-ellipsis
tags:
  - Questions
  - Meetings
  - Sprint-Planning
---
For [[SSG-159]] && SSG-165

[[Rhys x Liam - 06.03.25]]

We currently have a very good mission link/tie-in between the following projects:
* Meteorology:
	* AI4Mars
	* Planet Four
	* Cloudspotting [on Mars]
	* Jovian Vortex Hunters
* Astronomy:
	* Planet Hunters

Additionally, we have the biological projects like Burrowing Owls and Plankton Portal, which essentially are part of your collection of 'biology stations' (we need to improve the wording of these things). 

Currently implemented biology projects:
1. Burrowing Owls (Desert Station)
2. Iguanas from Above (Desert Station)
3. Plankton Portal (Ocean Station)
4. Click-A-Coral (new) (Ocean Station)

We also have the pokedex idea - scan animals/plants/fungi around you and add them to a collection. [youtube inspiration here](https://www.youtube.com/watch?v=NBmLFMN0fdw)

The basic flow is seen from the Miro board, and I'll attach a few screenshots related to how I think life would form on the terrariums.

We have a few other projects that haven't really been well integrated into the flow:
1. Sunspots
2. Disk Detective
3. Daily Minor Planet / Active Asteroids

I think that's [hopefully] brought you up to speed now. I have some other questions at [[Rhys x Liam - 06.03.25]]but we'll leave that for another day.

Here's a spreadsheet showing some ideas around missions and what the user gets out of them (projects -> chapters -> missions): https://docs.google.com/spreadsheets/d/1gdMz0bRzCOSGYAFaYWB_oZnV8IsmfSRYkGJkV-exMfQ/edit?gid=0#gid=0 

Another basic (at least initially) project would be users uploading things like their climate/surroundings so that their place on #Earth is also active/interactive (more on this later)
## Important questions
We have a few things that we can take a look at implementing -
1. Weather Generator (Earth or terrariums) - this would be required for life to evolve
2. Research & upgrade tree for structures (e.g. being able to expand the distance your telescope can see, how many cameras your greenhouse stations have, etc). Could potentially be "funded" using the "points" you get for completing missions
3. Resource management - using automatons to hoover up minerals that are discovered while completing projects like AI4M/P4 (because these classifications insert soil types and behaviours to the planet configuration)
4. Adding the timing feature and turning it into more of a ''harvest/create cool things based on your input" game

 Additionally, here's some things that might need an overhaul -
1. Structure of the tutorial
2. Latency/speed/bugs/layout
3. Milestones and location of components on the display
4. Backgrounds & art (this is slowly being overhauled, emphasis on "slowly" for now)

The big problems I have (no specific order):
1. Latency & speed (side note, look at the codebase in `main` branch as of today - too many pages? Is an SPA the right way to go?)
2. Things feel too static, and you have to jump through too many hoops - load in, click a structure, click a project, click a mission, do the mission...not very intuitive. Most of the app is just a series of menus
3. Not enough content or things to do, not really much crossover between projects (this is slowly being fixed with the creation of terrariums (see `/planets/[id]/page.tsx`), but again, emphasis on "slowly")
4. A lot of components don't fit the page well, either on desktop or mobile



# Create a method/flow in GPT to map notes to tickets/components, and map things to notes/tasks/components to do/write-up