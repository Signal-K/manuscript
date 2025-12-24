---
type: segment-base
project: Bumble
segment: Core Gameplay
isNext: true
status: in-progress
banner: media/Pasted image 20251014125056.png
---

# Core Gameplay

## Stories in this Segment

```dataview
TABLE WITHOUT ID
  link(file.link, story) as "Story",
  priority as "Priority",
  status as "Status"
FROM "_Tasks/Bumble/Stories"
WHERE segment = "Core Gameplay"
SORT priority DESC, status ASC
```

## All Tasks in Segment

```dataview
TASK
FROM "_Tasks/Bumble/Stories"
WHERE segment = "Core Gameplay"
SORT !completed, priority DESC
```

## Segment Overview
Core gameplay mechanics that form the foundation of the Bumble experience, focusing on bee management, crop cultivation, and honey production systems.

## Progress Summary
- **Stories:** 5 active stories
- **Key Focus:** Bee colony management and agricultural systems
- **Status:** In active development


* [x] Make Godot window full-screen in Expo #Expo #godot-rn 🆔 ud5z4f ✅ 2025-12-22
* [ ] Function to show tasks overdue or with current date
