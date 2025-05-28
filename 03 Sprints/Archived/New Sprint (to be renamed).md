---
tags:
  - Sprints
  - Sprint-Planning
  - Tickets
  - SSG-88
sticker: lucide//bluetooth
Jira:
  - SSG-88
---
# End goal
*(for end of sprint)*
1. Users can participate in any project (no research required)
2. Stardust that translates across multiple projects. You can unlock new chapters in existing projects (maybe we add a requirement for stardust for more projects...)
3. Upload project
4. #PlanetHunter generator
5. Expand the current project chapter format to #DailyMinorPlanet & #Cloudspotting 
6. Maybe community missions?

# New routes
2. Full upload process for users - but no functionality beyond viewing. Group by project category for now.
	1. List of uploads (yours/others), with ability to rate. Just a post card with file, location, and vote.
3. Allow users to share their cards externally

# New features
1. Stardust - see #SSG-82
	1. Across all projects
	2. Unlock new chapters
	3. Use as a store of progress, no utility for now

# Missions/Projects
1. Continue on from #SSC-45 
2. #Uploads & #zoodex-upload flow, with description/dialogue and mission rewards

# Cleanup/Refactoring
1. Make a note of all comment, post cards/forms...and remove or extract
2. Fix bugs around points, especially for [[Planet Hunters]]
3. Remember this:
```tsx
{classificationType && (

<div className="mt-4 p-4 border border-secondary rounded">

<h3 className="text-lg font-bold">Classification Type</h3>

<p>{classificationType}</p>

{voteCount <= 5 && (

<p className="tex-red-600 font-bold mt-2">

Anomalies require at least 5 votes to be classified & confirmed.

</p>

)}

{classificationType === "planet" && voteCount > 5 && (

<p className="text-green-600 font-bold mt-2">

This anomaly has been voted as a planet

</p>

)}

</div>

)}

{renderClassificationOptions()}
```

and
```tsx
<Button variant="ghost" size="sm" className="flex items-center">

<MessageSquare className="mr-2 h-4 w-4" />

{replyCount} Replies

</Button>
```
4. #PlanetHunter missions 3 & 4 don't scale correctly on mobile
# Customisations
[[Understandings from customisations]]
1. #PlanetHunter w/ #PostCards 
2. Being able to review #PlanetHunter #Generator 
3. Terrariums will just show a biomass trait initially, with a greyed out (non-selectable) view of other bio-anomalies until we can come up with a realistic narrative for the user's character (i.e. what year are we in, how are we keeping things semi-realistic? What actually are terrariums? Do we have a full-realism mode where terrariums are just representations (on Earth) of other location anomalies?)

Generator & "card customisers" will begin to be integrated in this sprint



# Some old stuff from `SSG-85`
![[Pasted image 20241216093636.png]]

Final cleanup:
1. Create a "global" component for project mission status
2. Pick out a minigame
3. Add proper tutorial text that fits in with the goal from `SSG-59`

Check off TickTick, Obsidian (review) and Tana before finalising sprint params