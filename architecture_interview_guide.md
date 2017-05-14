[Extremely good link](https://github.com/donnemartin/system-design-primer)
Architecture and System Design Interview High Level Points:
	
## Questions:	
*User Stories/Use Cases
*Flow of User
*Flow of Data
*Scale and Expected Scale
*Data Volume
*Testing and testability
*Assumptions
*Read/Write ratio

## Work on candidate solution, identify issues and areas of improvement, trade-offs, repeat
	
## Everything is a trade-off :)
## Everything can be fixed by introducing one more layer :)

## SOA/Microservice Design
*Service Boundries
*Loose coupling, Strong cohesiveness
*Orchestration vs Chorographing
*Saperation of concerns
*Single Responsibility Principle
*CAP theorem
*

## Computational Pieces
*Close to Data
*Event Driven
*Reactive
*Threading model
*Process or Thread Driven
*
## API/Services
## Data Transport
*Sync
*ASync with CallBacks
*Message Driven/PubSub
	*Atmost/Exactly/Atleast once delivery guarentees
*Idempotency
*Background
## Data Storage
*Memory
*FS
*RDBMS
*NoSQL
	*Key-Value
	*Document-Store
	*Graph DB like neo4J and FlockDB
## Data Access
*Direct connection/TCP
*Data Services
*Caching
## Security Layers
*Authentication and Authorization
*API contracts
*Data validations
	*Input
	*Output
## Data Management
*Replication
*Sharding
*Partitioning
	*Federation (or functional partitioning) 
*Consistent Hashing
## Cross Cutting Concerns:
*Logs
*Audit
*Metrics and Events
*Alerts
*Error handling
*
## Scale of Design
## Variations for Scalability (Horizontal/Vertical)
## Quality Attributes:
*Availability and Uptime Guarentees
*Maintainability
*Performance
*Reliability
*Master/Slave
## Load Balancing
*Load balancing strategies
## Numbers/Back of the envelop calculation


Important concepts:
	Push and Pull CDN
	Service Discovery
	Denormalization as a way to improve performance
	Graph DB
	BackPressure in Queue based systems
