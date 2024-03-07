A list of all tickets, ideas & other good stuff

# Game inspiration
[[Alchemy]]

# Design
[[SSF-2]]
Single scrollable content column again? How do we make this like a game and not a social network? Perhaps this could be useful once we get a significant userbase. Integrate with other networks e.g. mastodon?
# Components
[[ComponentList]]

# Protocols
[[Protocols]]
# Bugs
[[SSB-1]]
1. Post comments
2. Icons
3. Multi-paragraph threads
# Classifications
[[ClassificationComponents]]
Generating cities/objects based on lightkurve data haha? [[Ideas]]
[[StructureNarrative]]
[[DATA-1]]

# Populating
[[DATA-1]]
# Microservices
[[FLASK-1]] -> ideally, can we find a cheaper alternative for hosting?

# Inventory
## Crafting
[[Alchemy]]
[[StructureNarrative]]
## Items
[[Alchemy]]

## Construction
[[Alchemy]]
[[StructureNarrative]]
[[DATA-1]]

# Planning
### Design Principles

1. **Exploration and Discovery**: Focus on user exploration and discovery of new planets and alien life forms.
5. **Variety of Environments**: Introduce a diverse range of star types, planets, and alien life forms.
6. **User Interaction**: Encourage user participation and contributions to the game world.
7. **Flexible Gameplay**: Allow different play styles, including text-based and visual explorations.
8. **Multiplayer Elements**: Develop multiplayer features for user interaction and competition.

### Plans/Ideas

1. **Character Customisation**: Allow users to select their character type, home planet, and play style at the start.
2. **Mission Matching**: Assign starter missions based on user preferences to guide them in collecting resources and advancing.
3. **Visual vs. Text-based Content**: Decide between a simple text/image-based experience or a more complex 3D world.

### Tasks

1. **Design Character Selection Screen**: Create an initial screen for users to select their character and preferences.
2. **Create Starter Missions**: Develop initial missions that match user preferences and guide them in-game.

# Planet data pipelines
### Design Principles:

1. **Initial Planet Selection**: Focus on selecting six initial planets manually for the upcoming alpha version, which allows flexibility in data collection without creating complex pipelines.
2. **Data Representation**: Use calculated values such as planet radius and orbital period to provide insights into planet composition and temperature. Utilize existing databases like Lightkurve and Exofop for accurate data cross-referencing.
3. **Resource Allocation**: Assign resources to planets based on characteristics such as anomaly metallicity, radius, mass, orbital period, and star type.

### Tasks:
5. **Remove Outdated Database Schemas**: Merge or remove outdated schemas in Supabase, including tables for sites, replies, planet status, and other unused data tables.

# Full review
### Design Principles:

1. **Initial Planet Selection**: Select six initial planets manually for the upcoming alpha version to provide flexibility in data collection without creating complex pipelines.
2. **Data Representation**: Use calculated values such as planet radius and orbital period to provide insights into planet composition and temperature. Utilize existing databases like Lightkurve and Exofop for accurate data cross-referencing.

### Plans/Ideas:
4. **User Journey Mapping**: Create a comprehensive map of user journeys to identify key touchpoints and areas for enhancement.
6. **Community Events**: Organize events and challenges to engage the user base and foster a sense of community.
10. **Customization Options**: Provide users with customization options for avatars, ships, and other aspects of their in-game experience.
11. **Educational Resources**: Offer educational materials and resources to help users understand the scientific concepts behind the game.
13. **Augmented Reality Integration**: Explore the potential of integrating AR features for immersive gameplay and data visualization.
15. **Competition and Leaderboards**: Introduce competitive elements and leaderboards to foster healthy competition among users.
16. **Achievement System**: Implement an achievement system to reward users for reaching milestones and completing tasks.
17. **User Engagement Metrics**: Monitor and analyze user engagement metrics to identify opportunities for improvement.
18. **Cross-promotion Opportunities**: Collaborate with other platforms or games for cross-promotion opportunities and shared content.
19. **Seasonal Events**: Plan seasonal or special events to keep the gameplay fresh and engaging for users.

### Tasks:

3. **Implement Data Filtering**: Set up a filtering system that allows users to change the visual interpretation of data.
4. **Design Satellite and Mapping Tools**: Plan and create tools for gathering and mapping data in space.
8. **Optimize Backend Services**: Improve backend services for better performance and scalability.
9. **Develop User Authentication**: Implement secure user authentication and authorization mechanisms.
10. **Integrate Third-Party Tools**: Explore and integrate third-party tools and APIs for enhanced functionality.
11. **Implement Error Handling**: Create robust error handling for user-facing components and backend processes.
12. **Design User Onboarding**: Develop an onboarding process to guide new users through the application effectively.
13. **Optimize Database Queries**: Review and optimize database queries for faster data retrieval.
17. **User Data Management**: Implement systems for managing and securing user data, including profiles and preferences.
19. **Create Documentation**: Provide thorough documentation for developers and end-users to facilitate usage and maintenance.
20. **Continuous Integration and Deployment**: Set up automated CI/CD pipelines for efficient code deployment and testing.

### Citizen Science Components:

1. **User Contribution**: Components for users to submit data and observations, such as forms and interactive interfaces.
2. **Data Validation**: Systems for validating user contributions to ensure data quality and reliability.
3. **Feedback and Recognition**: Provide feedback and rewards to users for their contributions, encouraging continued participation.
4. **Collaboration Tools**: Tools that enable users to collaborate on citizen science projects and share findings.
5. **Data Aggregation**: Mechanisms for aggregating and organizing user-contributed data for analysis and research.
12. **Anomaly Detection**: Use user-contributed data to identify anomalies and potential areas for further research.

### Frontend Components:

1. **Navigation Components**: Create intuitive navigation elements such as navbars, sidebars, and menus.
2. **Forms and Inputs**: Design user-friendly forms and input fields for various interactions.
3. **Data Visualization**: Develop components for displaying data visually, including charts, graphs, and maps.
4. **Notifications and Alerts**: Implement notification and alert systems for user updates and feedback.
5. **User Profiles**: Create components for managing user profiles, settings, and preferences.
6. **Search Functionality**: Develop search components for users to quickly find relevant content and data.
7. **Media Display**: Create components for displaying media such as images, videos, and audio.
8. **Data Tables and Lists**: Design components for organizing and displaying data in tables and lists.
9. **Modal Dialogs and Popups**: Utilize modal dialogs and popups for additional user interactions and information.
10. **Authentication Components**: Implement components for user authentication and account management.
11. **Localization Support**: Design components that support multiple languages and locales.
12. **Real-time Updates**: Develop real-time update components for live data and user interactions.
13. **Forms Validation**: Create form validation systems to ensure user inputs are accurate and complete.
14. **Tooltips and Hints**: Provide tooltips and hints to guide users through the application.
15. **Interactive Maps**: Design interactive map components for data visualization and navigation.
16. **User Feedback Mechanisms**: Create components for collecting and managing user feedback.
17. **Tabs and Accordions**: Implement tabs and accordions to organize content and improve navigation.
18. **Carousel and Slider Components**: Design components for displaying images and content in carousels and sliders.
19. **Chat and Messaging Interfaces**: Create chat and messaging components for user communication.
20. **Dark Mode Support**: Offer dark mode support for improved user experience in different lighting conditions.

# Mars Rover Planning
### Tasks

- **Implement Feedback Mechanisms**: Develop features for users to provide feedback on their experiences and findings.
- **Establish User Roles**: Define and implement different user roles and permissions for access control and specialized functions.
- **Create Resource Management Tools**: Design tools for users to manage resources efficiently in the game world.
- **Integrate Scientific References**: Incorporate scientific references and data sources for accuracy and educational value.

### Citizen Science Components

- **User-Generated Annotations**: Allow users to annotate images and data with observations and comments.
- **Training and Tutorials**: Provide resources to train users in making accurate classifications and observations.
- **Citizen Science Missions**: Design missions specifically for citizen scientists to contribute data and insights.
- **Integration with Research Institutes**: Explore partnerships with research institutions to utilize user-contributed data effectively.

### Gameplay Components

- **Weather and Environmental Effects**: Implement dynamic weather and environmental changes that impact gameplay.
- **Spacecraft Customization**: Allow players to customize and upgrade their spacecraft for improved performance.
- **Mission Briefings and Debriefings**: Create interfaces for providing mission objectives and reviewing mission outcomes.
- **Economy Simulation**: Design an in-game economy with supply and demand dynamics to simulate trade and commerce.

### Frontend Components

- **User Dashboard**: Design a personalized dashboard for users to track their progress and manage their settings.
- **Leaderboard and Achievements UI**: Create a dedicated interface for viewing leaderboards and achievements.
- **Interactive Tutorials**: Implement tutorials with interactive elements to guide new users.
- **Minimap and HUD**: Develop minimap and heads-up display (HUD) components for user navigation and information.
- **Voice Command Interface**: Explore options for implementing a voice command interface for navigation and interaction.

### Plans

- **Integrate Augmented Reality (AR)**: Investigate the potential of AR for enhancing the gameplay experience, particularly for exploration and data visualization.
- **Partnerships with Research Organizations**: Establish partnerships with research organizations to facilitate the use of user-contributed data in scientific studies.
- **User-Centric Development**: Focus on user-centric development practices, emphasizing user feedback and iterative improvements.
- **Social and Competitive Play**: Design features that promote social interactions and competitive gameplay among players.

### Design Principles

- **Modularity and Flexibility**: Ensure modularity and flexibility in design to accommodate future expansions and updates.
- **Player Autonomy**: Design gameplay mechanics that encourage player choice and agency in how they approach tasks and missions.
- **Balanced Complexity**: Balance the complexity of gameplay elements to maintain accessibility while offering depth for engaged players.
- **Historical and Cultural References**: Integrate historical and cultural references into gameplay for added depth and immersion.

### Gameplay

1. **Custom Rover Actions**:
    
    - Task: Create custom rover actions using a central menu.
    - Quote: "I'm thinking that we use the central menu to create buildings and other actions, then for actions that can be done via clicking on a structure/icon (e.g. sending out a rover when you've already got one), we just lay out the structures randomly across the landscape."
2. **Structure Interactions**:
    
    - Task: Design "internal" areas for interacting with structures.
    - Quote: "Could you come up with a design for what the 'internal' areas will look like (i.e. what would it look like if you're interacting with a particular structure)."
3. **Feed Design**:
    
    - Task: Continue with a minimal format for the feed.
    - Quote: "For the feed I think we can just continue with the minimal format for now."
4. **Dynamic Content Updates**:
    
    - Task: Implement systems for real-time updates in the game world.
    - Quote: "Ensure the application is optimized for mobile devices for accessibility and user retention."
5. **Gamification Features**:
    
    - Task: Integrate gamification elements like achievements, rewards, and quests.
    - Quote: "Integrate game-like elements such as achievements, rewards, and quests to increase user motivation."

### Citizen Science

1. **User Data Collection**:
    
    - Task: Create tools for users to submit data and observations.
    - Quote: "Components for users to submit data and observations, such as forms and interactive interfaces."
2. **Data Validation Systems**:
    
    - Task: Implement systems for validating user contributions.
    - Quote: "Systems for validating user contributions to ensure data quality and reliability."
3. **Feedback and Recognition**:
    
    - Task: Provide feedback and rewards for user contributions.
    - Quote: "Provide feedback and rewards to users for their contributions, encouraging continued participation."
4. **Data Sharing with Researchers**:
    
    - Task: Facilitate data sharing between users and researchers.
    - Quote: "Facilitate data sharing between users and researchers to advance scientific knowledge."
5. **Community Forums**:
    
    - Task: Create spaces for users to discuss citizen science projects.
    - Quote: "Create spaces for users to discuss citizen science projects and share insights."

### Dataflow

1. **Lightkurve and Exofop Integration**:
    
    - Task: Utilize Lightkurve and Exofop for data cross-referencing.
    - Quote: "Utilize existing databases like Lightkurve and Exofop for accurate data cross-referencing."
2. **Calculate Planetary Values**:
    
    - Task: Develop methods to calculate planetary values such as radius, mass, and temperature.
    - Quote: "Develop methods to calculate planetary radius, mass, temperature, and other characteristics using available data."
3. **Data Filtering Systems**:
    
    - Task: Implement data filtering systems for data interpretation.
    - Quote: "Set up a filtering system that allows users to change the visual interpretation of data."
4. **Interactive Data Visualization**:
    
    - Task: Implement a filter-based, interactive toggle bar for data interpretation.
    - Quote: "Implement a filter-based, interactive toggle bar for data interpretation, allowing users to customize visual representation."
5. **Mapping and Satellite Tools**:
    
    - Task: Set up satellite and mapping tools for data gathering.
    - Quote: "Set up satellite and mapping tools for data gathering, including telescopes and probe droids for gathering light curve data and exploring anomalies."

### Classifications

1. **Initial Planet Selection**:
    
    - Task: Manually select initial planets for the alpha version.
    - Quote: "Select six initial planets manually for the upcoming alpha version to provide flexibility in data collection without creating complex pipelines."
2. **Resource Allocation**:
    
    - Task: Assign resources to planets based on their characteristics.
    - Quote: "Assign resources to planets based on characteristics such as anomaly metallicity, radius, mass, orbital period, and star type."
3. **Navigational Waypoints**:
    
    - Task: Use globular clusters as navigational waypoints.
    - Quote: "Consider using globular clusters as navigational waypoints to guide players in the universe."
4. **Auto-generated Descriptions**:
    
    - Task: Create auto-generated descriptions and visuals based on data and narrative.
    - Quote: "Generate descriptions and visuals based on planet data and narrative."
5. **User Impact Tracking**:
    
    - Task: Track the impact of user contributions in citizen science projects.
    - Quote: "Allow users to track their contributions and the impact they've made in citizen science projects."


# Overall task list -> split (priority)
Assume that everything not included here will not be included in V2 of Star Sailors. 

 1. Mission matching
 2. Better light curves
 3. Star types -> insert into narrative properly
 4. Planet types & stats -> evaluation & narrative insertion. Different base planet types
 5. Character design screen -> animations/object components
 6. Compare narrative points with December megadoc
 7. Content descriptions (specifically for anomalies). What other data/content needs to be added?
 8. Determine navigation system/methodologies, including waypoints (globular clusters?)
 9. Improve resource allocation formulae
 10. Interface similar to the `/explore` route for deploying structures and interacting with them (static & stationary types)
 11. Asset inheritance -> probe droids, satellites, structures, etc
 12. Better 'galaxy map'
 13. Starter missions
 14. Map existing user flow in V1, current drafts of V2, and plan for what the production fow should be
 15. Determine formula for community events (aka data days)
 16. Leaderboards/faction competitions
### /explore route
- **Weather and Environmental Effects**: Implement dynamic weather and environmental changes that impact gameplay.
- **Spacecraft Customization**: Allow players to customize and upgrade their spacecraft for improved performance.
- **Mission Briefings and Debriefings**: Create interfaces for providing mission objectives and reviewing mission outcomes.
- **Economy Simulation**: Design an in-game economy with supply and demand dynamics to simulate trade and commerce.
### economy
- **Economy Simulation**: Design an in-game economy with supply and demand dynamics to simulate trade and commerce.

### gameplay UI
- **Minimap and HUD**: Develop minimap and heads-up display (HUD) components for user navigation and information.
- **Voice Command Interface**: Explore options for implementing a voice command interface for navigation and interaction.

### Frontend
- **User Dashboard**: Design a personalized dashboard for users to track their progress and manage their settings.

### User flow
**Interactive Tutorials**: Implement tutorials with interactive elements to guide new users.

# V3 ideas
1. Can we integrate with achievements like on Google Play? (this would require development of a native app)