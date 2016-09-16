# Micro Services

###### This is a work in progress

These are services designed to approach the problem of breaking the monolith into manageable, autonomous units. They are small enough to carry out only one or few related tasks, but not too small to not make sense and be unmanageable in a distributed environment. They typically promote the Single Responsibility Principle.

Use of microservices promotes continuous delivery, use of newer technologies and technical heterogeneity, easier refactoring, loose coupling and tight cohesion, reuse of functionality etc..

Typical communication between the services is through via the network call (ideally, technology agnostic API calls, which may be sync or async) to force separation. The important keyword here is **Service boundry**. The services are self sufficient, with strict boundaries or layers, and data shared between then through well defined models.

The development of a service should be focussed on enabling changes to be incorporated easily, rather than creating a perfect system. The purpose of a system is not only to serve users, but also to be simple enough for developers and maintainers to make sure system can easily accommodate more business requirements, is extensible, manageable, testable, resilient etc..

It is important for an architect to have strategic goals, have and follow architectural principles, and design and delivery practices.

Few standard requirements of a microservice deployment are monitoring, metrics accumulation, alerts, redundancy, load balancing, error handling, resilient and idempotent message broker if required, etc..

During development of a new system in a new business/technical domain, it is recommended to start with a monolith, and break it down into micro-services when a new bounded context is sensible. A bounded context is a module which exposes only required APIs to satisfy a set of related functionalities, and communicates using well defined models. It is as important to avoid premature decomposition as it is to avoid a monolith for a large domain. A sample bounded context is a Data Service Layer, which can fetch data from memory, database, or network API call. How it fetches the data is encapsulated with the user of the APIs it exposes.

**Orchestration** Vs. **Choreography**: Orchestration means a central module/class governs the service flow, whereas choreographed system delegates the tasks to individual modules/services.
Reactive Extensions (Rx) are a great way to improve service performance.
