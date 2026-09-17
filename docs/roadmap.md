# Implementation Roadmap

1. Architecture contract and repository baseline.
2. API primitives: ULIDs, request IDs, response/error envelope, versioning.
3. Identity/authentication with Sanctum + Fortify.
4. Organizations, Memberships, roles/abilities and policies.
5. Jurisdiction model.
6. Audit foundation.
7. Case aggregate and restricted information.
8. Secure media/evidence boundary.
9. Case verification workflow.
10. Deterministic alert-eligibility/policy engine.
11. Alert aggregate and immutable revisions.
12. Approval/publication workflow.
13. Public Alert API and leak-regression tests.
14. Operator/public React UI.
15. PostGIS geographic targeting.
16. Tips/sightings and abuse controls.
17. Transactional outbox and distribution engine.
18. Push/SMS/email adapters.
19. Reliability/observability/load testing.
20. External integrations.

ML work runs in parallel: source registry -> raw acquisition -> audit -> target/feature definition -> baselines -> Random Forest -> evaluation/model card -> versioned inference -> shadow mode -> monitored advisory UI.
