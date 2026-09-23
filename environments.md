# HOTICE Environment Configuration

Supported application environments are `development`, `staging`, and `production`.

`APP_ENV` selects the environment and defaults safely to `production` when the deployment platform does not provide it. `APP_NAME` and `APP_VERSION` are non-secret configuration values.

Secrets must never be committed to source code. Secret-backed configuration will be added through AppDeploy's secret management when a later phase requires it.

Phase 0 deployment readiness requires a healthy API, database health check, structured logs, and a successful production build.