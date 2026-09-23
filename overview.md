# HOTICE Architecture

HOTICE is being built incrementally. Phase 0 contains only the application shell and operational foundation.

## Runtime

- React + TypeScript web client
- Node.js + TypeScript backend runtime provided by AppDeploy
- AppDeploy database service for the current deployment target
- REST-style API under `/api/v1`
- Structured backend logging
- Environment-aware configuration

## Boundaries

Authentication, E2EE, messaging, groups, Status, calls, Marketplace, moderation, notifications, and other product domains are intentionally deferred to later phases.

## Database note

The long-term HOTICE architecture targets PostgreSQL. The current AppDeploy deployment target exposes its managed database SDK rather than a direct PostgreSQL connection, so Phase 0 uses a small database adapter (`backend/database.ts`). This keeps the application boundary explicit and prevents platform-specific database calls from spreading through future product modules.