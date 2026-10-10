# Region 3 Maintenance — No Login Edition

Opens directly to dashboard; 24 units 8300–8323. Includes work orders, equipment requests, inventory and 5,000-mile service alerts.

## Railway setup
1. Push all project files to your GitHub repository (contents, not ZIP).
2. Add Railway PostgreSQL to the same project.
3. On the application service, add `DATABASE_URL` as a reference to PostgreSQL's `DATABASE_URL` variable, e.g. `${{Postgres.DATABASE_URL}}` (select the actual service name).
4. Redeploy the app. Add a public domain under service Networking if desired.

## IMPORTANT — Security
This edition has **NO authentication**. Anyone with network access to its URL can view, edit, or delete operational records. Do not expose it publicly for real operational use. Restrict access at the network/proxy layer or restore authentication before production.

`DATABASE_URL` is still required. Removing login does not remove the PostgreSQL dependency.
