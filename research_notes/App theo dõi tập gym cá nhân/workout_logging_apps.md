# Workout-logging apps for individual gym-goers: Hevy, Strong, JEFIT (plus Gymshark Training)

Research date: 2026-10-16. Most sources are third-party review/comparison articles from 2026 and App Store listings. Several of the comparison sites (sensai.fit, setgraph.app, jefit.com/blog) are competitors writing about rivals, so treat their opinions with caution. Their pricing figures agree with the App Store listings. Hevy's help centre (help.hevyapp.com) returned HTTP 403 to direct fetches, so Hevy help-centre content below comes from search-result snippets and a third-party summary. I could not reach Strong's help centre (help.strongapp.io) at all.

## 1. Data model: routine/template vs workout vs exercise vs set

### Takeaway
All three use the same hierarchy: Routine/Template (optionally in folders) → Exercises (from a library plus custom exercises) → Sets. A logged Workout is an instance of a routine that can diverge from it. Each set has a set type (warm-up / normal / drop / failure) and optional RPE. Supersets group exercises together. Notes attach at the exercise level. The free tiers cap the number of routines and custom exercises rather than logging itself.

### Cited Findings
- Hevy set types: warm-up, normal, drop set, failure. RPE uses a 6-10 scale and is available on the free tier. Supersets are unlimited and work as circuits. There is a 150-set limit per workout, even on Pro. — [aitoolsbakery Hevy review, Sep 2026](https://aitoolsbakery.com/?p=18424)
- The Hevy App Store listing mentions set types (warmup, normal, drop sets, failure, supersets), RPE, routine folders, PRs, 1RM, a plate calculator and widgets. — [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
- Hevy can share folders of routines — [Hevy feature page](https://www.hevyapp.com/features/share-folders-routines/)
- Hevy "supports supersets, drop sets, and rest-pause logging natively in the workout flow". Strong tags sets as warm-up, drop set or failure and supports supersets. Sources say both apps offer RPE/RIR fields that can be switched on per set "on paid tiers". This conflicts with aitoolsbakery, which says Hevy's RPE is free. — [sensai Hevy vs Strong, Jul 2026](https://www.sensai.fit/blog/hevy-vs-strong-2026)
- Strong lets you tag sets as warm-up, failure or drop sets, and has an auto countdown timer — [search summary of Strong listing](https://apps.apple.com/mx/app/id464254577)
- The Strong App Store listing lists supersets, RPE logging, workout notes, progress photos, CSV export, a plate calculator, a warm-up calculator and PR/1RM features — [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
- Custom exercises:
  - Hevy free tier allows only 7 custom exercises. Pro is unlimited. — [aitoolsbakery](https://aitoolsbakery.com/?p=18424); [sensai pricing](https://www.sensai.fit/blog/fitness-app-pricing-free-tier-comparison)
  - Strong has about 200 preset exercises and unlimited custom exercises — [sensai comparison, May 2026](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- Exercise library size:
  - JEFIT: 1,400+ exercises
  - Hevy: about 400
  - Strong: 200+
  - Source: [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- JEFIT's App Store summary mentions supersets, set tagging (warm-up, working, drop, failure), RPE, rest timer/stopwatch and recall of previous workout values — [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-planner-gym-log/id449810000)
- Gymshark Training has 700+ exercises and 450+ free workouts and plans. You can build your own workouts and plans and record 1RMs and sets. — [Gymshark search results / Gymshark blog](https://www.gymshark.com/blog/article/the-gymshark-training-app-for-ios-and-android)

### Inferences
- The industry-standard model is Folder → Routine → RoutineExercise (ordered, with superset group, notes, rest time) → planned sets (type, target weight/reps) → Workout (dated instance) → logged sets (weight, reps, type, RPE, completed flag).
- I did not find target rep ranges (e.g. "8-12") documented as a first-class field in Hevy or Strong in the sources I could reach. The rep-range check in Hevy Trainer suggests Hevy stores ranges at least for its Trainer programs.

### Gaps
- I could not confirm from primary docs whether Hevy and Strong store a rep range (min-max) per set in a template. Hevy's help centre was blocked (403).
- I found no primary source on RIR versus RPE in Strong.
- JEFIT's "RPE tagging" wording in the App Store summary was mixed together with set types, so the exact field set is unclear.

## 2. Set-logging UX: taps, previous values, checkmark, rest timer, watch, offline, routine changes mid-workout

### Takeaway
Fast loggers converge on one pattern:
- A table row per set: Set # | PREVIOUS (e.g. "45kg x 9") | weight | reps | checkmark.
- Tapping the previous value copies it into the row.
- Tapping the checkmark confirms the set and auto-starts the rest timer.
- Lock-screen live activity, a watch app and a plate calculator are optional extras.

Logging a repeated set takes about 1-2 taps. Hevy asks "Update Routine / Keep Original" only after structural changes, not after weight or rep changes.

### Cited Findings
- **Hevy previous column:** "your previous performance appears on the left side under the column labeled PREVIOUS". You can "tap on a previous value to instantly add it to your current workout". It shows weight and reps, e.g. "45kg x 9". — [Hevy feature page](https://www.hevyapp.com/features/track-exercises/)
- **Hevy previous-value source:** under Settings > Workout > Previous Workout Values you choose either "the last time you did that exercise regardless of the routine" or the last time within the current routine — [Hevy feature page](https://www.hevyapp.com/features/track-exercises/)
- This setting only changes the "previous" column. It does not change the weight/reps input columns. — [Hevy help: Previous Workout Values (search snippet)](https://help.hevyapp.com/hc/en-us/articles/34105442929943)
- **Hevy workout settings:**
  - rest timer
  - warm-up calculator (PRO), with a "Warmup Method" option for adding and removing warm-up sets
  - plate calculator
  - "Smart Superset Scrolling"
  - Source: [Hevy help: Workout Settings (search snippet)](https://help.hevyapp.com/hc/en-us/articles/33882110558743)
- **Hevy routine update prompt:** if you reorder exercises, or add or remove exercises or sets during a workout started from a routine, you choose "Update Routine" or "Keep Original Routine" at the end. "It will not appear for changes to reps or weight". Those are "saved automatically based on the routine settings and your previous values". — [Hevy help: Update Routine vs Keep Original (search snippet)](https://help.hevyapp.com/hc/en-us/articles/38387296276375-Update-Routine-vs-Keep-Original-Routine)
- **Hevy rest timer and devices:**
  - Rest timer is automatic — [aitoolsbakery](https://aitoolsbakery.com/?p=18424)
  - Lock-screen live activity, widgets, Apple Watch with live sync — [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
  - Wear OS support (Galaxy Watch 4+). No Garmin: "Garmin has rejected Hevy's application for access to their API". — [aitoolsbakery](https://aitoolsbakery.com/?p=18424)
- **Speed comparison:** both apps are "within a tap or two of each other on a single straight set", and both auto-fill from previous sessions. Strong's watch app lets you "log entire sessions without ever picking up your phone". With Hevy's watch app, "most users still pull out the phone for serious lifts". — [sensai Hevy vs Strong](https://www.sensai.fit/blog/hevy-vs-strong-2026)
- Strong is described as "the fastest plain log", with "two-tap set logging" — [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- Reddit users in r/weightroom and r/powerlifting reportedly default to Strong because it is the fastest for logging sets mid-workout — [setgraph Hevy vs Strong 2026](https://setgraph.app/ai-blog/hevy-vs-strong-app-comparison-2026) (aggregator from a competitor, not direct Reddit quotes)
- **Strong features:** rest timer with auto countdown, plate calculator, warm-up calculator, Apple Watch app with real-time sync, home-screen widgets — [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
- In Strong reviews, the plate calculator is "limited to known, common bar weights" — [Strong App Store reviews](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577?see-all=reviews)
- **JEFIT:** rest timers, stopwatch, previous-value retrieval, Apple Watch with live sync, widgets — [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-planner-gym-log/id449810000)
  - The watch app is listed as an Elite (paid) feature — [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)

### Inferences
- For the "lazy tracker" user, the key interactions are:
  - (a) show last session's weight x reps inline per set;
  - (b) one tap copies it, or prefill the inputs directly;
  - (c) one tap confirms and starts the rest timer.
  Hevy's setting distinguishes "previous" (display) from input prefill. A simpler design could prefill inputs with last values so that confirming is a single tap.
- Hevy auto-saves weight/rep changes and asks only about structural changes. That is a good low-friction default worth copying.

### Gaps
- I found no authoritative source on offline behaviour for any of the three apps (whether workouts log offline and sync later). The search snippets did not cover it.
- I could not confirm Strong's exact template-update behaviour after a workout from Strong's own docs. One snippet about "template update settings in the Finish Workout sheet" was not clearly from Strong, so I excluded it.
- I found no documented exact tap counts. "Two-tap" is a reviewer's characterisation.

## 3. Progressive overload support (PRs, e1RM, suggestions, graphs)

### Takeaway
All three track PRs and estimated 1RM and show per-exercise graphs. Strong and the Hevy free tier leave progression decisions to the user. Hevy Pro's "Hevy Trainer" (launched Feb 2026) auto-bumps weight when you hit the top of the rep range. JEFIT positions itself on deep analytics behind its Elite tier.

### Cited Findings
- **Hevy:** PR tracking, 1RM calculation, "tons of graphs" (review quote) — [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
  - The free tier keeps graph history for only 3 months. Pro unlocks unlimited history. — [sensai pricing](https://www.sensai.fit/blog/fitness-app-pricing-free-tier-comparison); [aitoolsbakery](https://aitoolsbakery.com/?p=18424)
- **Hevy Trainer** (Pro, launched Feb 2026) "auto-adjusts your working weights based on logged performance". It checks whether you "hit the upper end of the prescribed rep range" and bumps the load. — [sensai Hevy vs Strong](https://www.sensai.fit/blog/hevy-vs-strong-2026); [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- **Strong:** "No programming engine. You build templates, you log against them, you decide when to add weight". Its 1RM tracker is described as "dialed". — [sensai Hevy vs Strong](https://www.sensai.fit/blog/hevy-vs-strong-2026)
  - The App Store lists PRs and 1RM calculations — [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
- **JEFIT:** "best analytics", including body-part volume tracking, 1RM projections and advanced graphs, mostly in Elite — [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- **Hevy complaint:** bodyweight exercises do not add to total volume — [Hevy App Store review](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)

### Inferences
- A "beat last time" nudge is the simplest progressive-overload aid. An example rule: if all sets hit the top of an 8-12 range, suggest +2.5 kg. It matches what Hevy Trainer charges for, and nothing in Strong's free tier does it.

### Gaps
- I found no primary source for which 1RM formula each app uses (Epley, Brzycki, etc.).

## 4. Pricing & monetization (2025-2026)

### Takeaway
Hevy is the cheapest, and its free tier allows unlimited logging. Strong caps the free tier at 3 routines. JEFIT is ad-supported and has the most expensive subscription. Gymshark Training is free and acts as a brand-marketing tool.

### Cited Findings
- **Hevy**
  - Free: unlimited workouts, 4 routines, 7 custom exercises, 3 months of graph history, no ads
  - Pro: $2.99/mo (the App Store shows $2.99-$3.99), $23.99/yr, $74.99 lifetime
  - Pro adds Hevy Trainer and advanced measurements
  - No Family Sharing. Import is from Strong CSV only, one import allowed.
  - Sources: [sensai pricing](https://www.sensai.fit/blog/fitness-app-pricing-free-tier-comparison); [aitoolsbakery](https://aitoolsbakery.com/?p=18424); [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
- **Strong**
  - Free: unlimited workouts, 3 custom routines, CSV export
  - PRO: $4.99/mo, $29.99/yr, $99.99 lifetime
  - The App Store shows ranges of $3.99-$4.99/mo, $19.99-$29.99/yr and $79.99-$99.99 lifetime, which are likely regional or legacy SKUs. A 6-month plan at $19.99 also appears.
  - Sources: [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577); [sensai Hevy vs Strong](https://www.sensai.fit/blog/hevy-vs-strong-2026)
- **JEFIT**
  - Free: ad-supported, full 1,400+ exercise library, logging, community routines
  - Elite: $12.99/mo or $69.99/yr. Removes ads and adds expert plans, advanced analytics, the watch app and video demos.
  - Sources: [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-planner-gym-log/id449810000); [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- **Gymshark Training:** described as 100% free with no ads. One listing says "free with ads", so the sources conflict. — [Gymshark blog](https://www.gymshark.com/blog/article/the-gymshark-training-app-for-ios-and-android); [appshunter](https://appshunter.io/ios/app/1139151320)

### Inferences
- The common pattern is a limit on routines and custom exercises, plus a time limit on history and analytics, while logging stays unlimited. A notebook user with 3-5 split days (e.g. Push/Pull/Legs/Upper/Lower) hits Strong's 3-routine cap immediately, which is a known friction point.

### Gaps
- I did not research pricing in Vietnam (VND).

## 5. User praise and complaints

### Takeaway
Users praise speed, simplicity and graphs (Hevy and Strong both rate 4.9 on iOS). Complaints centre on paywalls (Strong's 3-routine cap), missing integrations (Hevy/Garmin), JEFIT's dated UI, ads and update churn, and small gaps such as bodyweight volume and custom bar weights.

### Cited Findings
- **App Store ratings:**
  - Hevy: 4.9 from about 98k ratings — [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
  - Strong: 4.9 from 109k+ — [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
  - JEFIT: 4.8 from about 47k — [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-planner-gym-log/id449810000)
- **Strong complaints:**
  - paywall on routine creation, with users wanting à la carte pricing
  - cannot log past workouts or merge sessions
  - plate calculator limited to common bars
  - no calorie estimate
  - Source: [Strong App Store reviews](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577?see-all=reviews)
- **Hevy complaints:**
  - bodyweight exercises add no volume — [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
  - the Discover/social feed on Home cannot be removed; no Garmin; 150-set cap — [aitoolsbakery citing Hevy help centre](https://aitoolsbakery.com/?p=18424)
- **JEFIT:**
  - "Interface feels like 2015 in places" — [sensai comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
  - frequent updates that complicate navigation; bugs with video playback and graphs — [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-planner-gym-log/id449810000)
- **Reddit sentiment** (via aggregators): r/fitness general threads favour Hevy for its generous free tier. r/weightroom and r/powerlifting favour Strong for raw speed. — [setgraph Hevy vs Strong 2026](https://setgraph.app/ai-blog/hevy-vs-strong-app-comparison-2026); [sensai](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)

### Inferences
- The social feed being forced onto Home is a friction point for "lazy trackers" who just want to log. A logger-first home screen is a differentiator.

### Gaps
- I did not fetch Reddit threads directly. The Reddit sentiment above comes from competitor-written aggregator articles, so it should be validated against primary r/Hevy and r/fitness threads.
- I found no concrete evidence of sync-failure complaints in the sources I reached.

## 6. Vietnamese language / exercise names

### Takeaway
None of the three apps is confirmed to support Vietnamese. JEFIT definitely does not. Hevy's 16-language list does not include it. Vietnamese exercise names are effectively unserved by these apps.

### Cited Findings
- **Hevy** App Store languages: English, Arabic, Catalan, French, German, Hindi, Italian, Japanese, Korean, Polish, Portuguese, Russian, Simplified Chinese, Spanish, Traditional Chinese and Turkish. Vietnamese is not in that list. The fetch tool's summary claimed "Vietnamese is included", which contradicts the list it returned, so I treat that claim as erroneous. — [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
- Hevy added 5 new languages in September 2026 — [aitoolsbakery](https://aitoolsbakery.com/?p=18424)
- **JEFIT** languages: English, French, German, Italian, Simplified Chinese, Spanish. No Vietnamese. — [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-planner-gym-log/id449810000)
- **Strong** supports "English plus 10 additional languages" — [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
  - A second fetch claimed Vietnamese, but it appears to have read the App Store website's own language-picker footer. Unreliable.

### Inferences
- A Vietnamese-first logger is a clear gap. It needs Vietnamese UI plus bilingual exercise names (e.g. "Đẩy ngực nằm ghế phẳng / Bench Press") and search that tolerates missing diacritics.

### Gaps
- I could not verify Strong's exact language list or the 5 languages Hevy added in September 2026. Check the App Store listings in the VN storefront directly.
