# Region 3 Fleet Maintenance — No Login

A standalone Node.js website for Tennessee Rural Service Patrol Region 3.

## Features
- No login, account creation, or PostgreSQL dependency
- Fleet units 8300–8323; 5,000-mile oil change interval and 500-mile warnings
- Work orders, equipment inventory, supply requests, CSV reports and JSON backups
- Server-side JSON data saved to `DATA_DIR/records.json`

## Railway setup
1. Upload the **contents of this ZIP** to the root of the GitHub repository connected to Railway. Replace older `server.js`, `package.json`, and `public` files. Commit changes to the branch Railway deploys.
2. Railway start command: `npm start` (or leave automatic detection). No database variables needed.
3. **IMPORTANT:** Add a persistent Railway Volume mounted at `/app/data` and set environment variable `DATA_DIR=/app/data`. Check Railway's service working directory if using a custom root directory. Without a volume, saved data may disappear on redeploy.
4. Redeploy and verify the new deployment succeeded. Refresh the browser (Ctrl+Shift+R).
5. Custom domain DNS is configured separately and does not replace deployment.

## Important security notice
This app intentionally has **no authentication**. Anyone with access to the public URL can view, edit, or delete all records. Do not use for confidential or sensitive information. Restrict network access if appropriate.

## Run locally
`npm start`, then visit http://localhost:3000.
