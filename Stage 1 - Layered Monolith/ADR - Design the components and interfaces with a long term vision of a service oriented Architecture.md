# ADR 4 - Design the components/interfaces with a long term vision of a service oriented Architecture

## Status

Accepted

## Context

The Layered Monolith is seen as a valid short term solution but will not easily scale and will be harder to maintain in the long run.

## Decision

Design the business logic layer and interaction with other layers already with the assumption that these will be later segregated into separate services.

## Consequences

This increases the complexity but on the other hand is already a step towards our long term vision.