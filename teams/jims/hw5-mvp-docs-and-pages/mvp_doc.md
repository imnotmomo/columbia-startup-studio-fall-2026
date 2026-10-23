# SettleWise MVP Brief

**Team Jims:** Jorim Chua, Maria Aezah, Izum Adnan, Sami Qian
**Date:** October 23, 2026
**Live:** https://settlewise.group · **Repo:** [JIMS-CU/Settlewise](https://github.com/JIMS-CU/Settlewise)

---

## 1. What we're building

**The problem.** Once NYC renters have found a few apartments that could work, the details are scattered across listing tabs, screenshots, group chats and half-finished spreadsheets. Listings leave out things that matter (broker fee, laundry, pets, guarantor rules), decisions have to happen in hours, and it's hard to see the trade-offs or what still needs asking. Our interviewees tracked options in Excel (one family tracked about 60 listings), WhatsApp and Messenger, and several signed under deadline pressure and were surprised later.

**Who it's for.** NYC renters at the comparing stage, not the searching stage: students and newcomers first (our interview sample), plus the parents and guarantors who sign for them.

**Core flow.**

| User | Action | Value |
|---|---|---|
| A renter with 2–5 apartments in mind | Adds them to SettleWise (one click from a StreetEasy page, or paste a Zillow/StreetEasy link and fill in details) and picks what matters to them | Sees all of them side by side, in their own priority order, with missing details shown as "Not listed" instead of guessed |

**First aha moment:** the renter sees two or more of *their own* apartments in one comparison and spots a detail one listing never mentioned. Everything in the MVP is the shortest path to that screen.

Background, not repeated here: [brand position](../hw4-synthesis-brand-position/brand_position.md) · [synthesis](../hw4-synthesis-brand-position/synthesis_comparison.md) · [interview notes](../hw3-interviews/Housing/) · [Reddit research](../hw4-synthesis-brand-position/reddit_research/) · [personas](../hw4-synthesis-brand-position/personas/)

---

## 2. MVP features

1. **Account:** create an account with email and password; log in, log out, reset password. The workspace opens only when signed in.
2. **Search groups:** a named apartment search (e.g. "My NYC Apartment Search") holding its own apartments and comparison fields.
3. **Add an apartment by link:** paste a Zillow or StreetEasy link; the original link is saved and opens from the apartment's name.
4. **Save to SettleWise button (Beta):** a bookmarklet that saves a StreetEasy listing in one click, reading address, rent, neighborhood and more from the page, with an Undo message.
5. **Listing photos:** a Save to SettleWise click keeps up to 5 of the listing's photos.
6. **Edit details:** fill in or correct any value, including answers learned later from a landlord.
7. **Side-by-side comparison:** apartments in columns, details in rows; missing values read "Not listed" / "Not added".
8. **Custom fields:** add a detail such as "Pets allowed"; it appears for every apartment in the group, with a separate value for each.
9. **Drag to prioritize:** put the details that matter most at the top.
10. **Non-negotiables:** mark must-haves and a maximum rent; apartments that miss them are flagged.
11. **Order by your priorities:** apartments are ordered by the renter's own priority list, with a plain explanation of how the order works.
12. **Delete apartments** the renter has ruled out.
13. **Source labels:** every imported value says where it came from ("From the StreetEasy page", "Added by you").

---

## 3. What comes later (rough order)

1. **Share a read-only comparison** with a parent, guarantor or roommate. The /for-parents page promises a shared view; this is what makes that promise real.
2. **"Why it's here" line and confirmed-before-missing ordering.** The top post-build persona requests: explain each apartment's place in words, and don't let missing details look like good news.
3. **"Worth checking" prompts:** plain-language nudges about what a listing leaves out (broker fee, guarantor, laundry) to ask before touring. Shown on the homepage as a preview.
4. **Paste listing text for phones:** paste a listing's text and have details filled in with an AI model, each value backed by a quote from the text. Phones can't use the bookmarklet.
5. **Address matching with NYC GeoSearch:** standardize the address and get the building IDs (BBL/BIN) that public-records features need.
6. **NYC building records:** HPD violations and 311 complaints with dates and status, framed as leads, not verdicts. Redditors say these "tell the real story".
7. **Full monthly cost:** broker fee, deposits, guarantor fees and net-effective rent rolled into one comparable number. Students' biggest surprise.
8. **Tour notes and photos/videos** per apartment, so what was learned on a tour lives next to the listing.
9. **Google sign-in** to cut sign-up friction, once we know email sign-up converts.

---

## 4. What's cut and what's faked

**Cut for now:** commute calculations, listing refresh and "is this still up?" checks, archived apartments, photo uploads by the renter, building records, AI extraction, a browser extension, email verification, marketing emails, account settings and deletion, and a phone-friendly one-click import.

**Wizard of Oz (done by hand behind the scenes):**

- **Details for pasted links.** Pasting a link saves the link only. For our first users, a team member (Jorim or Maria) opens the listing and types in rent, fees, laundry, pets and guarantor details by hand, so the renter sees a filled-in comparison the same day instead of an empty one. If this is wanted, it becomes the AI paste feature.
- **"Worth checking" questions.** Not automated. For early users who ask, a teammate reviews their comparison and writes the 2–3 questions to ask the landlord, in our voice.
- **Shared view for parents.** Not built. A parent who signs up from /for-parents gets their own workspace; until sharing exists, the renter can send a screenshot, and we use those sign-ups to measure whether parents want the real thing.
- **Phone users.** The bookmarklet is desktop-only; phone users paste a link and the same hand-entry above applies.

---

## 5. Stack and services

**Framework:** Next.js + React + TypeScript, Tailwind, Radix UI, Lucide icons, React Hook Form + Zod. Backend: Python FastAPI (bookmarklet saves, bookmark keys, photos).
**Coding agent:** Claude Code with our feature-forge skill (brief → architecture → plan → build → review, with synthetic persona reviews). Runs on teammates' existing Claude plans.
**Hosting:** Railway, two services (Next.js frontend, FastAPI backend). Domain: settlewise.group.

| Service | What it does for us | Cost to us now |
|---|---|---|
| Railway | Hosts the frontend and backend | Hobby plan, $5/month (includes $5 of usage, enough for both services at our traffic) |
| Domain (settlewise.group) | Public URL | About $20/year (.group domain) |
| Firebase Authentication | Email/password sign-in, password-reset emails; the list of sign-ups | $0 (free tier) |
| Cloud Firestore | Database: search groups, apartments, field values | $0 (free tier: 1 GiB, 50k reads and 20k writes a day) |
| Cloudflare R2 | Stores listing photos | $0 (free tier: 10 GB, no egress fees) |
| Google Analytics 4 | Page views and the landing page → sign-up funnel | $0 |
| GitHub | Code, reviews, class submission | $0 |
| Anthropic API (later, feature 4) | AI extraction from pasted listing text | Not used yet. Planned: about 2–4 cents per extraction, with a monthly spending cap |
| NYC GeoSearch (later, feature 5) | Address matching | $0, no key |

**Total today: about $5/month plus the domain.** Payments and transactional email are not needed for the MVP (Firebase sends reset emails).

---

## 6. How we'll know it works

**The action we measure:** account creations (Firebase → Authentication → Users), split by landing page using GA4 paths (landing page → `/signup` → `/dashboard`).

**The activation check:** of those accounts, how many save 2+ apartments in one search group within a week. That is the aha moment, read from Firestore.

**Keep going if, two weeks after we start driving traffic:**

- **40+ accounts** created from outside the team and class.
- **30%+ of accounts** save at least 2 apartments (they reached the aha moment).
- **At least one landing page converts visitors to sign-ups at 2x the weakest**, which tells us which value prop to lead with.

**Rethink if:** under 15 accounts, or under 10% of accounts save two apartments. Lots of sign-ups with no saved apartments means the promise pulls but the product doesn't deliver, and we look at adding apartments first.

---

## 7. Risks and open questions

**Risks:**

- **Adding apartments is too much work.** If renters must type details, SettleWise is "just another spreadsheet". The bookmarklet helps on desktop only; most hunting happens on phones.
- **StreetEasy changes its page** and the bookmarklet stops reading it. Reading fails safely to "Not listed", but the value drops.
- **The window is short.** Renters compare for days, not months, so each user is short-lived and word of mouth matters more than retention.
- **Spreadsheets are free and good enough** for some renters (Sean: "it's just not that deep").
- **Our evidence is narrow:** five interviews, mostly students, plus Reddit. Persona reviews are synthetic, not real users.
- **Per-page attribution is approximate.** Accounts aren't tagged with the page they came from; GA paths can undercount (ad blockers, cookie consent).
- **Privacy:** GA sets cookies; we have no consent notice or privacy page yet.

**Open questions:**

- Does the parents/guarantor angle pull sign-ups, and do parents or renters create the account?
- Will students on a budget sign up before they have listings, or only once they're mid-search?
- Is the bookmarklet setup too awkward for non-technical renters beyond our one tester?
- Should the ordering ever look like a ranking? The brand says "We don't rank apartments for you"; the priority ordering needs testing with real renters.
- Which AI model and spending cap for pasted text, once we build it?

---

## 8. Roles

| Person | Builds / owns | Owns traffic for |
|---|---|---|
| **Jorim Chua** | Backend and infrastructure: FastAPI service, Save to SettleWise bookmarklet, listing photos (R2), accounts and sign-in, Firebase and Railway setup, the MVP stages (drag to prioritize, edit values, delete, non-negotiables, priority ordering). Submits the team's homework PRs. | Homepage (settlewise.group) and the overall sign-up count |
| **Maria Aezah** | Frontend workspace: dashboard, search groups, add first apartment, apartment details, comparison table; homepage design and motion; Google Analytics. Wizard of Oz detail entry with Jorim. | /compare-apartments |
| **Izum Adnan** | /for-parents landing page; shipped /students-on-a-budget to the live site; this MVP doc and the HW5 README. Runs the weekly sign-up and activation numbers (section 6). | /for-parents |
| **Sami Qian** | /students-on-a-budget landing page (copy and design); writes the "Worth checking" questions for early users who ask. | /students-on-a-budget |

Each traffic owner posts their page in the communities where its audience already is (Columbia and other NYC student groups, r/NYCapartments where rules allow, parent and international-student groups) and reports sign-ups for their page each week.
