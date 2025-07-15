# Monolithi-MicroServices-Theory
Contains Monolithic and MicroServices Theory, its Advantages and Disadvantages.

### Monolith

- Tightly Coupled.
- All Components are part of single unit (Ex. User Auth, Product Catalogue, Payment, Shopping cart)
- Everything is developed, deployed and scaled as 1 unit
- App must be written with 1 Tech Stack
- Teams needs to be careful to not affect each other’s work
- 1 Single artifact, so you must redeploy the entire application on each update

### Challenges of Monolithic Architecture

- Application is too large and complex
- Parts are more tangled into each other
- you can only scale the entire app, instead of a specific service which results in higher Infrastructure cost.
- Release process takes longes
- On every change the entire application needs to be tested.
- Entire application needs to be built and deployed
- Bug in any module can potentially bring down the entire application.

### MicroService Architecture.

- Loosely Coupled.
- Split application into smaller independent services.
- Split based on Business Functionalities.
- 1 Service for 1 Specific Job.
- Self-contained and independent.
- Each MicroServices must be Developed, deployed and scaled separately.
- Each MicroServices can be in different tech stack like (Java,Python, Node etc)

### Communication b/w MicroServices

- API Calls
    - Each Service has its own API.
    - They can talk to each other, by sending requests to the respective API endpoint.
    - HTTP Request (Synchronous Communication and waits for the response.
- Message Broker (Message Queue)
    - Communication via messages
    - Common distribution patters : Publish/subscribe and Point-to-Point Messaging.
    - Asynchronous Communication.
- Service Mesh
    - Proxy created for each service and communication being established.

### Downsides of MicroServices

- Added complexity just by the fact that a MicroServices application is a distributed system.
- Configure the communication b/w Services.
- More difficult to monitor with multiple instances of each service distributed across servers.

### MonoRepo - Single Repository

- Means using 1 git repository that contains many projects
- A Directory for each service/project.
- Makes the code management and development easier
- Clone and work only with 1 repo
- Changes can be tracked together, tested together and released together.
- Share code and configurations.
- Ideal for Smaller MicroService Applications.
- Challenges
    - Tight coupling of projects.
    - Easier to break this criterion and develop more tightly coupled code.
    - Big source code, means git interactions becomes slow.
    - Additional logic necessary to make sure only service is built and deployed which had code changes.

### PolyRepo - Multiple Repository

- Code is completely isolated.
- Clone and work on them separately.
- Own CICD pipeline for each repository.
- Challenges
    - Cross-cutting changes is more difficult
    - Changes spread across projects must be submitted as separate Merge Requests instead of having a single, atomic MR.
    - Switching between projects tedious
    - Searching, testing and debugging is more difficult.
    - Sharing resources more difficult