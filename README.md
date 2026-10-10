# Tennessee Rural HELP — Region 3 Maintenance Portal

Railway-ready Node.js / Express / PostgreSQL starter for units **8300–8323**.

## Deploy to Railway
1. Create a private GitHub repository and upload these project files (not your `.env` file).
2. In Railway, create a new project from the GitHub repository.
3. Add a **PostgreSQL** service.
4. On the web service set `DATABASE_URL` to the PostgreSQL service's Railway connection variable (`${{Postgres.DATABASE_URL}}` if the service is named Postgres).
5. Set `SESSION_SECRET` to a long random value; set `ADMIN_EMAIL`, `ADMIN_PASSWORD` (12+ characters), and `NODE_ENV=production`.
6. Deploy. Railway will use `npm start`. Generate a Railway public domain under the service networking settings.
7. Sign in using the initial admin credentials; create supervisor and mechanic users under Users.

The admin is created only when the users table is empty. Remove `ADMIN_PASSWORD` from the Railway environment after initial setup. The application automatically creates its database tables and seeds the 24 truck numbers with **unknown starting mileage and oil-change history**. Enter actual readings before relying on alerts.

## Oil-change logic
Next oil service = last oil change odometer + 5,000. A warning appears when 500 or fewer miles remain. If there is no last oil change recorded, status is **Unknown**. Record an Oil Change under Services to establish/reset the interval.

## Notes
This is an operational starter, not a security-audited production platform. Before using for sensitive operations, add CSRF protection, login rate limits, audit trails, backups, password reset, stronger input validation, and monitoring. Restrict the Railway project and database access to authorized staff. Use HTTPS only.

## Region 3 branding
The supplied Rural Service Patrol Region 3 banner is installed at `public/region3-banner.png`. The application uses a dark charcoal, silver, and neon-green theme inspired by the banner.
