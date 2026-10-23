# ZeroOne: Homework 5

CallIt gives private friend groups a shared record of their predictions and results. Its promise is: "Being right is better when your group remembers."

## Public pages

| Page | Audience | Main value | URL |
|---|---|---|---|
| Homepage | Friend groups that make predictions together | Keep the call, answers, and result in one shared record | [call-it.app](https://call-it.app/) |
| Friends landing page | Friends making everyday predictions | Remember who called it without searching old messages | [Friends](https://call-it.app/for/friends) |
| Sports landing page | Recurring sports groups | Collect everyone's picks in one place | [Sports](https://call-it.app/for/sports) |
| Agreements landing page | Groups making predictions that stay open for weeks | Preserve the original terms until the result is known | [Agreements](https://call-it.app/for/agreements) |

Each page offers the same email signup. A successful signup leads to the [thank-you page](https://call-it.app/thanks).

The homepage, three landing pages, and thank-you page returned HTTP 200 on October 23, 2026. A real signup on October 16 confirmed that the address is saved. A browser check on October 22 confirmed that all four pages load the Google tag and that the thank-you page sends one signup event, with none on reload. Welcome-email sending has been accepted by the email provider; recipient inbox placement has not been verified.

## Product and design

- [MVP document](mvp_doc.md): scope, features, manual steps, services, costs, success measures, risks, and roles.
- [Brand position](../hw4-synthesis-brand-position/brand_position.md) and [style guide](../hw4-synthesis-brand-position/style_guide.md): the visual and language system used on the pages.
