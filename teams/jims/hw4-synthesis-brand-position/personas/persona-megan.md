# Persona agents

Five synthetic judge personas for Team Jims. Each one is grounded in our interviews (Jude, Zaynah,
Jackson, Yung Yi) and the Reddit research in `../reddit_research/`. Every Reddit quote is verbatim
with its link. Interview quotes from Jackson and Yung Yi are copied from the transcripts. Quotes from
Jude and Zaynah were lightly cleaned from the transcripts (filler words removed).

| Agent | Who | Grounded mainly in | What they judge hardest |
|---|---|---|---|
| persona-layla | International grad student signing from abroad | Jude, Yung Yi (guarantor), r/NYCapartments 1upyc2j, r/AskNYC 1qnk8lm | Unit-specific truth from abroad, true monthly cost, guarantor fit, sources |
| persona-megan | Domestic out-of-state grad student, two weekends to tour | Zaynah, r/NYCapartments 1s0qkkr, 1pzxari, 1s2we9l | Speed, cutting listing noise, saved trips, no extra admin |
| persona-hana | International sublet seeker who was scammed once | Yung Yi, r/NYCapartments 1o1n4hp | Visible proof behind "safe," money protection, no fees, short stays |
| persona-tyler | Near-local student, low stress (contrast persona) | Jackson, r/AskNYC 1qnk8lm, r/NYCapartments 1rowe4d | Resident voices, neighborhood truth, free, two minutes or nothing |
| persona-marcus | Young professional relocating for a job, one weekend | r/NYCapartments 1wlp7k2, 1rofkxp, 1t9lmoa | Fast red flags with sources, fee legality, one-time price, document privacy |

The contradictions in our interviews show up here as different personas. Megan wants more speed,
while Hana wants a forced pause. Layla and Hana need guarantor-free paths, while Tyler and Marcus
never hit that problem. Tyler would never pay, while Marcus would pay once.

## Install

Copy the `persona-*.md` files into `.claude/agents/` in the product repo. Claude Code picks them up
as subagents named `persona-layla`, `persona-megan`, and so on.

## Use

Ask Claude Code to run the persona agents on an artifact, for example: "Run persona-layla,
persona-megan, persona-hana, persona-tyler, and persona-marcus on docs/brand_position.md." Each
returns one verdict JSON (verdict, score, unclear, must_fix, nice_to_have, in-character reaction,
would_flip_me, would_pay).

## Round 1: what each persona said about the JIMS draft

Tested Oct 8, 2026 against `brand_position.md` (Oct 7 JIMS listing-alert draft, before the SettleWise pivot). Each persona ran as its own agent,
separately from the others. Full verdicts are in `test_results/`.

| Persona | Verdict | Score |
|---|---|---|
| Layla | approve with conditions | 5 |
| Megan | approve with conditions | 6 |
| Hana | approve with conditions | 6 |
| Tyler | reject | 4 |
| Marcus | reject | 4 |

**Layla (international, signing from abroad), 5/10.** She trusts the honest tone and likes that we
don't use "verified." But alerts don't solve her problem, which is finding out about pests, heat
and surprise fees after she signs. She wants matching on "accepts third-party guarantor," a
"budget" that means the true monthly cost, and labeled sources on each alert.

**Megan (out-of-state, two weekends to tour), 6/10.** She loves "a clear match, not another tab"
and having one place that watches every site. She pushes back on the "calm, at your own pace"
tone, because in her market speed wins. She wants each alert to tell her if a place is worth a
trip, by flagging AI photos, fake room counts and already-rented units. She also wants a shortlist
that replaces her spreadsheet.

**Hana (short-term sublet, scammed before), 6/10.** She is the most positive about our honesty:
"An alert is a lead, not a guarantee" is the sentence she wishes the site that scammed her had
said. Her conditions are that we say JIMS covers 4-8 month sublets and student boards, and that we
state the money model (no fees or ID before she confirms a place). She flags "before the listing
disappears" as the same pressure that got her scammed.

**Tyler (near-local, low stress), 4/10, reject.** To him it reads as "StreetEasy alerts but
nicer." What he wanted was to hear from people who live in the building. There's nothing for a
renter who has already found a place, and no way for him to give back.

**Marcus (job mover, one weekend), 4/10, reject.** A watch that runs for weeks doesn't fit someone
who signs in 72 hours. He wants a sourced building-history check he can use while touring, an
"is this fee legal?" answer, and a one-time price. "Keep watch" sounds to him like a subscription.

### What this tells us

1. **All five caught the same gap in the document.** The "Core insight" says the main pain is
   not knowing what a place is really like before committing. The positioning statement only
   promises listing alerts. Each persona raised this from a different angle, so it's a problem
   with the brand position itself, not a sign that the personas are too similar.
2. **They disagree on what should fill that gap.** Layla wants guarantor fit and true cost. Megan
   wants a worth-a-trip read on each listing. Hana wants sublet coverage and a clear money model.
   Tyler wants resident notes. Marcus wants a building check and fee-legality answers he can use
   on the spot.
3. **Shared conflict with our own values.** Megan, Hana and Layla all flag
   "Before the listing disappears" as urgency that contradicts "User interest over pressure."
4. **Price is missing from the document.** Hana, Tyler and Marcus all asked what it costs,
   and Marcus specifically won't take a subscription for a one-time move.
5. **What every persona liked:** the honesty rules (no "verified," "an alert is a lead, not a
   guarantee," and labeling what the listing claims versus what's confirmed). Keep these.

## Round 2: re-test on the SettleWise brand position (Oct 23, 2026)

We ran all five personas again on the current `brand_position.md` (SettleWise, Oct 8). The only change to the persona files was the product name, JIMS → SettleWise. Each persona ran as its own agent and didn't see the round 1 results. Full verdicts are in `test_results/persona-*_settlewise_2026-10-23.json`, and the full write-up is in `test_results/settlewise_retest_2026-10-23.md`.

| Persona | Round 1 (JIMS) | Round 2 (SettleWise) |
|---|---|---|
| Layla | 5, approve with conditions | 6, approve with conditions |
| Megan | 6, approve with conditions | 6, approve with conditions |
| Hana | 6, approve with conditions | 6, approve with conditions |
| Tyler | 4, reject | 5, approve with conditions |
| Marcus | 4, reject | 6, approve with conditions |

### What changed

1. **The gap all five personas caught in round 1 is closed.** The core insight and the positioning now match. Nobody said "it's just alerts" again, and the source labels (listing claim, renter note, public record, unverified) were singled out as the most reassuring part.
2. **No more urgency conflict.** "Before the listing disappears" is gone, and no persona flagged pressure this time.
3. **Both rejects moved up to conditional approval** (Tyler 4→5, Marcus 4→6). The average went from 5.0 to 5.8.
4. **New tension:** Megan reads "calm, relief" as slow. Fixing urgency for Hana and Layla created a speed concern for her.
5. **Still open:** each persona wants its own situation named in the brand. Layla wants remote signers, true cost and guarantor fit. Hana wants sublets and short stays. Tyler wants resident notes and the block. Marcus wants fee and deposit norms and decisions made within days. Megan wants misleading listings flagged. Price and document handling are still unanswered.

