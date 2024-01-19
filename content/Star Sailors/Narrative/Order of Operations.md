---
title: Star Sailors - Crafting & Inventory Operations
tags:
  - Star-Sailors
  - Content
  - Narrative
  - Planning
  - Sector
---
> Raw material [combination] → base building block → tool/structure/vehicle or other entity

Current setup:
1. /Gather page -> list of all sectors, ability to create new sectors
2. Create sector -> Take a random raw material, add that as the mineral deposit for the sector

It would probably be a good idea to get a list of all the files relevant to the gather and sector components to begin identifying possible duplication/code redundancy. 

`<ImagesGrid` component needs to be removed, and replaced with a function that takes all the [public] sectors and displays them. Currently it just shows a random set of images as a demo.

## Creating a sector
1. Check to see what planet a user currently "owns" (aka has set as their home planet. This is currently a manual process, in `profiles.location`, this is a part of our workflow we have to setup soon as well)
2. Currently the client chooses between silicates & coal when choosing the resource to be a part of the sector
3. A new rover image/cover image (so not required to be from a rover) SHOULD be generated, however we have it set to select the same one each time (for now): `coverUrl: "https://mars.nasa.gov/mars2020-raw-images/pub/ods/surface/sol/00090/ids/edr/browse/edl/EBE_0090_0674952393_193ECM_N0040048EDLC00090_0030LUJ01_1200.jpg",`. This should be fixed as well