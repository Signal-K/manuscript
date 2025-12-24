---
title: Bumble - Godot Integration
tags:
  - bumble
  - godot
  - technical
  - architecture
date: 2025-12-11
source: "Daily notes Nov-Dec 2025"
---

# Godot Integration

## Current Status

**✅ Godot build has been integrated!** (Dec 10)

## Architecture Decisions

### React Native Integration

Using [born](https://github.com/borndotcom/react-native-godot) for RN-Godot integration

**Limitations:**
- Unable to run Godot scenes in web interface
- REQUIRES native apps (therefore developer licenses)
- Desktop version won't run in React Native
- Need Godot + Supabase direct integration for desktop
- Forces mobile-first UI approach

**Benefits:**
- `godot-react-native` is convenient stop-gap while building to get early users
- Allows rapid iteration

### Long-term Direction

**Decision:** Bumble and Godot build likely separate projects
- **Godot build:** Exploratory/narrative focused
- **Bumble:** Garden-facing like PvZ Zen Garden

This separation allows each to focus on their strengths.

## Technical Tasks

### Immediate
- [ ] Godot scene takes basic params and user values from Expo
- [ ] Add virtual/on-screen controls in Godot that work in RN
- [ ] Detect if user is using mobile environment
- [ ] Harvesting in Godot (implement mechanics)

### Integration Points
- [ ] Getting Expo version of Bumble "dockerized"
- [ ] Nectar development in RN (honey refineries/automations)

## Build Strategy

**Decision:** EAS build locally, consistently, is the way to go
- More reliable than cloud builds
- Better debugging capability
- Consistent environment

---

**Related:**
- [[Game-Mechanics|Game Mechanics]]
- [[UI-Design|UI Design]]
- [[../../_Tasks/Projects/Bumble/Tasks|Bumble Tasks]]
