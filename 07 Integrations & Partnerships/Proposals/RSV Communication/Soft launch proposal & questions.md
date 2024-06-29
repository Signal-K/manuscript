---
tags:
  - Communications
  - Partnerships
  - Questions
  - Updates-Announcements
connie-publish: true
connie-page-id: "32571393"
---
Hi Rob,

Just wanted to get in touch again to give you a bit of an update about the last ~two weeks. We've just started in the Buildspace Incubator (we're 2 weeks in, 4 to go) and are planning to do weekly soft launches in preparation for a release of our "V2.0" platform at the end of the incubator (and lead into Science Week back home in Australia). The goal of these updates is to make some progress on the features, usability and try and onboard some users (and achieve a high user retention %) during a time when there are going to be a lot of eyes on us (through the incubator). By the time we come out with the launch of Star Sailors 2, we want to have the following (I will explain these points below):

1. Citizen science gameplay consisting of exoplanet candidates, mars rover photos/media, mars cloud data and one animal conservation project
2. An "unlimited" amount of data for our users to classify and content to explore
3. A context-rich feed of classifications and a voting & reputation system implemented
4. Engaging & simple gameplay mechanics and loop so that our users can understand the mechanics and don't get lost

Right now we have gameplay mechanics set up for users to "travel" between planet candidates, establish mining settlements and deploy rovers to collect resources, and use these resources to build "data collection" structures like telescopes (these provide lightcurve transits for the user to classify), rover cameras (photos from the surface of Mars, via the Opportunity, Curiosity & Perseverance rovers), and weather equipment (cloud data from Mars). We also allow the user to "fill in" missing data points for exoplanet candidates, for example if records for a particular entity have "gravity" and "radius", but not "mass", users can use what they learn in-game to submit an entry. We want to expand this mechanic so our users can contribute to atmospheric composition projects (once we have some more data to use and finish developing the starting points).

As of now, I'm leaning towards implementing the "Wildwatch Burrowing Owl" project because all of the data is available on Github, meaning that we can very easily integrate the workflow into our game mechanics. For animal/plant projects, the storyline in the game would describe the real animals as in-game "alien life" on the planet the user is on, so there's a bit of creative liberty taken.

The core gameplay loop consists of exploring, collecting resources, building structures and classifying data. Last year, the first version of Star Sailors had a limited amount of data, all of which had to be inserted manually - and it was all lightcurve data. This meant that there would be a limited amount of content that was available for users to classify, so if all the planet candidates had been classified, users would have to wait for us to add more data. And it was a much simpler and "less fun" game loop for many people, because it was essentially just a microblogging service about pictures of transit events. This time, we want to integrate datasets like Exofop directly into Star Sailors (V2) so that there's no shortage of things for the user to discover. Additionally, we want to add more content outside of the citizen science/classification aspect, so having more in-game events and milestones is something we want to implement.

To ensure the validity of results, every data point will have to have multiple users submitting classifications before our "findings" are submitted back to the data providers (e.g. Exofop). This ensures that low quality submissions will not degrade the overall quality of our findings. We are currently experimenting with ways we integrate a "requirement to vote" setting into the overall mechanics; being a scientist in "real life" you often have to peer review and research others' submissions and creations, so why not in citizen science as well?

If we can get the current build to a point where there will always be something for our users to do after logging in, and the development environment is set up in a way that provides easy implementation of new citizen science modules, our team will be happy with launching it publicly.

Nights & Weekends Season 5 (the buildspace incubator) runs until July 27. We'd like to launch SS V2 between then and science week; as mentioned above it's likely to be the time where we'll have a lot of attention on us (when compared to a regular time of the year). Every Sunday (EU time) until then, we'll be launching dedicated weekly previews and sharing them on social media to try and get some users and see what we're doing right before the full launch.

Is there anything that you think would be good to see or implement other than what's been mentioned? I can share a link to the upcoming development preview once it's confirmed to all be working (fingers crossed some time tomorrow).

Other than that, hope you're well, and looking forward to hearing from you

L