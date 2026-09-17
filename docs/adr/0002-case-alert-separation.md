# ADR 0002: Case and Alert Are Separate Aggregates

Status: Accepted

## Decision

A Case represents investigation/work management. An Alert represents an authorized public communication campaign associated with a Case.

A Case may have no public Alert. Alert publication cannot be represented as a boolean/public flag on a Case.
