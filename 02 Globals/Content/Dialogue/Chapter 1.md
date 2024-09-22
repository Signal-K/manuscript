---
sticker: lucide//lock
tags:
  - Dialogue
  - Missions
  - Tutorial
  - Onboarding
  - Chapters
  - Chapter-1
  - Chapter-2
---
Related to [[Sprint notes 14 September 2024]]
# Mission notes
Perhaps we should have a transition scene?
Remember to update the end of [[01 Onboarding]]to clarify the user will be "landing" on their planet.

**"Initialise Chapter 1"**
> Welcome! You're now on your planet. Let's start doing some classifications. If you start something and don't like it, you'll then be able to change, so don't worry

**Choose first classification**
> Your objective is to learn more about the different planets you visit and compare them to the rest of the galaxy as well as our home - Earth! You can choose different disciplines to explore, like terrain formation or how animals from Earth behave on planets with vastly different gravity; all contributions are valuable. To complete your planet, you'll need to perform a few different surveys, and then you're free to travel to other planets and learn more; if you'd like

**Complete first classification**
> Now that you've chosen [ #Structure ] mission, you'll notice a new structure has appeared in your dashboard [the one that's bouncing]. You'll find all the data and information required to complete your mission there.

---

(Research structure appears after this point, but it has an `inventory.configuration` value of `{"Uses": 0}`).

---

**Go mining**
> You'll notice that a Research Station has appeared, but before you can use it you'll need to find some iron to repair it. Head to your Automaton station (the one that's bouncing) to send your rovers out and find some iron

(Function to add *1* iron deposit to `mineralDeposits` for the user's `anomaly` if there isn't one already).

^187aab
Tutorial text/dialogue for the mining action scene:
> When you were setting up this planet, your rover found a few points of interest that are shown here. When mining, you choose the deposit that you'd like to mine from, and send an automaton out to collect the minerals. Later on you'll be able to upgrade your automatons to increase their speed or the resources they can mine and bring back to you. You should probably start with collecting some iron as you'll need that to repair your Research Station.


**Repair research structure**
> By repairing the Research Station, you'll be able to unlock new technologies and things to explore. You've successfully mined some iron, which you can use to repair any kind of structure when its durability starts running low. Click on the structure and then navigate to the "Durability" field

**Research a new technology**
> As you've been informed, we require you to conduct further investigations on your planet, so use the Research Station to unlock a new technology structure that you can then find some new objects to classify.


## Ideas
[[#^187aab]]has given me an idea, for [[01 Chapter 2]]how about we build a tutorial engine for all the classification #Structures that can be revisited at any time.