# Stark Labs — Homework 5: MVP doc, homepage and landing pages

**Team:** Stark Labs — Handong He (`hh3152`). One-person team from this homework on (Mansi Rank moved to The Babysitters).
**Date:** October 23, 2026
**Product:** ClientReady — know what belongs on each page.
**Product repository:** [Anzdon1/clientready](https://github.com/Anzdon1/clientready) (pages, templates, deploy notes)
**MVP brief:** [mvp_doc.md](mvp_doc.md)

All pages are live on `clientready.cc`, hosted on Cloudflare Pages and deployed from the product repository.

## Pages

| Page | URL | Audience | Value prop |
|---|---|---|---|
| Homepage | [clientready.cc](https://clientready.cc/) | Anyone building a small website from someone else's material | **Know what belongs on each page.** Sorts the text and images you were sent by page and section and keeps the open decisions visible. |
| Landing 1 | [clientready.cc/long-document](https://clientready.cc/long-document) | A student or friend building a site from "one long document and a bunch of images" (CR05) | **Start from what they sent.** Each paragraph placed, each image assigned, and a short list of the choices only they can make. |
| Landing 2 | [clientready.cc/section-brief](https://clientready.cc/section-brief) | Someone assembling a group's writing into one site (CR02) | **Tell everyone what each section needs before they write.** A page-by-page brief that lives in the shared doc you already use. |
| Landing 3 | [clientready.cc/needs-a-decision](https://clientready.cc/needs-a-decision) | A club or event page coordinator (CR01) | **See what is still missing and who it is waiting on.** Status in words, not colors; it won't make anyone reply faster, and says so. |
| Landing 4 | [clientready.cc/freelancers](https://clientready.cc/freelancers) | Freelance web designers and small studios (r/web_design, r/freelance) | **Turn questionnaire answers and a folder into a page-by-page content pack.** Their words beside your draft; the rewrite is still yours. |
| Thank-you | [clientready.cc/thanks](https://clientready.cc/thanks) | After a signup | Confirms the request and fires the `signup` analytics event. Opening the URL directly also fires it, so test visits are excluded when counting. |
| Privacy | [clientready.cc/privacy](https://clientready.cc/privacy) | — | What the site collects and why. |

Every page, the homepage included, has one action: the early-access email form. Submissions go through Formspree to Handong's inbox with hidden fields for the page and the UTM values of the arriving link, then redirect to `/thanks?from=<page>`. The signup was tested end to end on October 23 from the `/long-document` page: the submission appeared in the Formspree inbox with `page=long-document` and the test UTM fields, the notification email arrived, and the browser was sent to `/thanks`, where the `signup` event fired.

## Look

The pages apply the HW4 [style guide](../hw4-synthesis-brand-position/style_guide.md) and the selected "Aligned sheets" [logo set](../hw4-synthesis-brand-position/logo/README.md): cream ground, ink text, terracotta reserved for the one action, flat colors, no photography. Two changes from the HW4 preview, both recorded in the product repository: headings moved from Georgia to Newsreader and body text from Arial to Inter (Google Fonts, with the originals as fallbacks), and the hero now shows a page plan drawn as two sheets settling into alignment, the same idea as the logo mark. The sample project ("the campus journal") is written by us and the footer says so. No icon library was adopted; the style guide reserves that decision until there is UI that needs one.

## Copy sources

Landing-page headlines and quotes use the words of the people they are for:

- CR05 (long document and images), CR02 (what each section needs; the shared doc already works), CR01 (seeing what's missing doesn't make anyone reply) — from our [interview notes](../hw3-interviews/analysis.md), translated from Chinese and labeled as translations on the pages.
- r/web_design (questionnaire then rewrite) and r/freelance (collection tools "just seemed to add time") — from the [Reddit research](../hw4-synthesis-brand-position/reddit_research/reddit_research_summary.md), quoted verbatim and dated.

Per the brand position, the pages make no claims about response rates, time saved, customers or shipping dates.

## Analytics

Google Analytics 4 (`G-VZ595XF2ME`) is on every page, and `/thanks` fires the `signup` event that is marked as the key event. Setup details, the UTM convention and the weekly checks are in [Homework 6](../hw6-demand-plan-and-analytics/demand_strategy.md).
