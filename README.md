# FestDesk

**Smart club operations** for student organizations — browse fests, explore events, register without Google Forms, and manage everything from an organizer dashboard.

Built for the **9th DRMC International Tech Carnival 2026 — AI Web Development Contest**  
Theme: *Smart Club Operations* · Hierarchy: **Organization → Fest → Event → Registration**

## Live demo

**Deployment URL:** `REPLACE_BEFORE_SUBMIT: https://your-app.netlify.app`

**GitHub:** `https://github.com/adelpierocurl420-coder/stepmath-bsc`

### Demo credentials (organizer)

| Field | Value |
|--------|--------|
| Username | `admin` |
| Password | `admin123` |

### 60-second judge path

1. **Home** — fests, search, category filter, open-only  
2. Open an **event** — description, venue, deadline countdown, capacity, register  
3. See **confirmation ticket** (registration ID + QR)  
4. **My Registrations** — look up by email, edit or cancel  
5. **Organizer** — sign in → Overview chart → Participants → **Check-in** tab  

## Features

### Fest directory (required)
- List fests and events with category, time, venue, deadline, seat fill bar  
- Search, category filter, fest filter, “Open only”  
- Fest detail page and full event detail page  

### Registration (required)
- Validated form (name, email, phone, institution, notes)  
- Confirmation ticket with unique registration ID  
- Capacity limits and registration deadlines  
- **My Registrations** — view, edit details, cancel (frees seat)  
- Instant confirm or manual approval per event  

### Organizer (required)
- Dashboard with KPIs and fill rates  
- Participants table: search, filter, change status, delete  
- Create / edit / delete fests and events  
- CSV export of participants  

### Bonus / creative extras
- **Waitlist** when an event is full (auto-promote when a seat opens)  
- **QR code** on the confirmation ticket  
- **Check-in** tab for organizers (lookup by REG ID or email, check-in count)  
- **Registrations last 7 days** chart  
- **Live countdowns** to deadline and event start  
- **Per-event announcements**  
- Light / dark theme, printable ticket, responsive layout  

## Tech stack

- Single-page app: HTML, CSS, vanilla JavaScript (`index.html`)  
- Hash routing (`#/event/...`, `#/admin`, …)  
- `localStorage` persistence (no backend required for demo)  
- Netlify static hosting (`dist/`)  
- QR images via [goqr.me API](https://goqr.me/api/) (qrserver.com)  

## Setup

```bash
git clone <your-repo-url>
cd <repo>
# open index.html in a browser, or:
python3 -m http.server 8000
# http://localhost:8000
```

Netlify: publish directory `dist` (see `netlify.toml`). Build: `npm run build` (copies `index.html` → `dist/`).

Sample data is generated on first load (dates relative to “today”). Use **Organizer → Reset demo data** to restore.

## Deployment URL

`REPLACE_BEFORE_SUBMIT:` add your live Netlify URL here (same as above).

## Demo credentials

- **Username:** `admin`  
- **Password:** `admin123`  

## Third-party services / APIs

- **QR code images:** `https://api.qrserver.com/v1/create-qr-code/` (for ticket QR)  
- No paid APIs; no account required for the QR image service  

## AI tools used

Development was assisted by AI tools including **Claude**, **ChatGPT**, and **Grok**, used for scaffolding UI, feature ideas, and debugging. Product design, feature choices, testing, and deployment were directed by the participant.

## Screenshots

Captured from the current build in `docs/screenshots/`:

| File | Shows |
|---|---|
| `01-directory.png` | Fest directory, search, category/fest filters (desktop) |
| `02-event-registration.png` | Event page with deadline, capacity, countdown, form |
| `03-confirmation.png` | Confirmation ticket with QR and registration ID |
| `04-my-registrations.png` | My Registrations lookup by email |
| `05-admin-overview.png` | Organizer KPIs, 7-day chart, status bar |
| `06-admin-participants.png` | Participant table with search, filters, status control |
| `07-admin-checkin.png` | Check-in by REG ID or email |
| `08`-`10` | Mobile directory, event page and admin |

(`SCREENSHOTS.md` lists the shot checklist.)

## Known limitations

- Data is stored in the **browser `localStorage`**, so registrations on one device are not shared with another (no shared cloud database in this build).  
- QR codes need network access to the QR image API; offline, the ticket shows the registration ID instead.
- Check-in is by typing the REG ID or email (no camera scanning).
- Waitlist promotion runs in this browser's data when a seat is freed (no server).  
- Organizer auth is a simple demo login (not production-grade security).  
- Suitable as a contest / club demo; for production, add a real backend and stronger auth.  

## License

MIT License — see [LICENSE](./LICENSE).

## Project structure

```
index.html          # full app
dist/index.html     # Netlify publish copy
package.json
netlify.toml
LICENSE             # MIT
README.md
docs/screenshots/
```
