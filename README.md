# Amber Alert RF

Production-oriented missing-person / abducted-child emergency alert platform.

This repository is a clean rewrite of the earlier college proof-of-concept. The old project is reference material only; no architectural compatibility is assumed.

## Core invariants

1. A Case is not an Alert.
2. A public Alert never serializes investigative Case data directly.
3. Alert content is versioned as immutable Alert Revisions.
4. Case verification and Alert approval are separate decisions.
5. Organization membership and authorization are evaluated server-side for every protected action.
6. ML assessments are advisory and cannot publish, approve, or otherwise transition an Alert.
7. Important state transitions occur through explicit domain Actions and are auditable.
8. Cross-organization access is denied by default.
9. Restricted data is not copied wholesale into logs or audit records.
10. External distribution is idempotent and traceable to an exact Alert Revision.

## Planned repository layout

```text
amber-alert/
├── backend/      # Laravel 13 JSON API
├── frontend/     # React + TypeScript + Vite SPA
├── ml/           # Python ML package and reproducible training pipeline
├── infra/        # local/dev deployment assets
└── docs/         # architecture, domain, security and ML contracts
```

## Status

Milestone 0: architecture contract.
