---
tags:
  - Classifications
  - Star-Sailors
  - Inventory
  - Content
sticker: lucide//door-closed
connie-publish: true
connie-page-id: "33849345"
---
Finally starting to bring this back from [CPW-2](https://signalk.atlassian.net/browse/CPW-2) ( [[NWs S5 Week 3]] ).

We should show a model of the planets the users are on, and when they make a classification, a little post card is created that they can share, save, and is placed into their inventory/profile.

The main utility is that it gives users something to share, especially if we allow them to customise things like the colour or orientation/setup of the planet. We could highlight a structure or object being observed as part of it.

I guess the other utility is that it serves (by extension) the generator requirement, in that to realise the postcard concept, we'll have to build the rest of the generator and come up with a way to implement it in a way the user can understand.

So, a little bit of "order of operations" planning is required:

1. By default, the layout will show the "profile picture" of the planet, which is probably going to be a randomly generated image that is set in `anomalies.avatar_url` (so we'll need to create another api function for this)
2. Once the user has started building things, the generator will start working its magic (maybe not always...). First it generates a fuzzy blob that symbolises the fact that it's a planet candidate that hasn't been confirmed yet. Then, after the confirmation, we get a solid but plain spheroid, showing that we don't know what type of planet (gas giant, ice giant, terrestrial, water world, etc) it is. The more classifications that are made, the more things are added to it
3. The generator would partially be based on a user's individual classifications of that particular anomaly, and also all other users' contributions for that anomaly. After the user discovers the basics, they then need to work together. We can implement a tech tree, faction storyline/narrative around acquiring blueprints to get certain information
4. Each classification gives the user a blueprint/postcard, showing the anomaly in its current state of discovery (by that user). Hence, two users can have slightly different cards if their progress is at different stages at the same time. Gradually, the `avatar_url` field  would change (this would be because it's a `configuration` value made up of data points, not necessarily a specific image). Each blueprint is linked by user and anomaly, meaning users can see how their "understanding" of an anomaly/object changes over time. 

I'm really happy with this narrative structure. But this is quite a lot to pull off, so I think we'll keep it relatively simple for now:
1. We create a component that renders a contribution in a nice way, along with the asset[s] that were part of that classification (uploaded images, `avatar_url` or any other assets part of `anomaly.configuration`, etc), and a pointer/qr code to the anomaly view (so we'll need to create a page or state as well that takes you to that anomaly. Maybe the pokedex could serve that purpose as well)
2. Users can save, share their postcard and also share it into the general discussion feed.
3. I'll create an api route that can customise a new field in `anomalies.configuration` called `avatar_points` or something and, I don't know...implement some sort of cool feature (maybe just adding a small tint to the postcard based on the user's submission in structure `14`?)

This general discussion feed is how we can start integrating with LP/AP/Farcaster short-term, as we just have to have a pointer back to the original post (since it's not an actual classification with all sorts of context & visuals), and it can therefore be shown in a frontend like Lenster or Yup with nothing missing. However, I'm not sure if we're ready to embark on publishing into the decentralised networks, mainly because I'm not convinced that there will be enough attention there for the effort to be warranted (will people even understand what's going on if they're seeing it in their Lens feed? I somehow doubt it - at least for now). Open-sourcing public data in our backups will be a good intermediary step, I think. Put them on radicle or something.