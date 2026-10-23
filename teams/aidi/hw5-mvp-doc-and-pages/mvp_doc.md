# Aplovia MVP Product Brief

**Team:** AIDI  
**Product:** Aplovia  
**MVP scope:** Tasks 0–4, completed as of October 2026

## 1. What We Are Building

Aplovia is a bilingual college-research product for international high-school students applying for first-year admission to U.S. undergraduate programs. We are starting with students who lack experienced family or counselor support and do not know how to turn scattered college information into a trustworthy, personally relevant starting point.

These students can usually find rankings, admissions statistics, and university websites. Their harder problem is deciding which facts are current and credible, connecting those facts to their own preferences and family budget, and narrowing a large universe of colleges into options worth investigating. Our research showed that trust, visible sources, and personal relevance matter more than producing another long list quickly. The supporting evidence is documented in our [interview findings](../hw3-interviews/README.md), [research synthesis](../hw4-synthesis-brand-position/synthesis_comparison.md), and [brand position](../hw4-synthesis-brand-position/brand_position.md).

### Core flow

| User | Action | Value |
| --- | --- | --- |
| An international student who does not know where to begin | Enters background and college preferences, browses available colleges, explicitly applies selected hard filters, and opens a college detail page with official sources | Replaces scattered research with a smaller, relevant set of colleges and a clear way to verify the information before making a decision |

The MVP's first **aha moment** occurs when a student applies their own criteria, sees the college list narrow, opens a result, and can verify an important fact through its official source. The product is a transparent starting point for the student's research, not an unquestionable authority and not an admissions guarantee.

## 2. MVP Features

- **Bilingual application shell:** Provides English and Simplified Chinese navigation among Background & Preferences, Find Colleges, and the future My College List area.
- **Background & Preferences:** Lets students enter or revise academic background, testing plans, maximum annual family contribution, and college preferences without blocking access to the rest of the product.
- **Session-only student state:** Keeps student inputs in the current React application memory and clears them when the page is refreshed, closed, or left.
- **College directory:** Lets students browse published colleges, search by college name, sort by U.S. News National Universities rank with alphabetical tie-breaking, and move through results in pages of up to 20 colleges.
- **Standardized college cards:** Presents comparable school facts in a consistent format so students do not have to reconstruct the same categories across unrelated websites.
- **College detail pages:** Organizes a school's current selection information, application information, costs, and other available facts into a single research view.
- **Source transparency:** Shows official source links and last-checked dates in the relevant detail-page sections so consequential information remains verifiable.
- **Explicit hard filters:** Lets students choose which valid preferences to activate and returns every published college that satisfies all active requirements without silently relaxing them.
- **Clear empty states:** Explains when no college in the current dataset meets every selected requirement rather than inventing or loosening a match.
- **Validated pilot dataset:** Uses five manually researched schools to validate the complete data model, import, review, publication, browsing, detail, and filtering workflows before expanding coverage.

## 3. What Comes Later

The following work is ordered by the value and dependencies it adds after the current MVP:

1. **Target-user testing and data improvement:** Observe international students using the current flow, fix the highest-friction points, and confirm that source-linked filtering creates a useful starting point before adding more product complexity.
2. **Broader verified college coverage:** Expand toward the U.S. News National Universities top 100 so more students can find meaningful results while preserving the same source and validation standards.
3. **Explainable Recommendations and Reach/Match/Safety estimates:** Use GPA, SAT or ACT information, historical CDS evidence, preferences, and financial constraints to offer a balanced starting list without claiming a precise admission probability.
4. **My College List and application planning:** Let students keep one working list and view each college's application rounds, required tasks, and deadlines so research can turn into action.
5. **Accounts and secure persistence:** Add authentication only when cross-visit continuity provides enough value to justify the added security, privacy, and support burden.
6. **Application-material workspace:** Allow students to organize research notes, drafts, and other preparation materials after accounts, authorization, retention, deletion, and document-security rules have been designed.
7. **Production deployment and product analytics:** Deploy the product for broader use and instrument only the minimum consented events needed to understand activation, retention, and failure points.
8. **Homepage and landing-page reintegration:** Update the demand pages after product testing establishes which value proposition and workflow deserve to lead the public website.

## 4. What Is Cut and What Is Faked

### Cut from this MVP

The current MVP does not include Recommendations, Reach/Match/Safety results, a functional My College List, application-task management, accounts, sign-in, persistent student profiles, saved documents, reminders, calendars, payments, majors, B2B counselor or school accounts, runtime AI, automatic web scraping, or a complete top-100 dataset. These are absent rather than simulated. Navigation may reserve space for later workflows, but it must not present unfinished business functionality as available.

The MVP also does not store GPA, test scores, budget, preferences, or results in `localStorage`, `sessionStorage`, cookies, PostgreSQL, or analytics. A student can browse without finishing Background & Preferences, and leaving or refreshing the application clears the temporary inputs.

### Wizard of Oz operations

College-data operations are the MVP's faked, or Wizard of Oz, layer. Team members manually locate official 2025–2026 Common Data Sets and current official sources, extract relevant facts, normalize them into Aplovia's schema, review their accuracy, and publish approved records. A structured import and validation pipeline supports this work, but source discovery, interpretation, and approval are not automated.

The user-facing college facts, source links, detail pages, and filter calculations are real. Only the behind-the-scenes collection and maintenance workflow is performed manually. This lets us test whether students value trustworthy, comparable information before investing in a scalable data operation.

## 5. Stack and Services

Costs below describe the project's current incremental cost, not promotional list prices or future production estimates.

| Layer or service | Current use | Current incremental cost |
| --- | --- | --- |
| React 19, TypeScript, React Router 8, and Vite | Bilingual frontend, routing, interface state, and builds | $0; open-source software |
| Python 3.14, Django 5.2 LTS, and Django REST Framework | Versioned REST API, school data, publication rules, browsing, and filtering | $0; open-source software |
| PostgreSQL 18 and psycopg 3 | Relational school database | $0 in local development |
| OpenAPI with drf-spectacular | API contract and schema | $0; open-source software |
| pytest, Vitest, Testing Library, and Playwright | Backend, component, and end-to-end verification | $0; open-source software |
| OpenAI Codex | Coding agent used during development; it is not part of the product runtime | No separate project charge; used through existing team access |
| GitHub | Source control and team collaboration | $0 incremental project cost on the current plan |
| Railway | Approved target for the Django API and PostgreSQL production services; not yet provisioned | $0 currently; production cost to be confirmed before deployment |
| Frontend production hosting | Not yet selected or provisioned | $0 currently; provider and cost remain open |
| Cloudflare Worker and D1 | Existing marketing-site waitlist only; separate from the MVP product database | No incremental MVP product cost recorded |
| Official public data sources | CDS files, official college pages, NCES/IPEDS, federal Clery data, and verified ranking information | $0 access cost; manual research time is the material cost |
| Sign-in, transactional email, payments, product analytics, and runtime AI | Not used in the current MVP | $0 |

The codebase is a monorepo organized as a modular monolith with vertical feature slices. The frontend calls versioned `/api/v1/` REST endpoints; Django owns school facts and filter rules so business logic is not duplicated in the browser. Railway remains the approved backend and database target, while frontend hosting and production analytics remain open decisions.

## 6. How We Will Know It Works

Our primary activation action is the complete evidence-backed filtering loop: a target student enters at least one meaningful preference, activates and applies a filter, opens a returned college detail page, and locates an official source for an important fact.

We will keep developing this direction if **at least four of five target international-student testers complete that loop without assistance** and can explain why at least one returned college satisfies the criteria they selected. During this first test, the team will observe completion directly and record where users hesitate; no personal academic, financial, or preference data will be sent to analytics.

This threshold tests the MVP's actual promise: not simply whether a page loads, but whether a student can move from uncertainty to a narrower, understandable, and verifiable research path.

## 7. Risks and Open Questions

- **Limited coverage:** Five schools can validate the workflow but cannot yet produce a useful result for every combination of preferences.
- **Manual data cost:** Source discovery, normalization, review, and updates may become the main scaling constraint as coverage grows.
- **Freshness and comparability:** Colleges publish information on different schedules and in different formats, so visible source and last-checked dates must remain part of the product.
- **Zero-result filters:** Strict hard filters protect the meaning of a student's requirements but may produce no matches, especially in a small dataset.
- **Financial interpretation:** Published cost of attendance is not the same as a family's eventual net cost, and international aid outcomes cannot be promised.
- **Trust and usefulness:** Interview evidence supports the problem, but we still need to observe whether students use source links and consider the filtered list a better starting point than their existing process.
- **Recommendation validity:** Historical score distributions can support future categories, but the team has not yet validated decision-tree thresholds or how to communicate uncertainty responsibly.
- **Privacy and security:** Accounts and document storage would create materially higher obligations for authentication, access control, retention, deletion, and incident response.
- **Production choices:** Frontend hosting, product analytics, operating cost, and backup and recovery procedures must be resolved before public deployment.

## 8. Roles

| Responsibility | Owner(s) |
| --- | --- |
| Product and MVP Scope | Edison Hon |
| Frontend and UX | Edison Hon and Chengyiwei Fu |
| School Data | Jonah Smith |
| Decision Tree | Edison Hon |
| Backend and Deployment | Edison Hon and Chengyiwei Fu |
| QA and Data Validation | Jonah Smith |
| Demand, Analytics, and Traffic | Edison Hon and Jonah Smith |

The named owner is responsible for decisions and review within that area even when another teammate contributes implementation work. Edison Hon and Jonah Smith jointly own traffic: Edison owns product-facing demand experiments and conversion paths, while Jonah owns research-informed outreach, data validation feedback, and measurement support.
