# ADR 1 - Layered Monolith as a short term Architecture

## Status

Accepted

## Context

Our assumption is that time to market is critical so the initial cost and complexity need to be low. Scaling is not a major concern at the moment when looking at the current and foreseeable (next few months) number of users.

## Decision

Use a Layered Monolith Architecture as a pragmatic initial approach but with a clear separation of concerns and abstractions in place to allow an evolution to a service oriented and eventually micro services Architecture.

## Consequences

We get a faster time to market but incur the risk of taking longer (or even worse, being blocked) to get to a more future proof Architecture.
