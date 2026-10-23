# CallIt MVP

## 1. What we are building

CallIt is for existing friend groups that make recurring predictions and want a shared record of the original terms, answers, and results. The first useful moment is joining a friend's group and seeing a call that can be answered in seconds.

The audience and promise are defined in the [brand position](../hw4-synthesis-brand-position/brand_position.md). The [interview synthesis](../hw4-synthesis-brand-position/synthesis_comparison.md) compares GP-01 through GP-06. [Liam's interview](../hw3-interviews/group-points/interview-1/notes.md) describes searching Discord for old picks; [Ethan's interview](../hw3-interviews/group-points/interview-3/notes.md) describes the recurring effort of collecting picks. These findings support testing established groups with repeated calls.

Core flow:

1. A manager creates a private group and shares an invitation link.
2. Members create accounts or sign in, join, and view the call.
3. The manager publishes a question with 2 to 6 choices, a closing time, and clear terms.
4. Each member answers once before closing. Submitted answers and published terms stay fixed.
5. After closing, the manager checks the agreed result source and records the result.
6. Members return to see who called it and the group's record of correct answers.

## 2. MVP features

- Email/password accounts with a unique username.
- Private groups, invitation links, and manager/member roles.
- Calls with 2 to 6 answer choices, written terms, a closing time, and an optional result source.
- One answer per member, hidden from other members until closing.
- Manager-recorded results and a correct-answer scoreboard.
- Comments and a history of resolved calls.

## 3. What comes later

Possible next steps, in evaluation order:

1. Reminders, if pilot groups need help returning to an open call or its result.
2. A review process for disputed results, if manual resolution prevents groups from continuing.
3. Broader scoring, if repeat groups need more than the correct-answer record.
4. Public groups and a native mobile app, if demand extends beyond private groups using the web app.

These are future options, not features included in the core pilot.

## 4. What is cut and what is manual

The shortest pilot flow excludes automated notifications, dispute voting, public groups, payment processing, and a native mobile app. The wider app has optional room tokens and a settlement ledger; these are outside the core pilot flow. Any settlement happens outside CallIt.

A person recruits each pilot group and helps members join. The group manager checks the agreed source and enters the outcome manually. Reminders and feedback use the group's existing chat. A call with incorrect published terms must be cancelled and posted again. These manual steps avoid building automation before the pilot establishes a need.

## 5. Stack, services, and costs

The application uses Next.js. The marketing pages use Vite and a Node.js signup service. Codex and Claude Code are the coding agents. Caddy serves both sites over HTTPS.

Project costs recorded as of October 23, 2026:

| Service | Use | Project cost |
|---|---|---|
| DigitalOcean | Application and marketing-page hosting | USD 6/month planning baseline; final invoiced charges are not yet reconciled |
| Cloudflare | Domain registration and DNS for call-it.app | USD 8.20 initial domain purchase; renewal price is not yet established |
| Supabase | Authentication, Postgres database, and file storage | USD 0 on the current Free plan |
| Resend | Account email and waitlist welcome email | USD 0 on the current Free plan |
| Google Analytics 4 | Page, source, and signup measurement | USD 0 |
| GitHub | Source hosting and collaboration | USD 0 recorded |
| Pexels | Marketing-page media | USD 0 |
| Caddy | HTTPS and web serving | USD 0 software cost |
| Codex and Claude Code | Development assistance | Existing developer accounts; a separate project subscription cost is not recorded |

There is no production AI-model inference service or payment-processing integration in the core MVP. Founder time is not priced. Free-plan limits and future service upgrades can change the budget.

## 6. How we will know it works

The primary measure is non-team account creations in recruited groups. Keep this separate from email-waitlist signups.

A promising pilot result is that people create accounts, answer a call, return for its result, and voluntarily start another call. Seeing this behavior across more than one group would support continued development. If accounts are created but members do not answer or return, revise the first-call experience before expanding acquisition. The numeric continuation threshold remains an open evaluation question.

## 7. Risks and open questions

- Some groups may prefer chat and screenshots to another application.
- A small pilot may not predict continued use.
- Manager-entered results depend on clear terms and a trusted result source.
- The process for disputed results and a numeric continuation threshold still need to be defined.
- Final hosting charges, domain renewal pricing, and usage growth can change costs.

## 8. Roles

| Person | Responsibility |
|---|---|
| Yuval Gerber | Builds the app and landing pages; owns database integration, hosting, and analytics |
| Elad Tisch | Owns product decisions and the product demonstration |
| Aviv Pinto | Owns social content, group outreach, product identity, and interface design with Yuval |
| Shiyu Zhou (Emily) | Owns weekly traffic, community participation, blog planning, and pilot feedback |
| Zhangcheng (Charles) | Owns MVP planning, integration, requirements review, project budget, and homework submission |
