# Universe ERP – Local-first PWA prototype

A mobile-first, installable progressive web app for managing a shared fictional universe.

## Included in this first working prototype
- IndexedDB local database
- Master entity registry with flexible JSON custom fields
- Entity types: characters, locations, organizations, kingdoms, bloodlines, religions, magic systems, objects, creatures, species and concepts
- Event/transaction capture with participants, in-universe date, numeric sort key, narrative placement, location and cause-event reference
- Multiple series registry
- Timeline ordered by numeric sort key
- JSON full backup and restore
- CSV export per table
- Service worker caching for offline app shell

## Run locally
PWAs require HTTPS or localhost. From this folder:
```bash
python -m http.server 8000
```
Open `http://localhost:8000`.

## Publish free with GitHub Pages
1. Create a new GitHub repository (public for free GitHub Pages on a free account).
2. Upload all files in this folder to the repository root.
3. Open repository Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch.
5. Select `main` and `/ (root)`, then Save.
6. Open the published HTTPS URL on iPhone in Safari.
7. Tap Share → Add to Home Screen.

## iPhone notes
- The app stores records in Safari's IndexedDB on that device.
- The app shell is cached for offline use after the first successful load.
- Export JSON backups regularly. Browser data is not a substitute for backup.
- GitHub Pages hosts only the app code; it does not sync private records.
- For private projects, consider a private hosting option or add authentication before any cloud sync.

## Schema direction
The app's IndexedDB stores records in separate object stores. IDs are globally unique prefixed IDs (ENT-, EVT-, SER-, etc.). The current prototype is intentionally lightweight; it does not yet enforce every relational constraint or implement all planned transaction subtypes.

## Next development increments
1. Complete relational validators and cascade/restrict rules.
2. Add dedicated relationship, movement, knowledge, ownership and status transaction forms.
3. Add books, chapters, scenes and plotline CRUD.
4. Add entity detail pages with linked transaction history.
5. Add visual relationship graph and dual-axis chronology (universe time vs narrative order).
6. Add optional encrypted cloud synchronization and conflict handling.
