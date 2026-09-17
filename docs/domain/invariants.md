# Domain Invariants

These rules are architecture constraints, not implementation suggestions.

## Case / Alert separation

- A Case may exist with no Alert.
- An Alert must reference one Case.
- Public endpoints must not serialize Case models directly.
- Ending an Alert does not automatically resolve its Case.
- Resolving a Case requires an explicit decision about any active Alert.

## Alert revisions

- Published/approved Alert Revision content is immutable.
- Any material public-content change creates a new revision.
- Approval attaches to the exact revision, never to a mutable Alert record.
- Distribution records always identify the exact revision sent.

## Human authorization

- Case verification and Alert approval are distinct.
- The default policy forbids an Alert Revision author from approving their own revision.
- ML output cannot satisfy a verification or approval requirement.
- Frontend role checks are UX only; backend policy checks are authoritative.

## Organization isolation

- Internal Cases are owned by exactly one Organization in v1.
- Access to an internal resource requires an active membership in the owning Organization plus the required ability.
- Suspended or revoked memberships cannot perform protected actions.

## Information safety

- Public Alert data is deliberately copied/transformed into Alert Revisions.
- Restricted information is never made public because a source Case field exists.
- Tipster identity is stored and authorized separately from ordinary tip content.
- Audit/logging mechanisms never dump complete request bodies or Eloquent models by default.

## Machine learning

- The application remains fully operational when ML is unavailable.
- ML inference is asynchronous by default.
- Every production assessment identifies its model version and feature-schema version.
- Training data, transformations, metrics, and artifacts are reproducible and versioned.
