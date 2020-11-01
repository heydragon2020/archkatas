# ADR - Smart Fridge Hub/Adapter

## Status

Accepted

## Context

Smart fridges with different proprietary APIs might be used. 

## Decision

We need to contain this complexity by providing an abstraction over smart fridge API. Therefore we need an adapter for each type of API hosted in a fridge hub that would convert fridge requests into common API exposed by our service(s).

## Consequences

* Changes to public API exposed by services could potentially be more difficult because a single change in common API (such as adding a new common functionality) might trigger different changes in different fridge adapters.
* Adding a new type of smart fridge should normally only mean a new adapter without the need to change the common API.
* New deployment artifact - the fridge hub + adapters.
