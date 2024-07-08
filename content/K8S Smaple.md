```mermaid
graph LR
    subgraph Authentication [
        API_Gateway [API Gateway]
        Keycloak [Keycloak]
    ]
    subgraph Application_Tier [
        Load_Balancer [Load Balancer]
        Web_Server_1 [Web Server (3x)] --> Load_Balancer
        API_Server_1 [API Server (2x)] --> Load_Balancer
    ]
    subgraph Database [
        Database [Database]
    ]
    Authentication --> Application_Tier
    Application_Tier --> Database
```
