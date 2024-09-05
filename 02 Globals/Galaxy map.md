---
sticker: lucide//plane
tags:
  - Components
  - Content
  - Anomalies
  - Classifications
  - Data-Population
  - Data-Sources
  - Database
  - Gameplay
  - Interface
  - Inventory
  - Locations
---
I'm assuming that most planet candidates in our network would be based in the Milky Way, so let's assume this is the case until further notice.

If everyone is based in one galaxy for now, that means that the galaxy the candidate/actual planet is located in cannot be considered to be a discriminator.
Distance & direction from an entity would probably be the best way to mark the relationship, potentially the galactic core or our own solar system (direction is required because two systems could be a similar distance but on opposite planes/sides). I think the only other reliable discriminator (in the absence of a credible coordinates system) would be the closest globular cluster.

That can be marked into the `anomalies.configuration` value for the planet [candidate]. 

Two sections/tabs:
1. All discovered planets
2. Your discovered planets