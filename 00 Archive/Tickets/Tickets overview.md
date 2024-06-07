# Current boards
Talking about overlap between tickets and boards (e.g. the currency system consists of things from backend, frontend and narrative) reminds me we probably need to overhaul the labels and confluence labels at some point very soon...
## Generating Planets & Content (GP-)
1. Containerise next & flask in Docker (GP-19)
		If we end up requiring Flask for V2.0 (and this is still not confirmed yet), we will need to containerise it all, so this ticket should be reviewed. Ideally we also do Supabase right from the start
		Currently experiencing issues with getting Flask routes to be accessible when we run it through a docker container so we will need to review that
		This should probably be moved into a new board
2. Basic currency system setup (GP-7)
		Should probably be moved into a content or narrative board
		I don't think we require a currency system (beyond a # of classifications) for V2.0 to fit the criteria I laid out (I do want the rest of the team to review the criteria however)
3. New globe component (GP-16)
		I think it's in the correct board for now
		I do need to chat with Rhys about how we work this. Potentially it's the same format as the ringed layout? Maybe something to build in later
4. GP-14 & GP-15 can be archived.
5. 