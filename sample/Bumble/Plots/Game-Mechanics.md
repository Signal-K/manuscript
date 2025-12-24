---
title: Bumble - Game Mechanics & Systems
tags:
  - bumble
  - game-design
  - mechanics
date: 2025-12-11
source: "Daily notes Nov-Dec 2025"
---

# Game Mechanics & Systems

## Pollination System

### Hive Management
- Every user starts with one beehive
- Every harvest increases "pollination factor"
- Once pollination factor > 5, bees start spawning based on:
  - Plants in garden
  - Harvest history
  - Current weather

### Bee Behavior
- Bees leave hive at random times during the day
- Clicking bees opens classification dialogue
- Clicking bees adds extra nectar to hive
- Nectar also pools throughout day based on number of bees in each hive
- Need to determine what happens when nectar is full (honey harvesting with glass bottles?)

### Classification Integration
**Key Decision:** Classification should provide bonus rather than being required for growth

- Classifications produce higher yields because "more pollination" occurs
- "Who's visiting" task only available pre-harvest
- Challenge: How to make classifying pollinators provide tangible benefit narratively

## Resource Management

### Water System
- Water replenishes hourly or when weather changes (if it rains)
- Water tank shown in hive screen (upgradeable)
- Track old balance when leaving game
- User must click to receive "income" when returning

### Food System
- Food needs to be purchased or crafted
- Crafting grid/UI should be simple like old MCPE crafting UI

### Nectar & Honey Production (Updated Dec 6)
- **New System:** Users collect honey, not nectar directly
- **Processing Required:** Honey must be processed before selling
- Bees automatically manage nectar collection and processing
- **Bee Workflow:**
  1. Bees collect nectar throughout the day (visual mechanics)
  2. Nectar turns into honey as bees process it
  3. Honey deposited into hive hexagons periodically
  4. Hexagons fill up and user can harvest honey
- User can switch to cross-section view to see hive hexagon status
- **Cleaner process** that's easily supportable and automated

### Each flower/crop type produces different nectar
- Needs data dictionary for crop-nectar relationships
- Nectar pools in hive throughout day
- Future: honey harvesting mechanic

## Game Loop Ideas

### Stardew Valley-Inspired
- Farm honey as primary resource
- Each flower/crop type produces different nectar types
- Different nectar = different honey varieties
- Don't want to romanticize leaving "city life" - sick of that narrative
- No good setting for narrative yet (space not plausible)
- Building foundations like other SV clones for now

### Orders/Puzzle System
- Orders idea is good - turn into puzzle game
- Specific implementation TBD

## Experience & Leveling System (Dec 8)

### XP Point Values
- **Harvest plant:** 1 XP point
- **Mass harvest (+5):** 10 XP points  
- **Pollination:** 3 XP points (difficulty dependent)
- **Fair participation:** 2-4 XP points

### XP Spending & Unlocks
- **Craft new buildings:** 50 XP points spent
- **Unlock system** tied to XP thresholds
- **Large buildings** require higher XP investment
- **Tech tree progression** straightforward implementation

### Seasonal & Plant Management
- **Vegetables available** system with variety
- **Seasonal landscape** changes affect gameplay
- **Pollinator classification** integration provides benefits
- **Farmer/bee interaction** mechanics

## Technical Considerations

### Game Object Approach
- Treating everything like game objects is genius approach
- Allows flexible, modular design

---

**Related:**
- [[UI-Design|UI Design Decisions]]
- [[Citizen-Science-Integration|Citizen Science Integration]]
- [[../../_Tasks/Projects/Bumble/Tasks|Bumble Tasks]]
