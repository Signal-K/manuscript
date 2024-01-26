---
title: New Page Layout
tags:
  - Star-Sailors
  - Ticket
  - Card
  - Content
---

New page layout

Jira tag: 

Concept ->
1. We've been building the v2 layout assuming that we need to have all the information viewable on a single scrollable feed
2. While we are going to implement a single page layout for navigation/"lite" mode (see `SSF-3` possibly), this isn't the best course of action for `/planets` or `/sector` routes for the following reasons:
	1. There is way too much information to have in a single column (as the length/height of the page will be too high), but there needs to be sufficient width to each column (so as to not have the data visualisations/other content incorrectly formatted). On laptops or tablets, this results in a screen size that can't fix one problem without encountering the other
	2. (mainly textual) Content on background is too much like a webapp. It doesn't feel like a game, especially on mobile

What content is actually going to be shown/used? (This is across both sectors & planets as there will be occasional overlap):
1. Planet data -> temperature, semi-major axis, eccentricity, etc
2. Lightkurves & other visualisations
3. Visual media (e.g. "cover" images)
4. Discussion board
5. Structures & structure content
6. Vehicles & exploration actions
7. Sector grid

What I propose now is treat all of these entities/components as "pop-up" components. I.e. each is hidden behind a structure or other [visual] asset on the planet's (or anomaly's) surface.
We already had the idea to have things like the telescope data (aka lightkurve blocks) only visible when clicking on your telescope, so why not extend this to other areas like a discussion board hidden behind a "satellite communicator device". This means that, especially on mobile, it feels more like a game, where you can see your world/sector being built up.

Getting the sector grid *just* right, and then getting the structure order of operations (for the end-user) in place, will go a long way to getting it ready. The "`createBar`" component will be especially useful for this.

`<ContentPlaceholder />` will be used for the "popup" components.

We need to figure out what the newly created structuregrid can be used for. Maybe a minimal mode?
We also need to get the user flow (not the signup, that can be done later) for actions like picking a planet in place.
Combination between minimal saas template & game. Perhaps difference between desktop&mobile layout is key.

Note -> we will experiment with a scrollable layout for accessibility purposes as well.