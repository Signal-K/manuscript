---
connie-publish: false
tags:
  - Editing
sticker: emoji//1f468-200d-1f3a4
---

(in no specific order)

~~1. Improve classification process~~
	1. [[#^040856]]
~~2. Add the pokedex module~~
	1. Add content to a local database
	2. AI can help with other classifications too - see [[PostCards (CPW-2)]]
	3. Serves as a starting "engine" or backbone for the "collection"/portfolio concept
	4. Can build an api here - make standalone, add content, etc
~~3. Improve responsiveness & improve UI, implement feedback ^43038b~~
	1. Next-pwa does not need to be implemented yet as I already have it, so that's the main thing!
4. Reduce load on server with electric
	1. Don't necessarily need to get it all working, priority is features and UI. 
	2. The priority matrix for these backend tickets relates a lot to the number of users and the subsequent load on the server
~~5. More data -> fun sandbox mechanics~~
6. Give users more to do after the tutorial - implement an open-ended mechanic/loop
	1. Also explain certain mechanics/improve context better for [[#^43038b]], e.g. mining information
	2. Maybe it would be a good time to implement the post card (`FCDB-2`?) ticket/feature request again...

**8 July 2024**
Ask user what they want to do, we then build everything for them? Or just open up a build window/page?


**7 July 2024**
1. Playthrough, design review, push
2. Version naming nomenclature discussion in design review
3. Finish classification components for other modals
4. Post card implementation, feed, bottom menu

**6 July 2024**
*Star Sailors*:
Commit notes:
~~sytizen: GP-48, #47, #46, GP-34, CPW-29~~
~~client: GP-48, #118, SGV2-107, SGV2-113, CPW-29, SGV2-114, CPW-29~~

* Make a start on postcard design
* Design (and make a start?) on camera module (#zoodex)

**5 July 2024**
*Star Sailors*:
~~1. Have a playthrough :)~~
~~2. Put the openai credits on my invoice (maybe mark them as test eth or something)~~
3. Implement classification changes (db & frontend-side)
4. New  structure modal UI buttons -> for all current modules
5. Tutorial text for all buttons
6. Plan out design & dev infrastructure for the zoodex module in the current/immediate format

**4 July 2024**
*Star Sailors*:
~~1. How do we use the surveyor [[Structures]] in the immediate future?~~
2. Maybe produce some non-citizen science structures for them to build?
3. Revisit the Automaton Upgrade structure so that users can add things to their rovers...maybe even a little 3d scene (or start planning one out?)
~~4. Fix responsiveness issues~~

**3 July 2024**
*Star Sailors*:
2. Finish pokedex module
	1. Plan out AI narrative
3. Finish plan for "fun sandbox mechanics" (for the overall release, and for this week's pre-release)
4. Finish data pipeline - including re-routing other users' classified data to new users 
	1. Just need to figure out how we provide the user with enough data...shall we say 10 clouds per user? So let's put 30 in overall...because they can be shared. We can order them by anomaly using the current jupyter notebook, and figure out long-term plan after that

**2 July 2024**
*Star Sailors*:
~~1. Identify responsiveness issues~~
~~2. Start pokedex module~~
3. Classification process -> provide full documentation & plan/examples for all citizen science modules
4. Plan out new module for this week, if it's the pokedex, how do we integrate it into the workflow
	1. I think we will do the Pokedex, because it's relatively straightforward, has multiple usecases (see [[PostCards (CPW-2)]]) and I can probably sneak $50 USD worth of openai credits into my next invoice for Copernic
	2. We might need to accept location data - maybe just a manual seeding inside `classifications.configuration`?
~~5. Figure out update to existing missions and any new missions~~
	1. Improve on [[Missions - List|Missions - List]] OOO planning
6. Initialise electric project
~~7. Fix complaints/feedback (mainly from "negative" Dave)~~
~~8. Start thinking about "fun sandbox mechanics"~~
9. Make an actionable start on [[PostCards (CPW-2)]] and document

**1 July 2024**
*Star Sailors*:
~~1. Sprint planning~~
~~2. Plan out post card component~~
~~3. Draw structure modal~~
4. Plan list of components

*Copernic*:
1. Standup
2. Plan ghost content

**30th June 2024**
*Star Sailors*:
~~1. Put all textual components in for tutorial~~

**28th June 2024**
*Nordkurve*:
1. Find a new template for blogs, or have a go at this: https://github.com/CriticalMoments/CMSaasStarter
~~2. Insert iframes~~
~~3. UI improvements~~
4. Content from old site
5. Update shop to use sepa
~~6. Hide content based on subscription status~~

*Star Sailors*:
1. Come up with method of assigning users already classified content for redundancy & verifiability
2. Come up with engine/algo for calculating user "seniority"
3. Plan for integrating apis into saving state/populating the pygame/3js sandbox game
4. Come up with narrative & user flow for structures, classifications (beyond mission 21/onboarding) & the information/plan for current sprints, s2 plan, bring a new user in
~~5. Review of current sprint~~
6. Add github issues to Jira again [e.g.](https://github.com/Signal-K/sytizen/issues/46) 

**27th June 2024**
*Nordkurve*:
~~1. Update profiles table with old data, import users (look up how to import user data in relation to `public.profiles` schema and `auth` schema)~~
~~2. Insert everything back into it~~
~~3. Create a pointer for user data to user (maybe an "input your memberid" input, that cross references user's initial data with the data in `userdatas` table, and then go from there)~~
~~4. Content from old site (waiting on Wuppi)~~
5. Find a new template for blogs, or have a go at this: https://github.com/CriticalMoments/CMSaasStarter

*Copernic*:
~~1. Landing page design~~
2. Marketplace contract & template from 2024
3. Database migration
~~4. Figure out what was achieved today (yesterday/26th), if it moved anything forward~~
~~5. Meeting with accountants~~
~~6. Go through anti-silo notes and action items~~
~~7. Initialise thirdweb setup & get some matic for testnet~~

*Star Sailors*:
1. Improved order of operations for the automaton upgrade interface
2. Get all tutorial information to the user (and hopefully make a good start in the new layout)
~~3. Spacecraft~~ & launchpad blocks
4. Inventory block
5. [SGV2-63]
6. Change tic id values (backup as another value in configuration). Update `anomalies` schema once and for all. Try to convert to flask application. Either way, add surveyor & cloud module/data. Determine pipeline to infinite content (across all modules) and implement. Plan out (for next week) pathway towards sector creation & population. Include things like tree/life & stellar metallicity in plan. Document strongly and link in with jira tickets
~~7. Attempt to fix layout - let's have a chat with Rhys~~
~~8. Meeting with Rhys - early morning~~


**26th June 2024**
*Nordkurve*:
~~1. Content from old site~~ - Waiting on Wuppi
~~2. Roll-your-own with stripe (have a go at the template again) -> get users signing up and then migrate them, if we have a hard deadline?~~
	1. ~~If this doesn't work, new supabase with user management and then migrate controls over~~
3. Go over the spreadsheet again
4. Find a new template for blogs, or have a go at this: https://github.com/CriticalMoments/CMSaasStarter

*Copernic*:
1. Transactions between users
2. Mimic buy action
3. Initialise marketplace contracts or a template from 2024
4. Database changes & update creation process
4. Wallet "generation" & auth

*Star Sailors*:
~~1. Feedback, maybe some meetings~~
2. Come up with a better order of operations for the automaton upgrade interface
~~3. Write some text for each mission/stage [[Voidpet onbording experience]], restructure the missions so maybe there's multiple actions~~
~~4. Create v0.dev designs for the missions,~~ modals, buttons, first draw the designs in the notebook. 
5. Finish spaceship & launchpad blocks, update modals to include rate limiter/discriminator when attempting to engage transport
~~6. Get working API for the lightkurve generator~~
7. Inventory block
8. [SGV2-63]: We will be updating the missions, so we'll be able to navigate through everything then
~~9. Finish ticktick misc. #Star-Sailors tasks~~
~~9. Explore custom game engine (in web runtime), or interacting with a 3js scene (or alternative) outside of it~~


**25th June 2024**
*Copernic*:
1. Transactions between users
2. ~~Update db, fix migrations, and add the credits for transactions~~
3. Database changes & update creation process
4. Wallet "generation" & auth

*Star Sailors*
1. Feedback
2. Finish spaceship & launchpad blocks, update modals to include rate limiter/discriminator when attempting to engage transport
3. Continue API work
4. ~~Go through onboarding for Voidpet again~~, relate the tutorial to our components and to the overlays/layouts. [SGV2-91]
~~5. Review [SGV2-63]~~ 
6. Inventory block

**24th June 2024**
*Copernic*:
~~1. Frontend that allows users to authenticate and then choose buyer or seller interface~~
2. Users have a base amount of credits (just an int value)
3. Set up transactions between users
4. ~~Ensure that posting new payloads still works~~, update view interface (dynamic routes)
5. Determine every type of transaction that will occur (cross-reference with Nico's list)
~~6. Pull changes and try again for dapp~~

*Nordkurve*
1. Have a go at removing kinde auth and just rolling it with Supabase
2. Either way, determine how we get the csv into kinde/supabase (depending on auth change success rate. If failed, maybe we fix the csv file)

*Star Sailors*
1. (Hopefully) get some more feedback
2. ~~Submit nws5 update~~
3. Inventory block
4. Some API work -> get an instance working without the dockerised stuff (as in some population)

**16th June 2024**
*Star Sailors*:
1. Plan out sprint & start UI
2. Plan out flask experimentation for population api - only for sectors at the moment
3. Plan out one component/mission */* day
4. Plan out sprint goals for GP & CPW
5. Write to Rob Gell

*Nordkurve*:
1. Handle user data import

*Copernic*:
1. Identify clear sprint goals & UI requirements for demo

*Personal*:
1. Some more learning
~~2. Keep pitching~~

**15th June 2024**
*Star Sailors*:
1. Start planning out next sprint with tickets...sort of already done

**15th June 2024**
*Star Sailors*:
1. Migrate any open notes from Obsidian to new tickets & sprint pages

**14th June 2024**:
*Star Sailors*:
~~1. Finish surveyor module~~
~~2. Insert all missionData[[]]~~
3. Cleanup
~~4. Fix foreign key mission
5. Mission completion component
6. Go through notes, finalise info in Obsidian
7. Build camera receiver structure
5. Make a rover classification
6. Build surveyor module
7. Fix automaton coal issue - random~~
8. Report

Reward:
1. Create a new wishlist, get gpt advice, include info about funding increases

**13th June 2024**:
*Star Sailors*:
~~2. Build Automaton upgrade station~~
~~3. Build camera module~~


Rewards:
1. Get advice from gpt about what to build, do with new world, YouTubers to follow (route to Friday)

**11th June 2024:**
*Copernic*
1. Identify potential places to stay (Berlin)
2. Finalise design principles for v1 of Copernic
3. Identify all areas & components where we are behind
4. Complete off-chain component
5. Vercel e-commerce configuration setup

*Contract*
1. Initialise blog & integrate into main page area
2. Onboarding pathway for users
3. Restrict access with stripe
4. Update schema with old users

*Star Sailors*
1. ~~The goals in Tick Tick~~

*Personal*
* Get some washing done


Manuscript finder dirs:
![[Pasted image 20240611090955.png]]
![[Pasted image 20240611091008.png]]

9th June 2024:



*Nordkurve*
~~1. Start blog post layout~~
~~2. Restrict access to blog with stripe~~
~~4. Upload old/existing users (2) and update schema~~
~~5. Create onboarding pathway for users~~

*Star Sailors*
1. Go/Ruby/Rust investigation
	1. Could we make some standalone minigames?
	2. Maybe a standalone generator/explorer of your anomalies.
	3. Standalone frontend app to explore news & publications
2. Bit of daydreaming (react-integration ui) about Unity components again
3. ~~Update global state~~
4. Starter flask app - nothing else (however, identify the tick tick ✅ notes and make a record of them)
		**Add a flask app into the starsailors folder for sytizen repo; will handle classification calculations & data filling**
		I've updated it so that we now use the `Galaxy` dir docker for the flask app
1. Design layout for mission group 2 order, just a draft for now, and then plan out the component-by-component schema & structure

*Personal*
1. If the stains in turtleneck don't wash out, buy a new one