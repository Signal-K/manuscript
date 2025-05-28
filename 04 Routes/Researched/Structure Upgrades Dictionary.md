---
sticker: lucide//cloud-sun-rain
tags:
  - Structure
  - Structures
  - upgrades
  - Research
  - researched
---
# Astronomers
#Astronomers #Astronomer 
## Telescopes
#Telescope #Telescopes #Structure #Structures 
### Probes
1. If no entry in `researched` table relating to #Probe  (value: `probecount`), then we have 1 probe
2. If 1 entry, we have 2 probes
3. If 2 entries, we have 3 probes [for that telescope]

Later, I'll probably have to update this for scenarios where you may have probes assigned to/controlled by different telescopes...but we'll cross that bridge when we come to it.

### Range
1. If no entry in `researched` table relating to `proberange`, range is shown to be 1,000 LY
2. If 1 entry, 2,000 LY
3. 2 entries = 3,000 LY


# Stardust
Calculate/add up the total of all tech research and remove/hide that total from the overall #Stardust value

# Meteorologists
#Meteorologists 
## Probes
The first value/multiplier thing is how many events per terrarium we can identify each week (or other designated time frame). So, the next order of business is to identify all events that can occur, when they can occur (biome & surveyor values taken into account). As of the time of writing (10am GMT+1 on the 28th April 2025) , we can identify if any weather events on a terrarium have been 'redeemed' (i.e. added to the `events` #events table).

Increasing `probecount` #probecount increases this. I think that's a reasonable first step.

The #Weather-Balloon structure should show recent events/storms that have occurred. There won't be a limit on #anomalies discovered by the balloon...for now.

- [ ] Show event creation formula
- [ ] Test event creation in `events` table for current #milestones route
- [ ] Show a message describing when the next #events are due for each location

I'm going to map out the event creation & upload formula on my flight to REK

## item types
I'm going to have a sample value #ballooncount `ballooncount` purely as a placeholder for future, [currently unatainable] #Meteorologists tech

## Anomaly discovery
This will include #upload

I think a reasonable step is to say that users can #upload one event from real life per week. I don't really see how we can work an upgrade system in at this point.

### On planets
Users will send out a probe (with a balloon) to a planet and it will return with an anomaly...they select the planet they want (let's get #Mars & #Jupiter integrated into this selection process, but not worry about the generator component for now).

- [x] Allow users to add anomalies to #Mars / #Jupiter ✅ 2025-04-28 - #SSM-116 #SSM-126

**How does this relate to #milestones ?**
So as described in #SSG-193, there (for now) won't be any limit on how many anomalies can be discovered by the #Weather-Balloon . The only limit is how many #events can be discovered per week. Because of this, we won't have any limits on milestones either. 

# Biologists
#biologists 
Let's not worry about upload mechanics for now...let's just start with `cameraCount` and `stationSize`.
The page should also show the current researched #BiodomeStation s.

# Stardust & Milestones
#Stardust #milestones 
At the end of every week, (maybe we have this accessible on-repeat) we need to show the user what they've earned in relation to the milestones. So I think what we need to do is update the #milestones #api route to add an xp value, and this is what determines how much #Stardust is rewarded for milestones.
So we're saying that for every task done, you get 1 point, up to the maximum for that milestone. Then it's 0.5 points (rounded DOWN to the nearest whole number) per task.

So, the outcome of these notes are:
- [ ] Stardust total calculation to take into account the xp value and the total number of tasks performed with milestones
- [ ] Stardust to be increased for milestones, general '1'? point value for other tasks
- [x] Update `totalPoints` to be based on #stardust spent... ✅ 2025-04-28


![[Pasted image 20250430122751.png]]