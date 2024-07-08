+++
title = 'GraphQL'
date = 2024-04-05T08:50:13-05:00
draft = true
+++

When choosing Between REST and GraphQL it is importnt to conisder what problems have to be resolved in production settings.

When to Use GraphQL

- When the client must control the type and amount of data wanted from the server
- When data is collected and aggregated from multiple sources, a single client API call is required to fetch all the necessary data
- It helps in situations where badwidth is a concern. a GraphQL client can limit how much data is returned to it
- GraphQL is often useful for rapid prototyping
- 


Some Facts about GraphqL

- Unlike REST, GraphQL uses a single endpoint for all operations
- For simple scenarios you can call GraphQL endpoint via REST, but in more complex cases, you will require a GraPhQL client. There are several clients to consider including:
  - Apollo clinet
  - graphql-request
  - urql
  - Realy
  - graphql-hooks
- 


Advantages of GraphQL:



Issues:

- Performance issues
- Adds complexity
- Error handling becomes harder
- Integration into monitoring tools is mroe difficult since all queries return 200 ok status
- Some missing capabilities such as file uploads
- GraphQL has only one end point, making it mroe difficult to cache queries
- Some security challenges asociated with GraphQL include:
  - Attackers can dynamically query the schema and receive detailed information, including its types and activities. Thsi can expose  private data related to the underlying data model.
  - Rate limiting: When there is no efficient rate limitation, attackers can send numerous API requests to overwhelm the server and cause API spam and service depletion or unavailability.
  - Very deep or nested queries can result in denial of service attacks
-  
-


Some Features to Look for:

- Typescript Support
- Authentication support
- Support for multiple libraries (rect, angular, Svelte, etc)
- Support for multiple platforms
- Caching
- Query batching
- Query dedplication
- Pagination
- Local state management (ie redux)