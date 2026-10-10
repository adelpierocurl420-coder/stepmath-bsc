# Changelog

## Polish pass (final)
- Home: navy hero with live stats (fests, events, registrations, seats open), clear primary action, compact judge strip with numbered steps.
- Event cards: left status rule (open / few seats / full or closed), seats-left text, higher-contrast badges.
- Confirmation ticket redesigned: header band, large REG ID, QR with ID fallback when offline, perforated footer.
- Organizer: 4x2 KPI grid, chart bars now scale correctly (was clipped flat), sticky table headers, row hover, nowrap badges.
- Phones: all four nav items visible, header padding fixed, 2-column KPIs.
- Fixes: favicon added (no 404 console error), status set to waitlist now promotes, demo data skewed toward recent days so the 7-day chart reads naturally.
- Verified in a headless browser at 1280px and 390px: browse, search, filter, register, validation, duplicate block, ticket, My Registrations edit, session persistence after reload, participants search, check-in by ID and email, waitlist join, capacity-raise promotion, CSV export, reset. No JS errors.
- `dist/index.html` synced; screenshots regenerated.
