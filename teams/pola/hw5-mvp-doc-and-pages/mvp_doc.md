# AstraPath MVP

**Team Pola, 2026-10-23.** This is a course-internal demo for review and testing. The landing pages are live ([README](README.md)), and the app download link follows in a few weeks.

## What we're building

Map apps stop at the building's front door. Inside, people lose minutes to the wrong hallway or the wrong door. AstraPath guides you from the front door to the exact room, starting with students who have a few minutes between classes. For details, see the [brand position](../hw4-synthesis-brand-position/brand_position.md), the [interviews](../hw3-interview/), and the [synthesis](../hw4-synthesis-brand-position/synthesis_comparison.md).

**Core flow:** a student at Northwest Corner Building (**user**) picks a start, a destination, and the access they have, then follows the route floor by floor (**action**). Before walking, they see which hallway, stairs, or elevator leads to the room (**value**).

## MVP features (built; Northwest Corner only)

- A 3D building model: pick a floor to cut the building open.
- Place search, with shortcuts for restrooms, elevators, and stairs.
- Routes with three preferences: Fastest, Fewer changes, and Least effort.
- "I have" access options (cards, keys, student status), plus a choice for how to handle doors with uncertain access.
- Step-by-step directions that move the map floor by floor.
- Ask: Claude with the TopoNavi MCP tools. It answers in any language and knows the local time and weather.
- An iPhone app (Capacitor), and a campus model of Morningside that works offline.

## What comes later (built in parallel, not in order)

- **Calendar-link and QR-code entry,** so first use doesn't need a download.
- **Checked step-free routes,** because a wrong turn costs some people ten minutes and pain.
- **"Last checked" dates,** to show which parts of a route are confirmed.
- **Visitor routes** in buildings that have confirmed their access rules, so visitors aren't sent to badge-only doors.
- **Venue plans:** buildings pay, and visitors use AstraPath for free.
- **Automated mapping from floor plans, and feedback from use,** so maps scale and keep improving.

## What's cut and what's faked

**Cut:** other buildings, accounts and sign-in, notifications, always-on location (the user picks the start)

**Faked:** maps are written by hand in TopoScript (Jiawen Li, Oleh Goumain). A few Northwest Corner floors are interpolated from the typical layout of other floors.

## Stack and services

- **Framework:** OpenSpec ([repo setup](../hw4-synthesis-brand-position/repo_setup.md)).
- **Coding agents:** Claude Code, Codex, GitHub Copilot.
- **App:** React 19, TypeScript, Vite, three.js, Capacitor 8.
- **Engine:** [TopoNavi](https://github.com/HarryLiGameTech/indoor-topo-navi) (Scala 3 and Java, Spring Boot) and [toponavi-mcp-server](https://github.com/HarryLiGameTech/toponavi-mcp-server) (TypeScript).
- **Hosting:** the pages are on Netlify, and the engine runs on a team-run Debian machine reached over Tailscale. The app has no public hosting yet.

| Service (under $50 in total so far) | Use | Cost |
|---|---|---|
| Anthropic API (Claude Opus 5.5) | Ask | $4 / $20 per million input / output tokens |
| Netlify + Netlify Forms (netlify.app subdomain) | Pages and waitlist signups | $0 on the Free plan |
| Tailscale | Access to the engine | Within the $50 total |
| PostgreSQL | Engine database, self-hosted | $0 |
| Open-Meteo, OpenStreetMap | Weather; campus model | $0 |
| Google Analytics 4 | Traffic and signups by page | $0; not connected yet |

There is no sign-in, payment, or email-sending service.

## How we'll know it works

AstraPath has no accounts by design, so each person we can count is one user. We count:

- waitlist and venue signups, by page
- referral signups
- testers who finish a route
- iPhone installs, once the app is available

Each person counts once, matched by email where we have it.

On the MVP itself, we measure whether testers reach the room without doubling back or asking someone. **We keep going if** at least 8 of 10 testers do, including on the interpolated floors, and signups are on track for 100 users by Demo Day (December 18).

## Risks and open questions

- One wrong instruction ends trust, and the interpolated floors are the most likely place for one.
- The need fades after a first visit, and free alternatives (signs, asking someone) often work.
- There is no link or QR entry yet, and people would rather not install an app.
- The engine runs on one machine and isn't public yet.
- Wrong access rules send people to locked doors, and mapping by hand doesn't scale.
- **Open questions:**
  - How do we host the engine publicly?
  - Will people come back to use it in other buildings?
  - Which audience signs up most?
  - Will anyone, or any venue, pay?

## Roles

| Person | Builds or owns |
|---|---|
| Jiawen Li | Backend (the TopoNavi engine and its API), plus some mapping |
| Oleh Goumain | Mapping and testing |
| Yining Ma | Frontend (web and iPhone app), plus some marketing |
| Isha Mitra, Sophia Hirao | Marketing; traffic owners |
