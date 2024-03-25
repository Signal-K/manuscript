# Planets
1. I think that all structures on a planet's sectors will be accessible from the planet page, eventually. For now, this is going to cause all sorts of issues, so let's hold off on this for now.
2. How does tree data affect what's going on here?2
## Sectors
* Generated bg images/maps for each sector route
* Generate complete make-up/composition when creating a new sector, including confirming that the rover images change each time

## Data
* Need to get planet data to filter into sector data - currently it's all disorganised see ![[Pasted image 20240415133401.png]]

# Explore

# Index
* I think we'll show the user's spaceships, automations, and planet charicatures on the index route. At the bottom we'll have the navigation area, which will allow for the accordions to be selected
* .limit(3); // Set this to be owned planets -> for planet gallery card/garden
* It appears now that the sectors can be visited from the dashboard (i.e. the deeplinks work!)
* Perhaps we could show a grouping of public sectors underneath the accordion area?\
		* I'm having a go at experimenting with what could go below the accordions, currently we've got the sectors & inventory working. Defeats the purpose of the accordions, but while they've been a good stopgap at helping me/us figure out what needs to be shown, I think (thanks to [@Rhys Campbell](https://signalkineticsgroup.slack.com/team/U05MVAXPMCL)) that we've possibly found a better way.  
* Could the bg image be made up of a representation of your colony? "Our space colony".mp3
* ![[Pasted image 20240416171347.png]]

* The onboarding area/index page could house a bento box until we get the user comfortable with the VP-minimal UI
* Bento box -> your planet, your vehicle, citizen module, mission list, inventory
* Possibly we could have an option to toggle the bentogrid component, or highlight the missions. Determining if this is a feasible compromise and when/how to execute/introduce this will be a decision for Rhys
* Another big error -> too many components on the page causes the scroll to go past background/cover image.

# Collecting resources
* Same structure as with the old crypto game from 2022 -> just send a rover there and have it eat up supplies? Create a function that will determine how long the rover has been "mining", then click "end", microservice calculates rewards
* I was thinking that we could possibly have a very stripped back control panel for mobile, maybe even only one function, but then I remembered that it will be a mobile-first (or in theory, anyway, at minimum it will need feature parity between desktop and mobile) deliverable and thus we can't lock features out of the mobile inference.