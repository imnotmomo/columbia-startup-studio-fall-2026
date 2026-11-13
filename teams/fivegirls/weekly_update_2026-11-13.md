# Weekly Update: Restroom Ready (Five Girls), November 13, 2026

#### Accountability: what we did

- **Build:** Made Apple or Google sign-in required to use the finder on both the iPhone app and website. Users must check the agreement box to accept the Terms and acknowledge Privacy and data use before continuing. Agreement versions and acceptance times are stored privately in Firebase. Returning users can restore their accepted account session. We prioritized this account flow and measurement reliability over adding more features.
- **Grow:** Expanded our presence in neighborhood groups and continued sharing the [public TestFlight beta](https://testflight.apple.com/join/PxWSpdJ8) and [website](https://nyc.imfinethanku.me/find/). We focused on local communities to reach people who could use the app around NYC. Our focus is getting people through signup and into a restroom card, then checking which outreach brings people who complete that flow.
- **Analyze:** Connected website and iPhone activity to Google Analytics. Both track `sign_up` for a genuinely new Apple or Google account and `restroom_open` when someone opens a restroom card. Returning logins and preloaded map data do not count as new signups or card openings. The iPhone app also tracks major interactions such as searches, filters, saves and ratings. We now report the signup-to-card-open funnel separately from TestFlight downloads and Firebase account totals.
- **Analyze:** Published the count-only API at **https://nyc.imfinethanku.me/api/user-count**. It reads the Google Analytics funnel and returns signup users, completed users, completion rate, and iOS and web breakdowns. We improved handling of temporary Google API failures and checked its output against a fresh Analytics query.
- **Research:** Started researching what would motivate visitors to create an account. Requiring signup and agreement acceptance before people can try the service has become our main onboarding concern. We are looking at how to explain the app's value earlier and give people a clearer reason to sign up.

**Progress as of November 13, 11:39 AM EST:** For October 10–November 13, Google Analytics and our API both reported **43 signup users** and **34 users who signed up and then opened a restroom card**, a **79.1% completion rate**. The platform breakdown was **32 iOS** and **2 web** completions. These are GA-measured users and may include team and test activity.

**API response format:** The endpoint returns aggregate JSON without account identities. `user_count` is the number of users who completed the signup-to-card-open funnel, and `signup_users` is the number who reached the signup step. The response also includes platform counts, the reporting window and processing-delay indicators. This response was checked on November 13 at 11:46 AM EST:

```json
{
  "user_count": 34,
  "signup_users": 43,
  "completion_rate": 0.7906976744186046,
  "ios_user_count": 32,
  "web_user_count": 2,
  "source": "google_analytics",
  "definition": "closed_sign_up_then_restroom_open",
  "reportingIdentity": "BLENDED",
  "dateRange": {
    "startDate": "2026-10-10",
    "endDate": "2026-11-13"
  },
  "reportingTimeZone": "Etc/GMT+4",
  "asOf": "2026-11-13T16:46:20.091Z",
  "approximate": true,
  "dataDelayPossible": true,
  "includesPartialToday": true
}
```

#### Planning: what we're doing next

- **Build:** Simplify the signup and agreement flow and make the benefits of an account clearer, including saving useful restrooms and contributing ratings and notes. We prioritized this because visitors encounter the signup requirement before they can try the finder.
- **Grow:** Continue neighborhood-group outreach and share the website and TestFlight link with people who live in or travel to NYC. Use campaign links to compare which channels bring completed signup-to-card-open users.
- **Analyze:** Review the journey from arriving at the site to signing up and opening a restroom card. Check tracking coverage before and after the signup change so we can separate changes in measured traffic from people leaving during onboarding.
- **Research:** Talk with potential users and test the signup flow with people outside the team. Find out what makes them hesitate and which benefits give them a stronger reason to create an account.

#### Issues

- Requiring signup and agreement acceptance before using the service has created a barrier for visitors. Our earlier GA Realtime readings showed more than 400 active users in a 30-minute window, while recent readings have dropped to single digits after the change. We are researching how to give visitors a stronger reason to sign up. The current signup-to-card-open funnel starts at completed signup, so it does not show visitors who leave before creating an account.
- Google Analytics processing can delay new activity. The API refreshes on the first request after its five-minute cache expires, so it is not a Realtime counter.
