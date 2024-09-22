---
sticker: lucide//clock-2
banner: background1.jpeg
tags:
  - Star-Sailors
  - Starnet
  - Narrative
  - Chapters
---
So, here we are again, another chapter rewrite.

What's the change?
Essentially, we're going to be starting the user on #Earth, give them the tools and information to go through the basic missions and everything else, and then we'll send them to other planets.

Users will still be able to colonise/visit multiple planets (and rather than having multiple timelines, we can just have a rolling map that shows the progress/changes over time - #terraforming ). 

I think what we'll do is we'll finish the current mission architecture as the majority of the flow (set up your planet [by picking classifications to do] -> go mining/collect resources -> research -> more classifications -> building) will remain in place, this just means we'll need to edit some things like the background, look at how mining works...etc

Once this is implemented, we'll come up with a new sprint that will bridge the gap between the #Onboarding and the #Chapters , relocate the #Chapter-1 to Earth and introduce the loop to get the user onto the new planet for #Chapter-2 . Additionally, we'll work to improve the data flow and ensure that all content (including in test #Database instance) is seeded correctly (rather than not at all, the way it is now).

I think we might also include the #zoodex uploader #Classifications module in #Chapter-1 with this change.
So I'll need to go through everything again (anything with relevant tags or that was edited recently), discuss what can be salvaged and what will be brought forward/pushed back, and then here we go again.

The #Tickets as I see them:
1. New mission plan, including new routes, moving all old routes to an archived `api` directory; all missions with proposed sequencing (including a multi-layer sequencing to ensure no forced ordering for #Classifications )
2. Seed the relevant data for each module

Some questions:
1. How do we track `unlocked_technologies` from a #Database perspective?
2. Any other #Narrative discussions

This first sprint will be for cleanup, onboarding revival & retrospective, and initialising the #Earth scene.


![[background1.jpeg]]