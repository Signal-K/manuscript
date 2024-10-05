---
sticker: lucide//divide-square
tags:
  - Missions
  - Dialogue
  - Chapter-1
  - Chapter-2
  - Star-Sailors
  - Tutorial
---
By the time the user loads onto their planet, they'll already have completed the first mission ( #Initialisation of the #Chapters #Chapter-1 ) and chosen their first classification, so we don't need to have any dialogue around this. I think we'll still show "Chosen first classification" in the component though so the user can see what they've done.

Then, we should group all tutorial missions together, and all "first" (second) classification missions together as well. We determine their active mission by looking at the structure they have on #Earth and the modules that it has unlocked, and then highlight that mission in the Tutorial & First sections.

> You chose {$classificationChoice}, click on the {structureName} and then {relevantstructureButton} to go through the tutorial

(Research #Initialisation component shown here)

> You've completed the tutorial for {$completedTutorial}. If you'd like you can now classify some other objects or continue working on the same project

Then we can group the next set of missions together and start travelling off-world -
> What would you like to do?
> Travel and establish a base on a planet in our #Solar-System ?
> Research new projects to contribute to > New structure || New module
> Continue my current project

We need to figure out if the user is forced to use the #Research station for more modules/structures before travelling (they're already required to do so to unlock the Spaceship & Launchpad). 
I also need to come up with a new UI for the Research Station (maybe tabbed pagination separating the structures based on category e.g. Transport, Classifications)