---
sticker: lucide//building-2
---
# Bumble Tasks

Project: [[index|Bumble]]

## 🔥 High Priority

> Tasks marked as urgent or high priority

```dataview
TASK
WHERE file = this.file
  AND !completed
  AND (contains(text, "🔥") OR contains(text, "⚡"))
SORT text ASC
```

## 📋 Active Tasks

> All incomplete tasks for this project

```dataview
TASK
WHERE file = this.file
  AND !completed
SORT text ASC
```

## ✅ Recently Completed

> Last 10 completed tasks

```dataview
TASK
WHERE file = this.file
  AND completed
SORT completion DESC
LIMIT 10
```

---

## Tasks

### Technical Integration
- [ ] 🔼 📅 2025-11-10 🆔 c57qdy Godot scene takes basic params and user values from Expo #godot #integration
- [ ] Add virtual/on-screen controls in Godot that work in RN, if it detects user is using application in a mobile environment #Controls #Godot

### Harvesting & Resources
- [ ] Implement harvesting mechanics in Godot
- [ ] Develop nectar system in RN (honey refineries/automations)
- [ ] Determine what happens when nectar is full (honey harvesting with glass bottles?)

### UI/Visual
- [ ] Design clean and minimal classification UI that matches agricultural texture/style
- [ ] Overhaul text/background pages - current version looks bad
- [ ] Create additional sprites: player character, trees, flowers
- [ ] Create identical layout scenes with different colors for different biomes

### Game Systems
- [ ] Build data dictionary for crop-nectar relationships
- [ ] Implement orders/puzzle game mechanic
- [ ] Develop water replenishment system (hourly or weather-based)
- [ ] Create upgradeable water tank system for hive screen
- [ ] Implement "income" collection system when returning to game

### Onboarding
- [ ] Create script to remove guest accounts locally that are >1 day old
- [ ] Implement guest account merge with existing account feature

### Bee Management System
- [ ] Implement sophisticated hive population system (3-10 bee capacity)
- [ ] Create bee growth rate system (one bee per day progression)
- [ ] Build honey production pipeline (nectar collection → storage → processing)
- [ ] Add bee specialization system (collection, production, soldier types)
- [ ] Implement classification reward system (new bees or yield bonuses)

### Tech Tree & Progression
- [ ] Design plot expansion upgrade system
- [ ] Create inventory upgrade levels (10 → 50 → 100 slots)
- [ ] Implement crafting recipe unlocks at Level 5
- [ ] Build XP and leveling system with balanced progression curve
- [ ] Add hydroponics progression path

### Resource Systems
- [ ] Implement power, water, and material management
- [ ] Create advanced solar supply system
- [ ] Build offline value display systems
- [ ] Add material diversification (multiple input/output types)

### Second Mission - Grid System
- [ ] Create grid-based second mission structure
- [ ] Implement base building with crafting integration
- [ ] Add resource collection and processing mechanics
- [ ] Build crafting recipe system for grid mission

### Documentation
- [ ] Document game loop for distribution feedback
- [ ] Write up classification UI integration approach

**Related Documentation:**
- [[Game-Mechanics]]
- [[UI-Design]]
- [[Godot-Integration]]
- [[User-Onboarding]]
- [[Bee-Management]]
- [[Tech-Tree]]
