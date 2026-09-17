# ADR 0004: ML Is Advisory Only

Status: Accepted

## Decision

Machine-learning output is decision support. It has no permission to verify Cases, approve Alert Revisions, publish Alerts, or initiate emergency distribution.

## Rationale

The ML dataset and learned correlations have uncertainty, source bias, and distribution-shift risk. Safety-critical publication authority remains an explicit human/policy workflow.
