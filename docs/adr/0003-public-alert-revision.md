# ADR 0003: Public Alert Revisions Are Deliberate Immutable Snapshots

Status: Accepted

## Decision

Public APIs read from published Alert Revision data. They do not dynamically serialize/join internal Case records.

Approved/published revision content is immutable. Material changes create a new revision requiring its own review/approval.

## Consequence

We intentionally duplicate selected public values from the Case into the revision. This duplication is a security and audit feature, not accidental denormalization.
