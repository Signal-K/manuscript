---
sticker: lucide//dog
tags:
  - Database
  - Configuration
  - Tags
---
# Classifications
Configuration should include:
1. Structure that created it
2. The mission the user was performing (if any)
3. Multiple choice answers

# Anomalies
Configuration obviously depends on the `anomalyType` but essentially will include the basic stats of a particular anomaly (these can be updated? )


Some questions:
1. Should `anomalies -> settings` be its own db table?

Perhaps we should add an `AutomatonConfiguration` block (like `StructureConfiguration` for #Structures ) so that users can see stats and some simple actions for their #Automatons ?