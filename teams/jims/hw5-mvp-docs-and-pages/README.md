# HW5: MVP Doc, Homepage, and Landing Pages — Team Jims (SettleWise)

**Product:** SettleWise, an apartment comparison workspace for NYC renters. *Know before you settle.*
**Product repo:** [github.com/JIMS-CU/Settlewise](https://github.com/JIMS-CU/Settlewise) (pages live in `src/app/(marketing)/`)
**MVP doc:** [mvp_doc.md](mvp_doc.md)

## Live pages

| Page | URL | Audience | Value prop | Traffic owner |
|---|---|---|---|---|
| Homepage | https://settlewise.group/ | NYC renters who have already found a few apartments and feel stuck comparing them | Your apartment listings in one place, so you can compare with less stress. *Know before you settle.* | Jorim Chua |
| Landing page 1 | https://settlewise.group/for-parents | Parents and guarantors of students and newcomers renting in NYC, often in another state or country | The guarantor carries the risk. See the apartments they're considering side by side, and what's still unknown, before anyone signs. | Izum Adnan |
| Landing page 2 | https://settlewise.group/compare-apartments | Renters juggling several open listings ("Five apartments. Fifteen tabs. Zero clarity.") | Bring your options together, compare what matters to you, and see the trade-offs without juggling endless tabs. | Maria Aezah |
| Landing page 3 | https://settlewise.group/students-on-a-budget | Students renting in NYC on a tight budget and tighter schedule | Compare rent, broker fees and commute side by side, and see what each listing leaves out. | Sami Qian |

## The action on every page

Every page has one action: **Get started** → create a SettleWise account (`/signup`, email and password). The parents and students pages take the email right on the page and carry it into the sign-up form.

- **Where sign-ups land:** Firebase Console → Authentication → Users lists every account email with its sign-up date. The whole team can see it there.
- **Signups by page:** Google Analytics (GA4, `G-WC3ZKCLK0C`) runs on all marketing pages and `/signup`, so we compare landing page → `/signup` → `/dashboard` paths for each page.
- **How we test it:** create an account from each page's Get started button on the live site, then check the email appears under Firebase → Authentication → Users.

## Look and feel

All pages use the HW4 style guide, logo and icon set: [style guide](../hw4-synthesis-brand-position/style_guide.md), [logo](../hw4-synthesis-brand-position/logo/), [brand position](../hw4-synthesis-brand-position/brand_position.md). Copy on each landing page uses our interview and Reddit language ([interviews](../hw3-interviews/Housing/), [Reddit research](../hw4-synthesis-brand-position/reddit_research/)).
