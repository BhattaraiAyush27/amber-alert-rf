# Next Implementation Slice

After committing this architecture contract:

1. Scaffold `backend/` with Laravel 13.
2. Install API support/Sanctum and Fortify.
3. Configure PostgreSQL.
4. Add Pest, Pint, Larastan at maximum practical strictness.
5. Scaffold `frontend/` with Vite React TypeScript and pnpm.
6. Scaffold `ml/` as a typed Python package.
7. Add root CI and editor configuration.
8. Implement only platform primitives next: request ULID + standard JSON envelope + exception mapping + tests.

Do not create Case/Alert tables before Identity/Organization foundations are complete.
