---
tags:
  - Editing
  - Sprint-Planning
  - Sprints
  - Star-Sailors
sticker: lucide//flower
---
```jira-count

```
# What's remaining?
## Cleanup of Onboarding
[[Currently editing]]
1. Loading bar
2. Maybe some better explanations? (about gameplay)
3. Distribute user correctly
4. Fix planet generator (planet type (estimate), storage image, improve icons)
5. Rover image source display
6. Mobile floating menu
7. Dialogue timing
8. Inverted classification graph
9. Mobile UI changes (as per Rhys' input)
10. API route for all classification options
11. Profile colour scheme
12. 

## Global/infra
1. `mineralDeposits` items not being rendered?
2. Inconsistent anomaly images between buckets
3. Microblog - get entry & feedback from Rhys & Fred
4. Show easy way to view terrarium
5. New background(s)

Split up this obsidian doc (and tags) coherently
Is there something we can push/pull Obsidian to?

## Chapter 1
1. Icons for everything

### Mining
Order of operations:
1. View deposits (or find some new ones)
	1. Select the deposit you want to view
2. Further information, automaton select
3. Automaton configuration, "send"
4. Timer, automaton "mining" stats/c.panel, collect "earnings"
Integrate with journal/mission log, show structures available to build (maybe a building menu in the navbar or "redirect" back to the planet/index view)

Later features:
1. Paths/coordinates (user can customise the path the Automatons take, what they find)
2. Users can share/"give" deposits and other content

From a component perspective, we need to look at if the `time_of_deploy` field in the `inventory` table will be sufficient for this functionality

### Anomalies & structures
Content/user information:
1. Capt'n Cosmos gives the user some information about what they can focus on, we create a tech tree and "progression pathway" and the user has a bit of free reign from this point
2. Mission log shows what they can build, user selects topics/disciplines they're interested in and then are directed what to do to get there

## Some more gamification ideas
(no specific order, for now)
* User can search for "signs of" life (SETI content) after they've got a settlement and discovered some planet candidates
* Match signals to specific planet entities in the database
* Explore planets you settle, starting with the first set (because these are pre-configured to be the most habitable)
	* Explore how "Earth-like" animals behave on these planets, planetType and planet stats will affect the behaviour and slight anatomy
* Users theorise (based on their other content discoveries) about animal behaviour, results in a community-based filter for the zooniverse bio projects

We can then add things like atmosphere and biospheres to the planet stats/`configuration` and the generated image, resulting in a sort of terraforming minigame/mini-component. Users will need planets of different types to do/find different things (e.g. massive plate tectonics). Potentially experiments could also be conducted later on (mini-simulation engine).

# Sprint tickets (from Jira)
1. ~~Roovers being created without anomaly value~~
2. ~~Fix initial planet generator issues~~ & create new ticket SCOPE
3. ~~Tooltips for structures, as well as plan for internal notes & comparing with current Capt'n Cosmos, where does CC come back?~~
4. ~~SGV2-165~~
5. ~~Fix image bugs ↓~~
	Image bug fixed: ![[Pasted image 20240827195949.png]]
1. Other bugs
	1. Fix UI to remove forced scrolling (partial)
	1. Fix dialogue timing issues (partial)
1. SCOPE for new settlements :)

So I think I can go back to the mining ticket [for] now...

REVIEW:
1. [[Currently editing]]
2. [[00 Archive/Test/Structures]]

# Component-based
## Navigation & controllers
1. Inventory button & UI for header

Raspberry pi kit in-game?