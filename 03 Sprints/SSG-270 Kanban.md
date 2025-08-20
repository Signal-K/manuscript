---

kanban-plugin: basic

---

## Icebox

- [ ] Tag anomaly notifications with automaton type for dynamic messages #Notifications #UX #Entities
- [ ] Visual layout for deployed entity showing slots/anomalies (based on sketch) #UX #DMP #Automaton
- [ ] Link automaton components to Supabase `linked_anomalies` data #Deployments #Supabase #Automaton
- [ ] Build dynamic automaton display component for deployments (e.g. satellite, telescope) #Automaton #UI #Deploy
- [ ] Reward system proposal #GameDesign #Progression
- [ ] Ownership system outline/prep #Ownership #Infrastructure
- [ ] Automaton unlock logic: block access vs interaction-based unlock #Automaton #Design
- [ ] Rarer anomaly types: outline unlock behavior and visibility #Anomalies #ContentDesign
- [ ] Refactor automaton handler to support future types #Automaton #Modularity
- [ ] Schedule-based unlock logic for other automaton types (rovers, balloons, etc) #linked_anomalies #Design
- [ ] Add automaton-specific animations/post-deploy popups #Automaton #Deploy #Dialogue
- [ ] Extend user panel to show accolades, rotation, profile info etc. #UI #UserProfile #DMP


## In Progress

- [ ] Update Go job to check for and write to `push_anomaly_log` #Notifications #Backend #Logging
- [ ] Github action to run welcome notif in staging instance
- [ ] Staging action to run if undeployed structure for notif
- [x] Look into updating the satellite viewport background to look more like an earth-orbit landscape (rather than deep space) #Viewport #Satellite #COlours
- [ ] Telescope viewport block/section on index route - just shows scanning<br><br>https://github.com/Signal-K/client/commit/b27124d8ec28f956621dd9da3a0f51eb2aab5bb6


## In Review

- [ ] Improve `ActivityHeader` layout with automaton summary tiles #ActivityHeader #Automaton #UX
- [ ] Confirmed entity types used in `linked_anomalies` and user flow for anomaly unlocks #linked_anomalies #Telescope #Satellite


## Done

**Complete**
- [x] Add `push_anomaly_log` table to track sent push notifications #linked_anomalies #Notifications #Database
- [x] Add VAPID key handling in secure `.env` and backend task env vars #Notifications #Security #Config
- [x] Create `/api/save-subscription` endpoint to persist push subscription in Supabase #Notifications #API #Frontend
- [x] Save subscription data to new `push_subscriptions` table in Supabase #Notifications #Database #Supabase
- [x] Scoped out notifications flow based on VAPID and service workers #Notifications #Planning #PWA
- [x] Create `push_subscriptions` table in Supabase #Notifications #Supabase #Database JIRA:SSM-251 #SSM-251
- [x] Send a notification when `linked_anomalies` deploy (telescope) #Notifications #Vapid #linked_anomalies #Deploy JIRA:SSM-252 #SSM-252 #SSM-251
- [x] Write sprint plan and task breakdown for push + automaton UI #Planning #SprintNotes
- [x] Repair local supabase configuration #Supabase #Database
- [x] Created backend fetch SQL for unlocked/unnotified anomalies #linked_anomalies #Notifications #Backend
- [x] Implement Go function to fetch unlocked `linked_anomalies` and send push notifications #linked_anomalies #Notifications #Backend
- [x] Set up GitHub Action to run push service every 15 mins #Notifications #GitHubActions #DevOps
- [x] Register PWA service worker and request push permission from user #Notifications #PWA #Frontend




%% kanban:settings
```
{"kanban-plugin":"basic"}
```
%%