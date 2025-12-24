---
title: Meta Project
icon: lucide//settings
tags:
  - meta
  - project
  - general
---

# 🔧 Meta Project

**Type:** Cross-Project Organization  
**Purpose:** General project management, meetings, and cross-cutting concerns  

## Overview

The Meta project contains documentation and resources that span across all projects, including general game design ideas, project meetings, and organizational resources.

## Project Structure

- **[Games](Games/)** - Game design concepts and ideas
- **[Ideas](Ideas/)** - General brainstorming and concepts  
- **[Meetings](Meetings/)** - Project meetings and reviews
- **[Research](Research/)** - Cross-project research and findings

## Recent Meetings

```dataview
TABLE WITHOUT ID
  file.name as "Meeting",
  file.mtime as "Date"
FROM "content/_Tasks/Projects/Meta/Meetings"
SORT file.mtime DESC
LIMIT 5
```

---

## 🔗 Related Projects

- [[../Star-Sailors/|Star Sailors]] - Web application project
- [[../Bumble/|Bumble]] - Game development project  
- [[../Godot-Mars/|Godot Mars]] - Mars exploration game