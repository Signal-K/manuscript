---
tags:
  - Editing
  - Bugs
sticker: lucide//cloud-sun
---


Note: If you add anything to this page, I will kill you

1. ~~Lightkurve graph #3/4 on tutorial without readable background (remove transparency for borderline)~~
2. ~~Retract Cosmos' box after going through base graphs~~
3. Scrolling for t.scope classif. img not fixed (even though I said it was!)
4. Scrolling is even more retarded for the roover img classification in the tutorial (fix by arranging classification options in a grid)
5. Create icons for sidebar [mission title] items
6. Add a graphic/splash to the sidebar (desktop only) "STAR SAILORS"
7. Change ratio from 1/3 | 2/3 to 2/7 | 5/7
8. Roover photo containerised
9. Merge moonlight, starlight, novadust themes with custom hexes
10. ~~CENTRE THE FUCKING DEPLOY BUTTON [DIV]~~
	1. Roover button - see notebook for design
11. Increase res export of low pixel.count planets
12. ~~Make automaton configuration MEANINGFUL, be able to close it~~
13. ~~Onboarding next/back buttons should be in a fixed position regardless of content~~
14. File upload in `PostForm.tsx` no longer works
15. + all the mobile issues

TO-DO FOR LATER LIAM: organise these into boards


## Mining scene
Structures - clicking on one structure prevents being able to open others
* Also structures keep moving to the center and back again
* Bring actions back when there's a use for them
* Backgrounds and correct height-spacing for expansion
* Can't open the same structure after closing it

### Structures
[[Tickets|Tickets]] ->
1. ~~Upgrade automaton doesn't work if there's multiple automatons~~
2. Expanded don't scroll
3. Seems that they aren't being split again (we're re-using the `StructuresOnPlanet` component)

## Missions
1. Sessions seem to be having issues
2. Inventory items not stacking after mining event
3. [SGV2-179] Structures are being duplicated when users revert to original (first) classification choice

# Modules
1. Telescope: anomalySet: planets2 (what is the "second set" referred to as db-side, is it even worth having sets?)

# Automatons
1. Multiple automatons on a single planet screw things up (everything)