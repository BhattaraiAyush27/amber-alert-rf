# Initial Threat Model

## Primary security objectives

1. Prevent unauthorized or false public alerts.
2. Prevent leakage of child/minor, family, tipster, evidence, and investigative data.
3. Preserve traceability of high-impact actions.
4. Prevent cross-organization access.
5. Continue core operations during ML, queue, or provider failure.

## Representative threats and controls

### False alert issued by compromised or malicious operator
Controls: least privilege, independent approval, step-up auth before publication, audit, immutable revisions.

### Cross-tenant IDOR
Controls: organization-scoped routes/queries, policies, ownership checks, feature tests for foreign ULIDs.

### Private information exposed through public serializer
Controls: public AlertRevision model/read boundary; public API never serializes Case models; regression tests with secret sentinel values.

### Post-approval mutation
Controls: immutable Alert Revisions; changes create new revisions and invalidate prior approval for new content.

### Duplicate/replayed distribution
Controls: idempotency keys, unique distribution constraints, exact revision identity, expiry/state checks.

### Sensitive information duplicated into logs/audit
Controls: allow-listed structured log context; safe audit payloads; request-body logging prohibited for sensitive routes.

### Malicious public tips/uploads
Controls: rate limiting, quarantine, MIME/content validation, abuse triage, separate tipster identity.

### ML failure or manipulation
Controls: advisory-only output, asynchronous inference, model/version provenance, feature validation, human review, system operates without ML.
