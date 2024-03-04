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
2. **Base Building**: Incorporate resource management and base-building elements inspired by games like Hades Star and NMS.
3. **Narrative Engagement**: Create engaging storylines and missions that guide players through the universe.
4. **Resource Management**: Players should manage and gather resources for survival and growth.
5. **Variety of Environments**: Introduce a diverse range of star types, planets, and alien life forms.
6. **User Interaction**: Encourage user participation and contributions to the game world.
7. **Flexible Gameplay**: Allow different play styles, including text-based and visual explorations.
8. **Multiplayer Elements**: Develop multiplayer features for user interaction and competition.

### Plans/Ideas

1. **Character Customisation**: Allow users to select their character type, home planet, and play style at the start.
2. **Mission Matching**: Assign starter missions based on user preferences to guide them in collecting resources and advancing.
3. **Visual vs. Text-based Content**: Decide between a simple text/image-based experience or a more complex 3D world.
4. **Data Representation**: Explore ways to represent data such as light curves in a more engaging way.
5. **Narrative Focus**: Create a narrative centered around discovering aliens and life forms to maintain user interest.
6. **Star Types and Planetary Habitats**: Define different star and planet types and the potential for habitability.
7. **Gameplay Structure**: Develop a structure that starts with exploring a chosen base planet and then expands to more complex interactions.
8. **User Retention**: Aim for high user retention by offering compelling gameplay and frequent content updates.

### Tasks

1. **Design Character Selection Screen**: Create an initial screen for users to select their character and preferences.
2. **Create Starter Missions**: Develop initial missions that match user preferences and guide them in-game.
3. **Decide on Visual Style**: Choose between a simple text/image-based experience or a 3D world for exploration.
4. **Implement Data Representation**: Develop methods for representing scientific data (e.g., light curves) in an engaging way.
5. **Establish Base Planetary Types**: Define different base planet types, including resources and environments.
6. **Develop Narrative Structure**: Craft storylines around exploring alien life and planets.
7. **Introduce Multiplayer Features**: Plan and implement multiplayer elements for user interaction.
8. **Optimize for Mobile**: Ensure the game is optimized for mobile devices for accessibility and user retention.

These principles, plans/ideas, and tasks can guide the development of the project to create an engaging, interactive, and immersive experience for users.

# Planet data pipelines
### Design Principles:

1. **Initial Planet Selection**: Focus on selecting six initial planets manually for the upcoming alpha version, which allows flexibility in data collection without creating complex pipelines.
2. **Data Representation**: Use calculated values such as planet radius and orbital period to provide insights into planet composition and temperature. Utilize existing databases like Lightkurve and Exofop for accurate data cross-referencing.
3. **Resource Allocation**: Assign resources to planets based on characteristics such as anomaly metallicity, radius, mass, orbital period, and star type.
4. **Navigational Waypoints**: Consider using globular clusters as navigational waypoints to guide players in the universe.
5. **Auto-generated Descriptions**: Generate descriptions and visuals based on planet data and the narrative.

### Plans/Ideas:

1. **Interactive Data Visualization**: Implement a filter-based, interactive toggle bar for data interpretation, allowing users to customize visual representation.
2. **Mapping and Satellite Tools**: Set up satellite and mapping tools for data gathering, including telescopes and probe droids for gathering light curve data and exploring anomalies.
3. **Space Rigging Interface**: Develop a routing interface for deploying telescopes and probe droids in a grid/lattice network to gather data and explore anomalies.

### Tasks:

1. **Create Manual Planet Data**: Manually assign planet names, compositions, and resources based on data and assumptions.
2. **Calculate Planetary Values**: Develop methods to calculate planetary radius, mass, temperature, and other characteristics using available data.
3. **Implement Data Filtering**: Set up a filtering system that allows users to change the visual interpretation of data.
4. **Design Satellite and Mapping Tools**: Plan and create tools for gathering and mapping data in space.
5. **Remove Outdated Database Schemas**: Merge or remove outdated schemas in Supabase, including tables for sites, replies, planet status, and other unused data tables.

# Full review
### Design Principles:

1. **Initial Planet Selection**: Select six initial planets manually for the upcoming alpha version to provide flexibility in data collection without creating complex pipelines.
2. **Data Representation**: Use calculated values such as planet radius and orbital period to provide insights into planet composition and temperature. Utilize existing databases like Lightkurve and Exofop for accurate data cross-referencing.
3. **Resource Allocation**: Assign resources to planets based on characteristics such as anomaly metallicity, radius, mass, orbital period, and star type.
4. **Navigational Waypoints**: Use globular clusters as navigational waypoints to guide players in the universe.
5. **Auto-generated Descriptions**: Generate descriptions and visuals based on planet data and narrative.
6. **Modular Design**: Break down user interfaces and features into modular components for easier maintenance and scalability.
7. **Usability and Accessibility**: Implement design choices that enhance the usability and accessibility of the application for all users.
8. **Performance Optimization**: Focus on optimizing both frontend and backend components for a smooth and efficient user experience.
9. **Feedback Incorporation**: Continuously gather and integrate user feedback to improve the overall design and functionality.
10. **Consistency**: Maintain a consistent design language throughout the application to enhance the user experience.
11. **Progressive Disclosure**: Gradually reveal information to avoid overwhelming users and guide them through the application effectively.
12. **Responsive Design**: Design interfaces that adapt seamlessly across different devices and screen sizes.
13. **Data Security**: Prioritize data protection and user privacy in all aspects of design and functionality.
14. **Gamification**: Integrate elements of gamification to enhance user engagement and motivation.
15. **Adaptive Design**: Allow the application to adjust and respond to different user contexts and needs.
16. **Visual Hierarchy**: Utilize visual hierarchy to guide user focus and create intuitive navigation paths.
17. **Error Handling**: Design error handling mechanisms that are user-friendly and provide clear guidance on how to proceed.
18. **Internationalization**: Support multiple languages and cultures to make the application accessible to a broader audience.
19. **Collaborative Tools**: Facilitate user collaboration and community building through shared spaces and features.
20. **Continuous Improvement**: Strive for ongoing enhancements and updates based on data analysis and user insights.

### Plans/Ideas:

1. **Interactive Data Visualization**: Implement a filter-based, interactive toggle bar for data interpretation, allowing users to customize visual representation.
2. **Mapping and Satellite Tools**: Set up satellite and mapping tools for data gathering, including telescopes and probe droids for gathering light curve data and exploring anomalies.
3. **Space Rigging Interface**: Develop a routing interface for deploying telescopes and probe droids in a grid/lattice network to gather data and explore anomalies.
4. **User Journey Mapping**: Create a comprehensive map of user journeys to identify key touchpoints and areas for enhancement.
5. **Dynamic Content Generation**: Explore the use of AI and algorithms to dynamically generate content based on user interactions and data.
6. **Community Events**: Organize events and challenges to engage the user base and foster a sense of community.
7. **Cross-platform Accessibility**: Ensure the application is accessible across various platforms, including desktop, mobile, and web.
8. **Data Visualization Tools**: Create advanced tools for visualizing and interpreting data in an engaging and insightful manner.
9. **Gamification Features**: Integrate game-like elements such as achievements, rewards, and quests to increase user motivation.
10. **Customization Options**: Provide users with customization options for avatars, ships, and other aspects of their in-game experience.
11. **Educational Resources**: Offer educational materials and resources to help users understand the scientific concepts behind the game.
12. **Ecosystem Collaboration**: Develop partnerships with other organizations or games to enhance the user experience and content variety.
13. **Augmented Reality Integration**: Explore the potential of integrating AR features for immersive gameplay and data visualization.
14. **Storytelling Elements**: Infuse the game with compelling narratives and stories to enhance user engagement.
15. **Competition and Leaderboards**: Introduce competitive elements and leaderboards to foster healthy competition among users.
16. **Achievement System**: Implement an achievement system to reward users for reaching milestones and completing tasks.
17. **User Engagement Metrics**: Monitor and analyze user engagement metrics to identify opportunities for improvement.
18. **Cross-promotion Opportunities**: Collaborate with other platforms or games for cross-promotion opportunities and shared content.
19. **Seasonal Events**: Plan seasonal or special events to keep the gameplay fresh and engaging for users.
20. **Feedback-Driven Development**: Continuously iterate on the application based on user feedback and usage data.

### Tasks:

1. **Create Manual Planet Data**: Manually assign planet names, compositions, and resources based on data and assumptions.
2. **Calculate Planetary Values**: Develop methods to calculate planetary radius, mass, temperature, and other characteristics using available data.
3. **Implement Data Filtering**: Set up a filtering system that allows users to change the visual interpretation of data.
4. **Design Satellite and Mapping Tools**: Plan and create tools for gathering and mapping data in space.
5. **Remove Outdated Database Schemas**: Merge or remove outdated schemas in Supabase, including tables for sites, replies, planet status, and other unused data tables.
6. **Set Up API Routes**: Establish and document necessary API routes for handling data collection, retrieval, and user interactions.
7. **Create Frontend Components**: Design and implement React components for various parts of the user interface.
8. **Optimize Backend Services**: Improve backend services for better performance and scalability.
9. **Develop User Authentication**: Implement secure user authentication and authorization mechanisms.
10. **Integrate Third-Party Tools**: Explore and integrate third-party tools and APIs for enhanced functionality.
11. **Implement Error Handling**: Create robust error handling for user-facing components and backend processes.
12. **Design User Onboarding**: Develop an onboarding process to guide new users through the application effectively.
13. **Optimize Database Queries**: Review and optimize database queries for faster data retrieval.
14. **User Interface Improvements**: Continuously enhance the user interface for better usability and aesthetics.
15. **Bug Fixing**: Regularly identify and fix bugs in both frontend and backend components.
16. **Implement Gamification**: Design and integrate gamification features like achievements, rewards, and challenges.
17. **User Data Management**: Implement systems for managing and securing user data, including profiles and preferences.
18. **Cross-Platform Testing**: Test the application across different platforms to ensure consistency and performance.
19. **Create Documentation**: Provide thorough documentation for developers and end-users to facilitate usage and maintenance.
20. **Continuous Integration and Deployment**: Set up automated CI/CD pipelines for efficient code deployment and testing.

### Citizen Science Components:

1. **User Contribution**: Components for users to submit data and observations, such as forms and interactive interfaces.
2. **Data Validation**: Systems for validating user contributions to ensure data quality and reliability.
3. **Feedback and Recognition**: Provide feedback and rewards to users for their contributions, encouraging continued participation.
4. **Collaboration Tools**: Tools that enable users to collaborate on citizen science projects and share findings.
5. **Data Aggregation**: Mechanisms for aggregating and organizing user-contributed data for analysis and research.
6. **Interactive Visualizations**: Display user-contributed data using interactive visualizations for better understanding and engagement.
7. **Real-Time Data Updates**: Systems for updating and displaying user-contributed data in real-time.
8. **Educational Resources**: Provide resources and guides to help users understand the science behind their contributions.
9. **Community Forums**: Create spaces for users to discuss citizen science projects and share insights.
10. **Project Discovery**: Tools for users to discover and participate in new citizen science projects based on their interests.
11. **User Impact Tracking**: Allow users to track their contributions and the impact they've made in citizen science projects.
12. **Anomaly Detection**: Use user-contributed data to identify anomalies and potential areas for further research.
13. **Data Sharing**: Facilitate data sharing between users and researchers to advance scientific knowledge.
14. **User Mentorship**: Provide mentorship opportunities for experienced users to guide and support new contributors.
15. **Open Data Access**: Make aggregated data accessible to the wider community for research and analysis.
16. **Reward System**: Establish a system of rewards or recognition for significant user contributions.
17. **User Analytics**: Analyze user contribution patterns to tailor citizen science projects and engagement strategies.
18. **Cross-Project Integration**: Explore opportunities for integrating user data across multiple projects and platforms.
19. **Mobile Compatibility**: Ensure citizen science components are accessible and usable on mobile devices.
20. **Privacy and Ethics**: Prioritize user privacy and ethical data use in all aspects of citizen science projects.

### Gameplay Components:

1. **Structures and Environment**: Design and manage in-game structures, environments, and world-building.
2. **Player Movement**: Implement frontend and backend handling of player navigation and movement in the game world.
3. **Inventory and Items**: Create components for managing player inventory, items, and their interactions.
4. **Skills and Abilities**: Develop systems for player skill progression, abilities, and skill trees.
5. **Collaboration and Interaction**: Facilitate player collaboration and interaction with other players.
6. **Pets and Companions**: Design components for managing in-game pets and companions.
7. **Quests and Challenges**: Develop quests and challenges to guide players and provide goals.
8. **Combat Mechanics**: Implement and fine-tune combat mechanics and player interactions.
9. **Crafting and Upgrades**: Create systems for crafting items and upgrading player abilities and equipment.
10. **Achievement System**: Establish an achievement system to reward players for reaching milestones.
11. **Leaderboards and Rankings**: Introduce leaderboards and rankings to foster competition and engagement.
12. **Seasonal and Special Events**: Plan and implement events to keep the gameplay fresh and engaging.
13. **Real-Time Multiplayer**: Explore real-time multiplayer options for player interaction and collaboration.
14. **Dynamic Environments**: Create dynamic environments that evolve based on player actions and in-game events.
15. **Economy and Trading**: Design in-game economy and trading systems for player commerce.
16. **Customizable Avatars**: Allow players to customize their avatars and other aspects of their identity.
17. **Player Progression**: Develop a clear progression path for players, including levels, experience points, and rewards.
18. **Story-driven Gameplay**: Incorporate narratives and stories to enhance player immersion and engagement.
19. **Data-driven Balance**: Use data analytics to balance gameplay mechanics and ensure fairness.
20. **Community Features**: Create community features such as forums and groups to enhance player interaction.

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


# Overall task list -> split (priority)
Assume that everything not included here will not be included in V2 of Star Sailors. 

 1. Mission matching
 2. Better light curves
 3. Star types -> insert into narrative properly
 4. Character design screen -> animations/object components
 5. 