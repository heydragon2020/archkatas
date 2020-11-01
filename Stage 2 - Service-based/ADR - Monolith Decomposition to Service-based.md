# ADR - Monolith Decomposition to Service-based

## Status

Accepted

## Context

The layered monolith architecture has limits in terms of scaling and also doesn't allow for more fine-grained deployability because we would always need to deploy the whole monolith even if only a small change in some component was done.

## Decision

The decision was to decompose the monolith architecture into service-based architecture with business layer split into several coarse-grained independent services. In order to keep transition cost to minimum the database will be shared by all services.

## Consequences
* Deployment was made easier, because a change in one component triggers the deployment of only that service that contains the component.
* Scaling is now more fine-grained where we can make individual scaling decision per service as opposed to monolith where all scaling decisions affect the system as a whole.
* More deployment artifacts for DevOps to maintain.
* Shared database accessed by multiple independent services needs some partitioning technique applied.
