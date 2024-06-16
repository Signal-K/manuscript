---
connie-publish: true
sticker: emoji//1f4a2
connie-page-id: "24412274"
---


Mining stations will only be able to be placed in a specific sector and probably will only allow for the user to select a compatible mining deposit on that sector, which can be depleted?

Maybe you'll need to dig deeper to be able to collect more, as in there's multiple layers (each sector keeps a record of the level it's at, maybe via configuration (configuration is good because we don't need to have multiple new migrations and can have different values in multiple rows [in the same table] without having empty/whitespace)). 

Automatons are mainly used to find new sectors (this is something we could do for the UI cleanup sprint, inventing sectors). They have to do a bit of "base setting up" for the sector to be able to have things like mining stations work. 