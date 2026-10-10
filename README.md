# Region 3 Maintenance - clean deployment

This package uses a single compatible frontend and backend. It contains `server.js`, `package.json`, and a `public` directory with `index.html`, `app.js`, `style.css`, and `region3-banner.png`.

## GitHub deployment
1. Download and extract this ZIP.
2. In the GitHub repository root, replace the existing `server.js`, `package.json`, and `public/` files with these files. Remove any older root `index.html` and `app.js` files to prevent confusion. **Do not delete an existing data directory or database.**
3. Commit changes to the branch used by Railway. Check Railway deployment commit and hard-refresh the site.
4. Check `https://region3maintenance.com/api/data` returns JSON (not `Not found`).

## Persistent data
Mount a Railway volume at `/app/data` and set `DATA_DIR=/app/data` if `/app` is the application's working directory. Without a volume, records may be lost on redeployment. If existing records are elsewhere, migrate them before switching DATA_DIR. No login: anyone with the URL can edit or delete records.
