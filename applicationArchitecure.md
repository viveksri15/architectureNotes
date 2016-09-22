# Application Architecture


###### Inspired by https://msdn.microsoft.com/en-us/library/ff650706.aspx
###### Reference: https://aws.amazon.com/architecture/
###### Reference: https://en.wikipedia.org/wiki/Software_design_pattern
###### Reference: https://camel.apache.org/enterprise-integration-patterns.html

## What is an Application Architecture

There are many great definitions out there. Wikipedia says, "Software architecture refers to the fundamental structures of a software system, the discipline of creating such structures, and the documentation of these structures. These structures are needed to reason about the software system. Each structure comprises software elements, relations among them, and properties of both elements and relations, along with rationale for the introduction and configuration of each element. The architecture of a software system is a metaphor, analogous to the architecture of a building."

It is about breaking down the systems into parts, ensuring these parts meet business, technical and operational, while ensuring quality attributes are maintained. A good architecture should consider users, business, developers and people managing the day-to-day operations of the system while being designed, developed, tested, and deployed.

It should be flexible to accomodate changes in future, should be focussed on user experience, and should take advantage of products in the market which can reduce the development and application management overhead. Avoiding over-engineering while trying to predict future trends (thus reducing risks) should be aimed for. Assumtions should be mentioned clearly, and verified as much as possible. A good architecture exposes the structure of the system, and hides the implementation details. It covers all use cases and user stories.

## Who is an architect?

An architect is a person responsible for facilitating and guiding the architecture, design, development, deployment and operations of a system for business or technical requirements. An architect is expected to know key engineering decisions and tradeoffs taken during development of the system, and understanding the user, business and technical goals. He/She is aware of various candidate solutions, and their pros and cons.

## Key design principles of an architect:

(Recommendation: Microservices)

1. Saperation of concern
2. Single responsibility principle
3. Principle of least knowledge
4. DRY principle
5. Minimize upfront design: Avoid Big Design UpFront (BDUF), and do not over-engineer based on assumptions (YAGNI).

A useful guideline for design and coding is the use of consistent development and integration technologies, API contracts, design patterns, and conventions to reduce operations cost and improve the quality of the system. Use of dependency injection for managing cross cutting concerns also helps a lot.

### Quality Attributes

It is important to understand and satisfy *key* quality attributes of a production system. Not all may be applicable from the list mentioned below, and having one may trade off another attribute. It should be clear as to which are the *must have* requirements, and to what degree.

### List of important quality attributes:

- Availability
- Conceptual Integration
- Interoperatability
- Maintainability
- Managebility
- Performance
- Reliability
- Reusablity
- Scalability
- Secuirty
- Supportabilty
- Testability
- Usability
- User Experience
- Extensibility
- Robust Logging
- Monitoring and Alerts
- Metrics

It is equally important to have the following in different components of the system:

- Centralized Logging
- Exception Handling Framework
- Authentication and Authorisation
- Caching
- Communication
- Validation
- Configuration Management

## Achitectural Styles:

1. Client/Server Architecure, P2P Architecture
2. Component based architecture
3. Domain Driven Design
4. Layerd Architecture
5. Message Bus
6. N-Tier Architecture
7. Object Oriented Design
8. Service Oriented Design

These are not mutually exclusive, but one or more of them work together to create a coherent system.

## Techniques

Software Architecture, design and development is an iterative process of steps focusing on discussing and improving candidate solutions with following steps

1. Identify architecture objectives
2. Identify key (business critical, high impact, etc.) scenarios convering all the required functionalities and users of the application.
3. Create application overview with use cases, known constraints, and quality attributes.
4. Identify key issues
5. Define candidate solutions.

Each iteration should focus on getting a clearer picture of the system to be developed in terms of functionality, architecture and design style, expected quality attributes and figuring out relevant technologies by asking more questions each time.

An Architectural Spike is a test implementation of a small part of application which can be used for the purpose of validation and evolution of the design.

### Architecture Review

Review is extremely important to figure out details and mistakes before the cost of such ammendments is too high.

Review methodologies include Software Architecture Analysis Method (SAAM), Architecture Trade Off Analysis Method (ATAM), Active Design Review (ADR), Cost Benefit Analysis Method (CBAM) etc.

### Well known method of describing architecture to others:

- 4+1 method: Uses 5 views to describing the system. Covers logical view (object models etc), process view (concurrency etc), physical view (layers), development view, and Use-Case view.
- UML: Uses 3 views: Functional requirement view, the static structural view(objects, relationships etc), and dynamic behaviour view (interaction among objects etc.).

### Layers and Tiers

**Tier vs Layer**: Tier is the physical component, like servers. Layer describes the logical grouping of functionalities, like Database Layer, Web Layer etc.

A typical web service consists of Presentation Layer, Service Layer, Application Layer, Data Layer. All of these layers may be broken down into modules, or microservices depending on distinct business domains, complexities, resuabulity etc. Also, all these layers have to deal with logging, monitoring, configuration, caching, authentication, discovery and other common concerns. Each of these (cross cutting) concerns may be deployed as centralised piece as a service. For example, in the diagram mentioned [here](http://media.amazonwebservices.com/architecturecenter/AWS_ac_ra_ecommerce_webfrontend_14.pdf), caching and logging can be seen as saperate layers. There is a trade-off between benefits of having multiple layers (reusability, easy deployment, redundancy, loose coupling) and costs associated with them (complexity, network communication cost etc.). The trade-off should be properly considered when going deciding a layering strategy.

Interaction between layers can be strict (which means a layer can interact only with the layer just below it) or loose (which means layers can be bypassed). Strict interaction has an advantage of simplicity and ease of change, but suffers from emtpy APIs, whose only purpose can be enabling communication across layers without adding any benefits. Loose coupling can take care of this problem of empty APIs, but the cost of changes can go high due to wide impact of a change across many layers.
