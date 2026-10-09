# Manual Reddit HTML Collection

**Completed and checked October 9, 2026:** The team manually saved 35 Reddit HTML pages: 12 searches, 20 discussion threads, and three quoted-comment pages. **34 are usable.** The “bathroom outdated” search has no results and is excluded from that count. This meets the guide’s 30–100-file target.

The originals remain in `reddit_corpus/browser/`. Byte-identical copies with the filenames below are in `reddit_corpus/raw/`, following the course layout. All five selected quotes, their authors, and context match the saved HTML. The [collection manifest](collection_manifest.json) records file mappings, hashes, and counts.

The two style-reference HTML files in `browser/` and the earlier failed browser attempts are excluded from the research count. All raw HTML remains local and ignored by Git. These are saved HTML pages, not Reddit JSON exports or complete copies of every collapsed reply.

## Method used and checks

1. Open a link and wait until its results or post and comments are visible.
2. Save the page with your browser’s Save As command, using `.html` and the listed filename. Select HTML/page source rather than a PDF or screenshot. On macOS, use Command-S.
3. Reopen the saved file and check that its result list or post/comment text is readable. A blocked/login page, empty results, truncated source, or duplicate does not count as a usable save.
4. Save the three comment permalinks too, so R3–R5 include the quoted reply, author, and surrounding context. Expand relevant collapsed replies before saving when necessary.
5. Keep raw files local. Any additional saves need the same readable-text and quote checks before the final count changes.

The submitted files remain the [thread list](thread_list.md), [research summary](research_summary.md), and [selected quotes](selected_quotes.md). The [course research README](https://github.com/kenxle/columbia-startup-studio-fall-2026/tree/main/classes/20261002_c4w4_fri_synthesis-and-brand-position/exercise/reddit-research) describes the collection rounds and HTML fallback.

## Search pages

| Page | Save as |
| --- | --- |
| [AskNYC: public bathrooms](https://old.reddit.com/r/AskNYC/search/?q=public%20bathrooms&restrict_sr=on&sort=relevance&t=all) | `search_01_asknyc_public_bathrooms.html` |
| [AskNYC: clean bathroom](https://old.reddit.com/r/AskNYC/search/?q=clean%20bathroom&restrict_sr=on&sort=relevance&t=all) | `search_02_asknyc_clean_bathroom.html` |
| [AskNYC: bathroom map](https://old.reddit.com/r/AskNYC/search/?q=bathroom%20map&restrict_sr=on&sort=relevance&t=all) | `search_03_asknyc_bathroom_map.html` |
| [nyc: bathroom outdated — empty, excluded](https://old.reddit.com/r/nyc/search/?q=bathroom%20outdated&restrict_sr=on&sort=relevance&t=all) | `search_04_nyc_bathroom_outdated.html` |
| [AskNYC: bathroom locked](https://old.reddit.com/r/AskNYC/search/?q=bathroom%20locked&restrict_sr=on&sort=relevance&t=all) | `search_05_asknyc_bathroom_locked.html` |
| [AskNYC: bathroom purchase](https://old.reddit.com/r/AskNYC/search/?q=bathroom%20purchase&restrict_sr=on&sort=relevance&t=all) | `search_06_asknyc_bathroom_purchase.html` |
| [AskNYC: restroom stairs](https://old.reddit.com/r/AskNYC/search/?q=restroom%20stairs&restrict_sr=on&sort=relevance&t=all) | `search_07_asknyc_restroom_stairs.html` |
| [nyc: bathroom luggage](https://old.reddit.com/r/nyc/search/?q=bathroom%20luggage&restrict_sr=on&sort=relevance&t=all) | `search_08_nyc_bathroom_luggage.html` |
| [AskNYC: restroom floor](https://old.reddit.com/r/AskNYC/search/?q=restroom%20floor&restrict_sr=on&sort=relevance&t=all) | `search_09_asknyc_restroom_floor.html` |
| [AskNYC: bathroom hotel key](https://old.reddit.com/r/AskNYC/search/?q=bathroom%20hotel%20key&restrict_sr=on&sort=relevance&t=all) | `search_10_asknyc_bathroom_hotel_key.html` |
| [AskNYC: bathroom reliable](https://old.reddit.com/r/AskNYC/search/?q=bathroom%20reliable&restrict_sr=on&sort=relevance&t=all) | `search_11_asknyc_bathroom_reliable.html` |
| [nyc: public restroom](https://old.reddit.com/r/nyc/search/?q=public%20restroom&restrict_sr=on&sort=relevance&t=all) | `search_12_nyc_public_restroom.html` |

## Discussion threads

| Page | Save as |
| --- | --- |
| [T01 — Where are all the decent public restrooms in this city?](https://old.reddit.com/r/AskNYC/comments/1vp3cve/where_are_all_the_decent_public_restrooms_in_this/) | `thread_01_1vp3cve.html` |
| [T02 — Ok, weird question, but what are some nice and clean bathrooms or what are some businesses where I can purchase something or get some food grab and go that have a bathroom for customer use - around the perimeter of Manhattan?](https://old.reddit.com/r/AskNYC/comments/1nv77hi/ok_weird_question_but_what_are_some_nice_and/) | `thread_02_1nv77hi.html` |
| [T03 — Where’s the cleanest (relative) public restroom in Manhattan?](https://old.reddit.com/r/AskNYC/comments/wxq7nl/wheres_the_cleanest_relative_public_restroom_in/) | `thread_03_wxq7nl.html` |
| [T04 — Nicest public bathroom](https://old.reddit.com/r/AskNYC/comments/1urbs88/nicest_public_bathroom/) | `thread_04_1urbs88.html` |
| [T05 — Public bathrooms in NYC](https://old.reddit.com/r/AskNYC/comments/1tc14ro/public_bathrooms_in_nyc/) | `thread_05_1tc14ro.html` |
| [T06 — Where is your go-to bathroom spot in busy Manhattan](https://old.reddit.com/r/AskNYC/comments/14a7o4u/where_is_your_goto_bathroom_spot_in_busy_manhattan/) | `thread_06_14a7o4u.html` |
| [T07 — Places in NYC with reliable bathrooms?](https://old.reddit.com/r/AskNYC/comments/kf8fwk/places_in_nyc_with_reliable_bathrooms/) | `thread_07_kf8fwk.html` |
| [T08 — How do people find public restrooms in NYC?](https://old.reddit.com/r/AskNYC/comments/102s6md/how_do_people_find_public_restrooms_in_nyc/) | `thread_08_102s6md.html` |
| [T09 — Investigation of NYC park bathrooms finds alarming rate of litter, missing locks and unsanitary conditions](https://old.reddit.com/r/nyc/comments/1f9stab/investigation_of_nyc_park_bathrooms_finds/) | `thread_09_1f9stab.html` |
| [T10 — Is there an app that shows where to go when you got to go?](https://old.reddit.com/r/AskNYC/comments/192gaah/) | `thread_10_192gaah.html` |
| [T11 — A new Google Maps layer shows public restrooms in NYC](https://old.reddit.com/r/nyc/comments/1d82vmv/) | `thread_11_1d82vmv.html` |
| [T12 — Is Got2Go still going?](https://old.reddit.com/r/AskNYC/comments/1stifh0/) | `thread_12_1stifh0.html` |
| [T13 — Finding public restrooms in NYC](https://old.reddit.com/r/AskNYC/comments/1gdxitl/) | `thread_13_1gdxitl.html` |
| [T14 — Crowd-sourced map of restrooms (with door codes) in NYC](https://old.reddit.com/r/nyc/comments/18cdkg1/) | `thread_14_18cdkg1.html` |
| [T15 — Access to public park restrooms should be a basic human right, and the city is failing in this regard](https://old.reddit.com/r/nyc/comments/10r1fqo/) | `thread_15_10r1fqo.html` |
| [T16 — Super odd question, but... where are the restrooms in NYC?](https://old.reddit.com/r/AskNYC/comments/1ft63mc/) | `thread_16_1ft63mc.html` |
| [T17 — What NYC lifehack was worse than expected?](https://old.reddit.com/r/AskNYC/comments/reusvf/) | `thread_17_reusvf.html` |
| [T18 — Urgent! Where can you go to the bathroom at Times Square?](https://old.reddit.com/r/AskNYC/comments/vabcpz/) | `thread_18_vabcpz.html` |
| [T19 — Do you think NYC is an accessible city?](https://old.reddit.com/r/AskNYC/comments/14jqol3/) | `thread_19_14jqol3.html` |
| [T20 — Quiet or private public bathroom options](https://old.reddit.com/r/AskNYC/comments/exzlbo/) | `thread_20_exzlbo.html` |

## Quoted comments

| Page | Save as |
| --- | --- |
| [R3 — conflicting Starbucks advice](https://old.reddit.com/r/AskNYC/comments/192gaah/comment/kh25iyx/?context=3) | `quote_R3_192gaah_kh25iyx.html` |
| [R4 — suitcase and hotel refusal](https://old.reddit.com/r/AskNYC/comments/reusvf/comment/hoczy9n/?context=3) | `quote_R4_reusvf_hoczy9n.html` |
| [R5 — stairs inside restaurants](https://old.reddit.com/r/AskNYC/comments/14jqol3/comment/jpqyn9d/?context=3) | `quote_R5_14jqol3_jpqyn9d.html` |

## Finish check

- [x] At least 30 usable pages, excluding empty, blocked, truncated, and duplicate saves.
- [x] R1–R5 match the saved post/comment wording, authors, permalinks, and context.
- [x] The summary and thread list match the saved sources and final count.
- [x] Raw files remain ignored and local.
