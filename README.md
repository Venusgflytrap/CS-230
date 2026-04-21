# CS-230 Portfolio: DRAW IT or LOSE IT SOFTWARE DESIGN 

## Project Overview

**The Gaming Room** is the client for this project. They requested to the design and development of a web-based version of their existing Android game, *Draw It or Lose It*. The game is modeled after the 1980s television program *Win, Lose or Draw*, where competing teams attempt to identify progressively revealed stock drawings within timed rounds.

The client's primary goal was to expand their audience beyond Android users by creating a platform agnostic experience accessible from any modern web browser on desktops, tablets, and mobile devices.
### Software Requirements
The core requirements provided by The Gaming Room included:
*   **Multi Team Support:** A single game instance must accommodate one or more competing teams simultaneously.
*   **Multi Player Teams:** Each team must support multiple players, each maintaining a unique identity.
*   **Unique Naming:** Game names and team names must be unique across the entire application.
*   **Single Game Instance:** Only one instance of a game may exist in memory at any given time (enforced programmatically).
*   **Unique Identifiers:** Every game, team, and player must be assigned a unique numeric identifier upon creation.
## Reflection
**What did you do particularly well in developing this documentation?**
I believe I successfully articulated the transition from a single platform mobile application to a distributed web environment. The documentation clearly defines the domain model using Object Oriented principles (Inheritance, Encapsulation, Abstraction) and explicitly details how specific design patterns namely the Singleton pattern for the `GameService` and the Iterator pattern for unique naming directly satisfy the client's constraints.
**What about the process of working through a design document did you find helpful when developing the code?**
Creating the UML class diagram and defining the entity hierarchy (`Entity` base class extended by `Game`, `Team`, and `Player`) before writing code was incredibly helpful. It established a clear contract for how data would be structured and related. By solving the logical problems (like enforcing the single game instance constraint) in the design phase, the actual implementation phase became much more straightforward and focused on syntax rather than architectural problem solving.
**If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?**
I would expand the "System Architecture View" section. Currently, it notes that a full description of the physical tiers and logical topology is planned for a subsequent phase. I would improve the document by including at least a preliminary diagram of the proposed three tier architecture (presentation, logic, and data tiers) and a visual representation of the WebSocket communication layer recommended for real time gameplay.
**How did you interpret the user’s needs and implement them into your software design? Why is it so important to consider the user’s needs when designing?**
The user's primary need was accessibility across different platforms (Windows, macOS, Linux, iOS, Android). I interpreted this by designing a server side Java application that delivers the client interface through standards compliant HTML, CSS, and JavaScript, ensuring platform independence. Considering user needs is paramount because software is ultimately built for people to use; if the architecture doesn't support the environments where the users actually are, the application will fail regardless of how well the backend is coded. Furthermore, understanding the need for a real time, multi user experience drove the recommendation for WebSocket integration.
**How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?**
My approach was top down, starting with the client's business goals, translating those into technical requirements and constraints, and then building a domain model to represent the system logically. In the future, I will continue to utilize UML modeling early in the process. I would also place a stronger initial emphasis on security and concurrency modeling when designing web based, multi user systems, as these are often the most complex challenges to retrofit into an existing architecture. I will also continue evaluating hosting environments (like the recommended Linux based cloud platform) as a core part of the design process, as deployment strategy heavily influences architectural decisions.
