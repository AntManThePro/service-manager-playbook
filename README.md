# NEXUS // Service Manager OS (Playbook)

A local-only service manager playbook for a field-service lead: 7-day Mission
Board with checkable tasks, Quick Capture (coaching / crew visit / action),
Leadership Pulse KPIs (crew visits 0/6, coaching 0/8), Weekly Win + weekly
review, and an activity feed. Everything saves to localStorage under
`nexus_manager_os_v1`; the app starts empty and there is no account, no
cloud call, and no external load of any kind (no CDN — fully self-contained).

## Which variant this is

Source: `HB_Service_Manager_Playbook.html` (27,690 bytes, 463 lines) from the
phone batch — byte-identical to the Drive copy. It is the most complete of
the single-file playbook family:

- `SMPlaybookV3.html` == `SMPlaybookV4.html` (7,866 bytes) — "NEXUS //
  Service Manager v3". Same feature shape (mission board, quick capture,
  activity log, voice command) but smaller, Tailwind CDN, and a hardcoded
  default edit password (`antmanpro`) in plaintext client-side JS. Rejected.
- `SMPv4.html` (9,077 bytes) — "NEXUS v4 // Service Manager". Same shape
  plus export/import; also a hardcoded default edit password (`antpro2026`)
  in plaintext. Rejected.
- `HB_Service_Manager_Playbook.html` — picked. Bigger and more complete
  (mission board + Leadership Pulse + Weekly Win/review + candidates tab),
  zero external loads, and **no password anywhere** — no client-side gate
  at all. Editing is open in the app; protection is the Netlify Team login
  on the published site, the same pattern as the live SMOS v7.

## Not this app

- **SMOS v7** (`nexus-hood-boss-smos`) is a separate, already-live app — the
  full Service Manager OS "TRUTH PACKET". This playbook is a smaller,
  standalone planning/tracking tool, not a replacement for it.
- **Service Manager OS Fullstack** (FastAPI + SQLite + JWT + Docker) is a
  real backend and cannot be a Netlify static push; it needs a Docker/Python
  host and is out of scope for this repo.

## Notes

- JS passes `node --check` (both inline script blocks).
- No `Math.random`, no seeded demo records — starts empty.
- No banned branding (godmode2025.net / TwistedGenius), 0 hits.
- No fetch/XHR, no secrets.

## Live

https://service-manager-playbook.netlify.app/

## How to use

1. Open the live site — it starts empty, just for you.
2. Tap a day on the Mission Board and check tasks off as the week moves.
3. Use Quick Capture to log coaching, a crew visit, an interview, or an action.
4. Check Leadership Pulse for the week, and save a Weekly Win + review before Friday.

Everything saves in your browser only (localStorage). No account, no cloud.

## Links

- Live site: https://service-manager-playbook.netlify.app/
- NEXUS World Hub: https://nexus-world-hub.netlify.app/
- Repo: https://github.com/AntManThePro/service-manager-playbook
