+++
title = 'API Design'
date = 2024-04-05T08:50:13-05:00
draft = true
+++

## Purpose of APIs

- Deliver integration between systems

## Principles of API Design

Effective Web API design requires understanding and applying three important elements:

- Business capabilities: The underlying business capabilities should reflected in the API design.
  - Why: Will deliver the services clients want and need
- Product thinking: The focus of an API product is
on meeting market needs in a scalable and cost-effective way.
    Why: Increases reuse and flexibility
- Developer experience: The developer must find the API easy to use and meet their needs  
  - Why: A great DX is essential to the success of an API and will help develop business value faster

## Another View of Principles

- Principle 1: Collaborative API design
is essential for a good API.
  - Principle 2: API design starts with an outcome-based focus. A focus on the outcome ensures the API delivers value to everyone
  - Principle 3: Select the API design elements that match the need. Trying to find the perfect API style is a fruitless endeavor. Instead, seek to understand and apply the API elements appropriate for the need, whether that is REST, GraphQL or gRPC
  - Principle 4: API documentation is the most important user interface for developers. Therefore, API documentation should be first class and not left as a last-minute task. (Chapter 13)
  - Principle 5: APIs are forever. Thoughtful API design combined with an evolutionary design approach makes APIs resilient to change.

## Goals of API Design

- Deliver outcomes and experiences
- Optimized network access
- Programming language independence.
- Stable over time

## What is API Design About?

- Communicaiton across network boundaries
  - Consider protocol(HTTP, REST, GraphQL, gRPC, MQTT, AMQP), chattiness
- Communication with developers
- Communication with the marketplace

## Applicable Principles of API Design

- Modularization
- Encapsulation
- Loose coupling
- High cohesion

Other best practices:

- Focus on resources
  - Don't confuse resources with data tables or domain objects
- Focus on the design and exchnage of messages
- Consider how the API might change if the client requirements changed
  - eg change to a different consumer (mobile app, chatbot, etc)
  - eg change to a different use case

## Things to Avoid

- APIs that don't align with the underlying business capabilities
- Custom APIs that are intended for a very limited set of clients and use cases
- Not enough feedback from the eventual clients
- Implementation is difficult without the original developers around
- Poor documentation
- API is not divided into cohesive consistent packages
- Inconsistency in organization, naming, granularity, capabilities exposed, protocols, etc
- Implementation details (language, platform, data model) are evident in the API
- Tightly coupled code
- Lack of cohesion

- Using the data model as the basis of the API design
  - Why: Data models may change over time to support better performance. Don't base the APIs on the data model
- Excessive network chattiness caused by very fine grained granularity
- Exposing a domain object as a resource:
  - Why:
-

# Common Protocols

1. REST (Representational State Transfer)
   - Architectural Style: Resource-based design and stateless interactions.
   - HTTP Verbs: Leverages HTTP methods (GET, POST, PUT, DELETE) for CRUD operations.
   - Flexibility: Offers flexibility in data formats (JSON, XML, etc.).

2. SOAP (Simple Object Access Protocol)
   - XML-Based: Employs XML for data - formatting, making it quite structured and strict.
  - WSDL: Uses Web Services Description Language (WSDL) to define the API's structure and operations in detail.
   - Well-Suited For:** Enterprise applications, formal contracts, and scenarios where strict data consistency is paramount.
3. GraphQL:
   - Flexible Queries: Lets clients ask for the precise data they need in a single request, minimizing over-fetching.
   - Schema-Driven: Relies on a schema to define data types and relationships.
    - Well-suited for:  Situations with complex data relationships or when the client needs granular control over fetched data.

4. gRPC:
   - Remote Procedure Calls:** Employs an RPC (Remote Procedure Call) framework.
   - Efficient: Uses Protocol Buffers (binary data format) for compact data encoding, enhancing speed.
   -Well-suited for: Microservices architectures, internal systems with high-performance demands, and real-time communication.

4. WebSockets**

* **Full-Duplex Communication:** Enables persistent, bidirectional communication between client and server.
* **Real-time Updates:** Ideal for building chat systems, dashboards with real-time data, or any application needing instant updates.
* **Well-suited for:** Use cases where immediate updates and low latency are key.

**Other Noteworthy Protocols**

* **WebHooks:** Allow servers to "push" updates to subscribed clients rather than clients needing to poll for changes.
* **SSE (Server-Sent Events):** A one-way communication protocol allowing servers to stream updates to clients.

**Choosing the Right One**

The best API protocol depends heavily on your project's requirements:

* **Need strict rules and well-defined data structures?**  SOAP might be a good fit.
* **Flexibility in queries and minimizing data over fetching a priority?** GraphQL could be your choice.
* **Speed and efficiency a top concern?** gRPC is worth considering.
* **Real-time communication is a must-have?** Look into WebSockets.

Let me know if you'd like a deeper dive into a specific protocol! 
