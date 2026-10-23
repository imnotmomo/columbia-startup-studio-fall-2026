# Black Panthers Updated Homework 5 - Additional Pages

## Team

- Hunter Doradea
- Catherine Escobar
- Abraham Alemu
- Eldad Tolla
- Jaden Hinton

## Three distinct landing pages

We attest that Plandit has three separate, publicly accessible landing pages at three distinct
URLs. Each page speaks to a different user and planning problem while directing visitors to the
same early-access waitlist.

| Landing page | Primary audience | Message being tested | Public URL |
|---|---|---|---|
| Primary Plandit page | Students such as Sofia who have many saved places but rarely turn them into plans | Turn scattered saves into a ready-to-go day that fits the student's time, budget, and distance | [https://www.plandit.app/](https://www.plandit.app/) |
| Group plans page | Group organizers such as Amara who are tired of group-chat indecision | Turn the group's ideas into one concrete, budget-visible plan with a start time, ordered stops, and route | [https://www.plandit.app/group-plans](https://www.plandit.app/group-plans) |
| Free window page | Time-constrained students such as Marcus who have only a few free hours | Start with an exact time window and distance limit, then build a nearby plan with stops that remain open | [https://www.plandit.app/free-window](https://www.plandit.app/free-window) |

These are not three links to sections of one page. They are three independently addressable
landing pages with different headlines, supporting copy, examples, audience objections, and
conversion paths.

## Page-by-page differences

### 1. Primary page: saved places into a real day

The primary page leads with **“Your saves deserve to become a real day.”** It represents
Plandit's core positioning: students already have places they want to visit, but need help turning
those places into a practical plan. The page demonstrates collecting saved places, setting time
and budget constraints, ordering stops, and following the route.

### 2. Group plans: end the back-and-forth

The group page leads with **“Send the plan. Not another question.”** It speaks to the friend who
normally carries the planning work. The page emphasizes:

- Bringing the group's existing ideas into one plan.
- Showing expected cost before everyone commits.
- Replacing another open-ended poll with a start time, ordered stops, and route.
- Sharing the finished plan with everyone in Plandit.

The page states the current product constraint clearly: everyone in a shared plan will need the
Plandit app at launch.

### 3. Free window: make limited time count

The free-window page leads with **“Three free hours. Make them count.”** It speaks to students
whose primary constraint is time rather than a large backlog of saved places. The page emphasizes:

- Starting with the exact free-time window.
- Keeping stops nearby so travel does not consume the available time.
- Starting from saved places or adding nearby options.
- Confirming that example stops remain open during the selected window.

## Conversion and measurement

Each persona-specific page includes two email signup opportunities:

1. A primary email CTA in the hero.
2. A second email CTA after the page has explained the value proposition.

All signup forms use the same live Formspree waitlist, but submit the page source and form location
so results can be compared. GA4 records successful signups and errors by landing page and CTA
location. Vercel Web Analytics provides page-level traffic for the three URLs.

This setup lets us compare:

- Visits to each audience-specific page.
- Hero versus closing-form conversion.
- Waitlist signup rates for the primary, group-planning, and short-window messages.

## Verification

On October 23, 2026, we verified that all three public URLs returned successful HTTP `200`
responses:

- `https://www.plandit.app/`
- `https://www.plandit.app/group-plans`
- `https://www.plandit.app/free-window`
