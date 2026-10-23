# ClientReady — MVP brief

**Team:** Stark Labs — Handong He (`hh3152`). Mansi Rank moved to The Babysitters after Homework 4; Stark Labs is a one-person team from this homework on.
**Date:** October 23, 2026
**Live pages:** [clientready.cc](https://clientready.cc), listed with audiences in the [README](README.md)
**Product repository:** [Anzdon1/clientready](https://github.com/Anzdon1/clientready)
**Context:** [brand position](../hw4-synthesis-brand-position/brand_position.md), [interview synthesis](../hw3-interviews/analysis.md), [Reddit research](../hw4-synthesis-brand-position/reddit_research/reddit_research_summary.md), [style guide](../hw4-synthesis-brand-position/style_guide.md)

## What we're building

**The problem.** Someone agrees to build a small website from material that belongs to someone else: a friend's project, a club, a group assignment, a client. The material arrives as "one long document and a bunch of images" (CR05), or as four people's uneven paragraphs in one Google Doc (CR02), or as a chat thread with a bio still missing (CR01). The builder then spends an evening and two calls deciding what goes on which page, and still ends up sending a vague "we still need content" message. The full account and its limits are in the brand position; this brief does not repeat them.

**Who it's for.** First: students and freelancers who build a site from someone else's material a few times a year. They are reachable (our interviews came from them), their projects are small enough to finish in a week, and their pain is concrete. Freelance designers and small studios are the second audience; they have the same handoff more often, and the Reddit research shows them already running questionnaire-and-rewrite workflows. We are not claiming studio demand yet.

**Core flow.** User: the builder. Action: hands ClientReady the agreed page list plus the document and images they were sent. Value: within a day they get back a *content pack organized by page* — each paragraph placed under a page and section with the original text kept beside it, each image attached to the section it supports, and a short, worded list of the decisions only the content owner can make. The aha moment is opening that pack and seeing that the thing they dreaded sorting is already sorted, and that the one message they need to send is written for them.

## MVP features

- Homepage and four landing pages, one per audience and value prop, each with a working email signup and analytics (live now).
- A **request form**: page list, pasted document text or an uploaded file, and an image folder link. Submitting it is the "first try" action.
- A **content pack** returned by email as one shared document: page → section → draft text, source text, assigned image, status (*draft to review* / *missing* / *needs a decision*).
- An **open-decisions list** at the top of the pack, written as sentences a builder can forward to the content owner unchanged.
- A **24-hour turnaround promise** for the first five requests, stated on the request form.

## What comes later

1. **Self-serve sorting in the browser.** The user pastes and sees placement immediately instead of waiting a day. Matters because turnaround is the obvious reason not to use a human-in-the-loop service twice.
2. **Section briefs before anyone writes** (the `/section-brief` promise). Matters because CR02's problem is uneven contribution, and a brief prevents it rather than repairing it.
3. **Contributor answer links without an account.** Matters because CR01 and the Reddit threads both say another login is a barrier; silence must still never count as approval.
4. **Status view per page** (the `/needs-a-decision` promise) with "waiting on whom" in words. Matters for coordinators who run the same event page repeatedly.
5. **Reusable page templates per builder** (Home/About/Services/Contact sets). Matters for freelancers running the same handoff monthly.
6. **Export to a CMS or Markdown.** Matters once the builder actually assembles the site from the pack.

## What's cut and what's faked

**Cut for now:** accounts and login; a dashboard; collaborative editing; reminders or any feature that implies we can make someone reply; AI-written copy that invents business facts; payments; a native app; anything B2B-sales shaped.

**Faked (Wizard of Oz):** the sorting itself. For the first requests, Handong produces the pack by hand with an AI assistant: read the document, map paragraphs to the agreed pages, pick the image per section, write the open-decisions list, and send it as a shared Google Doc within 24 hours. Builder time, contributor time and our own preparation time are logged for each pack, and we note the corrections the builder makes to our placement. This is the test from the [ClientReady vs. Strata brief](../hw4-synthesis-brand-position/idea_comparison.md): test the workflow before building the software, and measure both sides' effort.

Also faked: the "24-hour" turnaround is a person checking the inbox, not a queue, and the thank-you page's invitation to email one line about your project goes to a forwarded address that Handong reads by hand.

## Stack and services

| Part | Choice | Cost |
|---|---|---|
| Pages | Static HTML rendered from templates by a small Node script (`npm run export`); one hand-written stylesheet on the HW4 palette, with Newsreader and Inter from Google Fonts; no framework | $0 |
| Coding agent | Claude (Anthropic) for the pages, copy checks and this brief, working from `docs/brand_position.md` and `docs/style_guide.md`; Codex was used for the HW4 research tooling | Existing subscription |
| Hosting | Cloudflare Pages, deploys from the GitHub repo on push | $0 (free tier) |
| Domain | `clientready.cc` at Cloudflare Registrar | about $10/year |
| Email signup | Formspree form `xbggrvoo`; submissions email Handong and sit in the Formspree inbox; hidden fields carry page and UTM values | $0 (free tier, 50 submissions/month; $10/month if we pass that) |
| Thank-you page and signup event | `/thanks` fires `gtag('event','signup')`; marked as a key event once GA4 lists the event (up to 24 hours after the first hit) | $0 |
| Analytics | Google Analytics 4, tag on every page | $0 |
| Content pack delivery (Wizard of Oz) | Google Docs shared link, sent from `hello@clientready.cc`, which Cloudflare Email Routing forwards to Handong's Gmail | $0 |
| AI model for sorting assistance | Claude via the desktop app during the faked phase; when self-serve sorting is built, an API call per pack | $0 now; estimated under $0.10 per pack later |
| Later: request storage and uploads | Cloudflare Workers + D1 for request records, R2 for images; Resend for sending packs | $0 on free tiers at this volume |

Nothing on the list requires a credit card today except the domain, which is paid.

## How you'll know it works

**The action we measure:** email signups, by landing page, with the `signup` key event in GA4 and the page/UTM fields in each Formspree email. Second action, once the request form is live: **a real document submitted** for a pack.

**Keep going if, by the November 6 class (two weeks of traffic):**
- at least 25 signups across the five pages, with one page taking 40% or more of them — that page becomes the product's front door and the roadmap's first self-serve feature;
- at least 3 people submit real material, and at least 2 of them use the returned pack in an actual site and tell us what they had to fix.

**Stop or change direction if:** signups spread evenly and thin (no value prop pulls), or people sign up but nobody sends material (the pain is real but not worth a day's wait — build self-serve or drop it), or builders receive the pack and still rebuild the placement from scratch (our sorting adds nothing over their own).

## Risks and open questions

- **One person.** Building, writing packs by hand and driving traffic are three jobs. The mitigation is the Wizard of Oz scope: no code beyond the pages until the signup data says which page to build for.
- **A shared doc may already be enough.** CR02 said so, and the pages say so back. If the pack is only a tidier Google Doc, people won't come back. The test is whether builders reuse the open-decisions list and the placement, not whether they liked receiving it.
- **Nonresponse is not our problem to solve, and users may expect it to be.** The pages state the limit; the pack must never mark anything approved because a file arrived.
- **Contributor effort may just move.** If the builder saves an hour and the contributor spends one answering our questions, nothing was gained. Logging both sides' time per pack is the only way to know.
- **Content Snare and similar tools already do sectioned requests.** Our bet is on the output (a page-ready pack from existing material) rather than on another intake form. Unproven.
- **Open questions:** Which of the four audiences signs up? Will anyone send a real document to a stranger's form? What does "usable" mean to a builder — do they want draft copy, or only placement and the question list? Is 24 hours fast enough for a student with a deadline tonight?

## Roles

Stark Labs is Handong He alone from this homework on, so the plan names one person for everything and says what gets dropped if time runs out.

| Who | Builds | Owns |
|---|---|---|
| **Handong He** | Pages, request form, content packs by hand, analytics setup, this brief and the demand plan | Traffic every week (see [demand strategy](../hw6-demand-plan-and-analytics/demand_strategy.md)); replying to every signup within a day; logging times and corrections per pack |

If a week is short, the order of what gets dropped is: new features first, then blog posts, never the weekly Reddit replies or the pack turnaround. Traffic and packs are the experiment; the code is not.
