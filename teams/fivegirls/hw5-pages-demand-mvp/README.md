# HW5 — Restroom Ready

**Team:** Five Girls

**Updated:** October 23, 2026

**Product:** [Restroom Ready](https://nyc.imfinethanku.me/)

**Development repository:** [imnotmomo/nyc-restroom](https://github.com/imnotmomo/nyc-restroom)

Restroom Ready helps NYC residents and visitors choose a restroom before making the trip. The October 23 presentation uses the native iPhone app, built with SwiftUI and MapKit. Internal TestFlight **1.0 (7)** is **Testing** in the existing **4995** and **Team** groups; there is no public TestFlight link or App Store release. The public web finder remains the presentation backup. Both clients use the same Firebase accounts and community records alongside a dated city directory; a listing does not establish current availability or complete NYC coverage.

The website also retains the four marketing pages, email signup flow and separate sample demo submitted for HW5.

## Native MVP and demo

The app supports anonymous map/list browsing, search, walking directions and independent **Clean, Accessible, Stair Free, Public and Elevator access** filters. Selected options combine with AND; Clear filters restores unrestricted discovery. Search uses a scrollable Liquid Glass dropdown over the map, with inline empty results. **Account** contains Saved and Add restroom. Google Sign-in protects saves, private notes, ratings, passcode contributions, new locations and public visit reports. The interface uses native system fonts, iOS 26 Liquid Glass with earlier-iOS fallbacks, and a minimum deployment target of iOS 18.

The demo follows **Joslyn, an illustrative woman using a wheelchair on Fifth Avenue: map → Accessible + Stair Free → Peninsula → check reported hours, entrance and route → Directions**. Peninsula's contributor reports 24/7 restroom hours, step-free doors right of the main entrance, and the Penthouse elevator to the 23rd floor with 0 stairs after entry. Entry permission and observation date remain unknown. For a hypothetical return visit, show the five-star cleanliness control in **Details & reports**, then bookmark the place and open **Account → Saved**. Sign in with Google if needed; publish a rating only for an actual personal visit.

Build 7 adds Stair Free and structured access details, retaining the compact card, rating fixes, Map/List crossfade and fitted filter sheet. All **31 native model tests** passed, the Firebase-linked simulator build succeeded, and the focused Peninsula workflow passed in **46.197 seconds**. Both existing TestFlight groups are enabled without changing tester membership. Device installation, genuine signed-in contributions and physical presentation rehearsal remain separate checks.

## Public pages

| Page | URL | Purpose |
| --- | --- | --- |
| Homepage | [nyc.imfinethanku.me](https://nyc.imfinethanku.me/) | Introduce the product and collect emails. |
| Conditions | [Conditions](https://nyc.imfinethanku.me/conditions/) | Test interest in knowing usable basics before walking over. |
| Entry and route | [Entry and route](https://nyc.imfinethanku.me/entry-route/) | Test interest in permission, floors, stairs, and the route inside. |
| Dated reports | [Dated reports](https://nyc.imfinethanku.me/dated-reports/) | Test interest in sources, dates, and visible unknowns. |
| Interactive demo | [Try the demo](https://nyc.imfinethanku.me/demo/) | Separate sample page, outside the native presentation workflow. Changes are simulated and reset on reload. |
| Thank-you | [Thank-you](https://nyc.imfinethanku.me/thank-you/) | Confirm a successful email signup. Opening this URL alone does not count as a signup. |
| Privacy | [Privacy](https://nyc.imfinethanku.me/privacy/) | Explain waitlist, account, contribution, and Analytics data. |

The full [finder](https://nyc.imfinethanku.me/find/) opens without a shared passcode or account. Google Sign-in is required for account-owned saves and contributions.

## Submission files

- [Demand strategy](demand_strategy.md): audiences, named owners, campaign links, Facebook and X outreach, the published blog, and measurement.
- [MVP document](mvp_doc.md): core flow, shipped scope, cuts, stack, responsibilities, and the October 23 demo.

## Analytics and learning

Google Analytics measurement ID **`G-YJG2N05KY9`** covers the public website and finder on the team domain. Actual web page visits were observed in Realtime. The current **`sign_up` key event** means first-time Firebase Google account creation; returning logins and legacy waitlist submissions do not count. Historical `generate_lead` data remains separate. The iPhone integration is prepared but requires a new compiled/uploaded build; **installed build 1.0 (7) has no Analytics**. Demo page visits are tracked, but simulated demo actions do not send action events. QA visits are not customer demand. See [HW6 Analytics verification](../hw6-demand-plan-and-analytics/analytics.md).

The [October 23 HW6 verification](../hw6-demand-plan-and-analytics/analytics.md) includes the team's seven-day Analytics screenshots and current tag checks. Pageviews use approved routes and lowercase UTM labels. Emails, Firebase account IDs, private notes, search text, and precise coordinates are excluded. Automatic outbound and form tracking is disabled. The product repository records the [actual setup and verification](https://github.com/imnotmomo/nyc-restroom/blob/main/docs/features/google-analytics.md).

**Analytics Academy:** enrolled in Google's current [Google Analytics Certification (2026) learning path](https://skillshop.docebosaas.com/learn/courses/18609/google-analytics-certification-2026). The older standalone 101 and 102 links supplied by Google's Help page returned “Access denied” after sign-in. The current path contains the matching introductory sections:

- **101 topic:** Get Started Using Google Analytics (GA). Its first activity, “Understand Google Analytics and Its Role in Business Growth,” was opened and Skillshop confirmed it was started on October 16.
- **102 topic:** Manage GA Data and Learn to read reports. Its first activity, “Navigate Your Google Analytics Account,” was opened in the training player on October 16.

These are course starts, not course completion or certification.

## Remaining submission steps

Real credited NYC photographs have been added to all four marketing pages; sources, photograph dates, and CC BY 4.0 credits are visible.

The current three-placement plan is the New York&People Facebook group, the published X post, and the published Medium article. Record the Facebook permalink and actual landing-page link to finish documenting the three placements. The Reddit research communities remain documented in the demand strategy, together with the observed submission outcomes and the change in distribution. The combined team PR also includes the [HW6 semester demand plan](../hw6-demand-plan-and-analytics/demand_strategy.md) and [Analytics verification](../hw6-demand-plan-and-analytics/analytics.md). For HW6, the PR itself is the submission; nothing additional is submitted on CourseWorks.

For October 23, the current midterm rubric gives each team **7.5 minutes presenting and 7.5 minutes Q&A**; every teammate must attend and speak. Prepare title/one-liner, team names and headshots, research-grounded problem and audience, solution, and at least one working live workflow. Rehearse together on the presenting iPhone, test the classroom projector and screen mirroring, and keep the web finder and a recording as backups. The [MVP document](mvp_doc.md) records the current scope and responsibilities. Check CourseWorks for any separate deck-upload instructions.
