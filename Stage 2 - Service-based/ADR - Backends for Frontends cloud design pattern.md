# ADR - Backends for Frontends cloud design pattern

## Status

Accepted

## Context

We are required to support multiple different frontends (mobile/web/POS) that certainly have different requirements.

## Decision

Use a BFF cloud design pattern where each type of frontend has a corresponding backend service. We can then have an optimized Mobile Backend Service, POS Backend Service, etc.

## Consequences

This enables us to fine-tune the behavior and performance of each backend to best match the needs of the frontend environment without worrying about affecting other frontend experiences. A potential drawback is code duplication and the associated downsides of that.
