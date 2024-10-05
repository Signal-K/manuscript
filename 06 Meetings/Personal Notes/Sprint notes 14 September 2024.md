---
sticker: lucide//file-plus-2
tags:
  - Active-Sprint
  - Chapter-1
---
1. Combine [[Research topics for Chapter 1]]&& [[Chapter 1 Research scope]] 
2. ~~Implement test/couple words of dialogue for each mission~~, test out Rhys' fix
3. ~~Report on~~ [[What's left]]
4. ~~[[01 Chapter 2/Tickets to revisit]] && #Tickets priority, figure out lead into #Chapter-2 & scope for novelty components~~
~~5. Fix [[02 Chapter 2]]&& [[01 Chapter 2]]~~
6. ~~Plan scope & initial story treatment for #Chapter-2 ,~~ set up sprint board, infrastructure plan and strict novelty pipeline including postcards
7. > ~~Now update it so that clicking "unlock" on a STRUCTURE creates an entry in `inventory` table (as well as in `unlocked_technology`) where `anomaly` = `activePlanet.id`, `owner` = `session.user.id` and `item` = `structure.id`~~
	1. And any additional things.
8. [[12 September 2024]]
9. ~~Fix issue with deposits generating from rover photos~~
10. ~~What's left for `SGV2-196`~~
11. ~~Fix issue with structures not displaying on frontend~~
	1. Figure out why #Automatons are and #Structures aren't, it's probably something to do with [[Dialogue]]


Quick report on [[What's left]]:
1. ~~Once [[Mission list]]is finished, we need to go through how #CaptnCosmos looks on mobile (along with the rest of the UI)~~
2. ~~I'm implementing the #RoversS image spinner, maybe we could have some sort of animation for this later?~~

Fix `MiningScene` in `Properties`
### `SGV2-196` (what's left)
1. Documentation for pipeline for `unlocked_technologies` table, what needs to happen once we move past the hacky #Inventory table implementation ( [[Migrating to unlocked_technologies table]])
2. Tie in with #Missions table to show what the user has done, allow the user to unlock new technology (essentially, creating that new object)
3. ~~`classification/researchPoints` implementation so that the user has to spend their rewards to unlock new tech ( starting in #Chapter-2  [[Transition]] we'll require crafting as well). Show the classification experience balance and some dialogue explaining what's going on.~~
4. Update the mission based on what the user selects, tie in with `activeMission` for allowing the user to build/research new structures
5. Automaton configuration will not be introduced until #Chapter-2 I feel

So we need to integrate the structure modal for the Research station, get that to appear, and then do everything all over again