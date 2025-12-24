---
title: Comprehensive Project Summary - December 2025
date: 2025-12-14
tags:
  - meta
  - summary
  - overview
  - star-sailors
  - bumble
  - godot-mars
---

# 🌟 Comprehensive Project Summary - December 2025

## 🎮 **Bumble (Bee Management & Garden Simulation)**

### Core Concept Evolution
You're building Bumble as a **cozy farming game with pollinator ecology mechanics**, blending Stardew Valley-style resource management with citizen science education. The game has evolved significantly with clear design decisions emerging from your physical notes.

### Key Ideas & Mechanics

**Garden & Expansion System:**
- **Grid-based expansion** with different plot types (grape, mint, basil, greenhouse plots)
- **Weather effects** that impact garden plots and create seasonal transitions
- **Dynamic UI** for managing expanding garden spaces
- **Coral regions integration** - exploring coral classification as additional gameplay content

**Bee & Pollination Mechanics:**
- **Simplified honey production workflow** - Users collect honey (not raw nectar), bees automatically manage collection/processing
- **Hexagon-based hive system** with visual cross-section view to see honey storage
- **Pollination factor system** that triggers bee spawning based on plants, harvest history, and weather
- **Classification bonuses** - Classifying visiting bees increases yields through "better pollination"
- **XP system:** Harvesting (1 XP), Mass harvest (10 XP), Pollination (3 XP), Fair participation (2-4 XP)

**Fishing & Coral Minigame (Emerging Concept):**
- **Coral regions** as expansion content for Bumble
- **Simple classification interface** for coral identification
- **Integration with N31 regions** creating variety in gameplay
- **"Fishing brambles" system** - mentioned but needs further definition

### Questions/Struggles
- **Narrative framing:** "Don't want to romanticize leaving city life" - seeking alternatives to typical farming game narratives
- **Classification integration:** How to make bee/pollinator classification provide tangible narrative benefit beyond just mechanics
- **Honey vs nectar:** Wrestling with whether players collect raw nectar or processed honey (resolved: honey)
- **Space setting:** Questioning if space theme works for farming game or if it needs Earth-based setting

---

## 🔴 **Godot Mars (Mars Exploration & Colony Building)**

### Core Vision
A **mission-driven Mars colonization game** with construction mechanics, terrain exploration, and progressive system unlocking. Influenced by survival/crafting games but with structured mission progression.

### Key Systems Being Developed

**Terrain & Environment:**
- **Martian soil color palettes** implemented (completed Dec 12)
- **Multiple biomes:** Ice regions, crater formations, diverse terrain types
- **Weather system:** Dynamic weather affecting construction and resource gathering
- **Spider & cloud tilemaps** for environmental variety

**Construction & Base Building:**
- **Stellar construction missions** - Solar array building as first major project
- **Block-based construction** (solar panels, corner/cable connectors)
- **Sealing requirements** - Buildings must be complete and sealed for atmospheric integrity
- **Union transport system** for moving construction materials
- **Mission progression:** Solar → Hydroponics → Advanced facilities

**Early Game Mission Structure:**
- **Telegraph/communication systems** for early-game progression
- **Life support systems** requiring power infrastructure
- **Station building** with modular, flexible shapes
- **Progressive unlocking** of capabilities based on completed infrastructure

**Resource Management:**
- Inventory system
- Farming/crop growing (Mars agriculture)
- Save state integration (local or Supabase)
- Enemies/NPCs
- Day/date transition mechanics
- Block placement system
- Level building tools

### Integration with Star Sailors Ecosystem
- **Godot-RN template:** Building reusable framework for all Godot games
- **Supabase integration** for cross-platform saves and data
- **"View discoveries"** - Common feature linking all Star Sailors ecosystem games
- **Citizen science missions** planned for integration

### Questions/Struggles
- **Scope management:** Balancing demo vs full release features
- **Graphics complexity:** Keeping visuals simple enough to implement quickly while maintaining quality
- **Integration timing:** When to fully integrate into Star Sailors ecosystem vs standalone development

---

## ⭐ **Star Sailors (Citizen Science Web Platform)**

### Core Mission
**"Contributing to science through gamified astronomical data classification"** - Your flagship project connecting real research with engaging gameplay.

### Citizen Science Integration

**Real Data Sources:**
- **Planet classification** using real astronomical data (temperature, radius from TIC/KOI datasets)
- **NGTS integration** - New lightcurve types from NGTS research
- **Exoplanet data** from multiple scientific databases
- **User-generated observations** - Users can upload their own photos/observations

**Two-Way Contribution Model:**
- **Researchers → Users:** Big datasets need classification help
- **Users → Researchers:** Crowd-sourced observations (e.g., bird migrations, unusual sightings)
- **Example:** "Saw a red-tailed black cockatoo 20km outside its regular area? Upload photo, get in-game points, data goes to research maintainer"

**Scientific Authenticity:**
- **"Cannot present as confirmed until it actually is"** - Maintaining scientific integrity
- **Real formulas** for planet classification (Terrestrial/Gaseous/Ice based on parent star data)
- **External dataset prefixes** (KOI-xxx, TIC-xxx) for research integration
- **Spectroscopy data** and stellar metallicity values for sandbox content

### Current Development Focus

**V2.1 Bug Fixes & Patches (Current Segment):**
- **Ensure stable user experience:** Bug fixes and performance improvements
- **Allow users to navigate easily:** Mailing list integration, landing page improvements
- **Provide fast and responsive experience:** PostHog analytics, web scrapers, route optimization

**V3.0 Vision (Future):**
- **Implement user feedback** from Product Hunt launch
- **Rebuild missions/storyline** around projects users want to participate in
- **Advanced discovery features** and new user interface

### Platform Integration
- **Multiple game projects** feeding into one ecosystem:
  1. Star Sailors (web) - Main classification platform
  2. Bumble - Coming soon
  3. "Voxel"/Godot-Mars - Coming soon
- **Godot-RN template** allows multiple Godot builds in one React Native app
- **Deeplinks strategy** to avoid confusing users focused on specific mechanics

### Questions/Struggles
- **When to resume full-time web development** vs focusing on new game projects
- **Balancing act:** Not letting web version interfere with Godot games progress
- **User engagement:** Determining what mechanics users actually want through analytics and feedback
- **Multi-app strategy:** One app for all games vs separate apps with deeplinks?

---

## 🎯 **Cross-Project Themes & Design Philosophy**

### Overarching Vision
You're building a **"Star Sailors universe"** - an interconnected ecosystem of games that:
- **Ground gameplay in real science** without being purely educational
- **Contribute to actual research** through citizen science mechanics
- **Provide cozy, engaging gameplay** that respects players' time
- **Enable creative expression** through construction, discovery, and exploration

### Design Principles Emerging

**Anti-Patterns You're Avoiding:**
- **No romanticizing "leaving city life"** narratives
- **Not purely educational** - must have real gameplay value
- **Not Pokémon clones** - finding unique takes on collection/classification mechanics
- **Not overwhelming complexity** - keeping graphics and systems manageable for solo development

**What You're Seeking:**
- **Cozy but meaningful** - Games that feel good to play while contributing something real
- **Semi-sandbox freedom** - Users can build/explore but with some structure (like Crashlands/Stardew)
- **Survival-lite** - Limited resources without harsh punishment
- **Puzzle integration** - Order systems that become puzzle games
- **Real-world relevance** - Every mechanic should connect to something tangible

### Mechanics You Want Across Projects
1. **Construction** - Block-based building in both Bumble and Mars
2. **Fishing/Marine life** - Emerging coral classification concept
3. **Classification** - Core mechanic linking all games to science
4. **Exploration** - Discovery-driven gameplay
5. **Resource management** - Meaningful choices without grinding

### Content/Marketing Strategy
- **Product Hunt launch** for Star Sailors v2
- **"scroobl.es" website** consolidating all projects
- **Social media presence** needed but uncertain which platform
- **Devlog-style content** showing development process
- **Soft-launch approach** for new games

---

## 📝 **Current Challenges & Open Questions**

### Technical
- **Asset generation workflow:** Need local 3D/2D generators (maybe on Raspberry Pi?)
- **Godot-RN integration:** Ensuring timing/latency values remain strong
- **Save state architecture:** Local vs Supabase for different game types
- **Graphics pipeline:** Crashlands-style thick outlines, AI generation + manual cleanup

### Design
- **Bumble narrative:** What's the story/setting if not traditional farm game?
- **Coral/fishing integration:** How does this fit into Bumble's core loop?
- **Classification rewards:** Making citizen science feel meaningful in-game
- **Progression pacing:** Balancing XP systems, unlocks, and player agency

### Strategic
- **Time allocation:** When to focus on web Star Sailors vs Godot games?
- **Launch sequencing:** Bumble demo → Godot Mars → Integration into ecosystem?
- **Audience building:** How to start creating signal without becoming "content creator"?
- **Scope control:** What's truly MVP for each project segment?

---

## 🚀 **Next Steps & Momentum**

You've established clear organizational systems (segments, stories, project folders) and are actively developing across multiple fronts. The **coral/fishing minigame concept** is emerging as a bridge between Bumble's core mechanics and Star Sailors' classification focus. Your **mission-driven Godot Mars** structure is taking shape with concrete systems (stellar construction, terrain generation).

The key insight from your notes: You're building an **ecosystem**, not just separate games. Each project feeds into and supports the others, creating a unified "Star Sailors universe" where players contribute to real science while enjoying cozy, meaningful gameplay experiences.

---

## 📚 **Related Documentation**

- [[../Star-Sailors/|Star Sailors Project]]
- [[../Bumble/|Bumble Project]]
- [[../Godot-Mars/|Godot Mars Project]]
- [[../../Physical-Notes/|Physical Notes]]
- [[Meetings/|Project Meetings]]

---

*Generated: December 14, 2025*  
*Sources: Dashboard notes, Physical notes (Dec 4-8), Design proposals, Sprint documentation*
