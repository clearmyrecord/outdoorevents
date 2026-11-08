# Outdoor Events Association — Rebuild Prototype

A responsive, browser-based rebuild of the event sponsorship platform, based on the 12 supplied reference screenshots and `OEA-Final-Review.xd`.

## Run
Open `index.html` in a modern browser with internet access for map tiles and the Leaflet map library. For the most reliable experience, serve this directory locally (e.g. run `python -m http.server 8000` in this directory, then open http://localhost:8000). No build process or package installation is required.

## Included functionality
- Event and site-style listing dashboard
- Five-step event creator: description, event details, interactive unit placement, media uploads, review and publish
- Event marketplace search, event detail pages and available-unit counts
- Sponsor artwork submission and organizer review: approve / request changes / decline
- Unit claiming after artwork approval with demo account balance/price calculations
- Client/placement list, media library, browser data backup/import
- Switchable Organizer/Sponsor/Admin demo roles (visual convenience, **not authenticated access controls**)
- One demonstration event: **Rhythm N Blooms**, explicitly sample data. Dates/details are fictionalized.

## Important limitations
This is a usable **front-end prototype**, not production infrastructure. It uses browser localStorage, so data is only available in the current browser/profile, cannot support multiple users, and can be lost when site data is cleared. Uploaded images are limited to ~1.5MB to minimize browser storage failures. Event media kits are stored as text/links. Real map functionality requires third-party CDN/tiles. No email, verification, moderation security, persistent cloud storage, payments, invoicing, or inventory concurrency locking is present. A unit claim is **not** a purchase or actual commercial reservation. Do not use for live selling until these are added.

## Recommended production build phases
1. Hosted database with event, unit, sponsor, artwork, decision, reservation, and payment models, plus role-based authentication.
2. Secure media storage, image processing, organizer-approved brand exclusions and revision history.
3. Stripe Checkout/Connect as appropriate, transaction records, event unit holds, server-side inventory locking, receipts and refunds.
4. Sponsor/organizer notifications, onboarding, audit trail and robust mobile map placement.
5. QA, accessibility, privacy, deployment, domain integration and real company branding.

## Reference material
- `assets/reference/1.png` through `12.png`: supplied original screen designs
- `assets/reference/OEA-Final-Review.xd`: supplied original Adobe XD file
- Vimeo reference: https://vimeo.com/379374522

The logos, brands, dates, and artwork in the screenshots are **reference materials only**. The rebuilt interface does not claim affiliation with the pictured brands.


## Version 1.1: Eight-category mapped inventory
The map placement editor now includes the supplied map legend: portable toilets, VIP luxury toilet trailers, shower trailers, trash cans, Box Chairs, barricades, tents and stages. Select an asset category before clicking the map; drag to position. Each placement retains an independent type and optional price override (otherwise event default). Existing placements without a type are interpreted as portable toilets for backwards compatibility. Event detail and claim workflow display asset types, availability and per-placement prices. The original legend is included at assets/reference/Legend.JPG.

## Version 2.0: Original event management expansion
Researched against Eventeny's publicly documented *capabilities*, not its copyrighted interface or source code. Added six browser-local modules via `modules.js`, reachable from the top navigation:
- **Vendors:** custom event-linked vendor/exhibitor submissions, contact details, requested space, fee estimate, notes, manual approval/waitlist/decline decisions, booth assignment.
- **Tickets:** ticket types with prices and capacity; demo attendee issue codes, check-in / undo check-in, search; no real sales, QR scanner or payments.
- **Volunteers:** shifts with start/end, capacity and location, volunteer signup and check-in.
- **Schedule:** speaker/performer/session programming with event dates, times, stages, and categories.
- **Sponsor CRM:** opportunity pipeline, packages, proposed value, follow-up date, deliverables and stage updates.
- **Reports:** per-event operational summary and downloadable CSV; full existing JSON workspace export remains available.
All records are locally persisted in the same localStorage workspace and included in JSON export/import, with backwards compatibility for prior backups.

### Scope note
This is **not** a full Eventeny replica, and no Eventeny software, site assets, copy, logos, customer data or proprietary interface is included. The following require a further production engineering effort: authenticated multi-user roles, customizable application form builders and jury scoring, attached documents and e-signatures, secure multi-tenant infrastructure, ticket checkout/refunds/QR scanning, physical POS/hardware, inventory locks, online vendor storefronts and product payments, dynamic seat maps and indoor floorplan drawing, automated notifications, contracts, invoices, actual payment collection/payouts, and mobile applications. The map still focuses on OEA's distinctive outdoor advertising inventory.

### Original expanded map assets
- `assets/reference/Legend.JPG`: eight placement categories
- `assets/reference/HOVER_OEA_LEGEND.ai`: original Illustrator drill-down legend (not yet fully interactive in the app)
- `assets/reference/hover_oea_preview.png`: preview of that original Illustrator design
