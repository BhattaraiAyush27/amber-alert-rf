# ADR 0001: Modular Monolith First

Status: Accepted

## Decision

Build the operational backend as one Laravel deployment with explicit domain boundaries. Do not start with microservices.

Potential future extraction boundaries include distribution/notifications, geospatial processing, media processing, search, analytics, and ML workers.

## Rationale

The system needs transactional consistency, clear authorization, and rapid evolution more than distributed deployment complexity. Domain events/outbox boundaries will preserve future extraction options.
