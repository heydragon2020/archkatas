# ADR - Event based Micro-services as target Architecture

## Status

Proposed

## Context

Since the architecture has to be evolutionary and our assumption is that the system has already progressed from modular monolith startup stage to service based and ultimately reached the evolution stage where the architectural primary drivers are performance, scalability, evolvability and deployability. 

There is also assumption that the product already reaches to success and to further grow received major investments, so the cost and simplicity and is not anymore primary drivers. It's rather time when complex product requires complex solution architecture. 

## Decision

To meet the new needs it is decided to rearchitect system to the event based micro-services. Existing services extracted into fine grained micro services where preferred way of communication is event based. 

Additionally each micro-service will run behind load balancer to meet the fine grained load balancing, fault-tolerance as well as scaling needs. 

It maximizes clear separation of concerns, allows services to be loosely coupled and single responsible. Such decision also opens opportunity for development teams to have less dependencies, and own the services end to end. 

In new architecture almost everything becomes an event, many changes in the system triggering events, where interested services can subscribe to event bus and handle appropriate to service responsibilities.

The business logic is not anymore in single place orchestrated, it's rather split into many services and choreography way conducted.

The communication between Smart Fridges and the system is done via bi-directional channel such as gRPC. 

The Inventory and Payment services integrate with 3rd party accounting and inventory procurement systems via synchronous REST channel.

To maximize fault-tolerance the system will be deployed onto multiple cloud regions and the entry point will be managed with regional traffic manager to load balance requests volume based on geographical priority.

All services logs are pulled into centralized logging big data store, where various analytic tools can perform data science activities and monitor overall system health and trends. 

## Consequences

Such a advanced and flexible architecture comes up with costly production system maintenance / SRE, complex monitoring and issue investigation.

Along with that automated end to end testing becomes a quite big challenge. Any bugs and issues investigation requires checking multiple services logs. So centralized logging solution becomes a way to slightly mitigate that aspect.