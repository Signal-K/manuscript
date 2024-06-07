# Mission list
const [missions, setMissions] = useState([

{ name: "Pick your home planet", completed: false },

{ name: "Build your first rover", completed: false },

{ name: "Collect your first resources", completed: false },

{ name: "Build your first structure", completed: false },

{ name: "Make your first classification", completed: false },

]);

Note -> as per SGV2-20, missions 1 & 2 (and maybe others) will technically be completed by the onboarding process...but good to keep them in here for now.

# Onboarding report
Users can currently visit the in-dev version and are invited to navigate to the `/auth` route. This will handle authentication.

Is it worth doing the automation route for providing users with the base entity? I'm guessing we're comfortable with `basePlanets` being the initial narrative point (I mean, the main game flow and inventory structure sort of does assume this, but just thought it would be worth confirming (again))
## 23/4/24
2. For testing, they will all be given id "3" upon signup until further notice