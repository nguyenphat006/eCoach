# Programs, Phases and Automatic Progression in Gym Apps (Boostcamp, Liftosaur, Fitbod, Hevy/Strong, RP, Alpha Progression, JuggernautAI, MacroFactor Workouts)

Researched 2026-10-16. Note: many comparison pages are written by competitors (Boostcamp "vs" pages, sensai.fit, alphaprogression.com blog), so they are flagged where used. Several help-center pages (Hevy) returned 403 and could not be read directly.

## 1. How is a program structured, and how do users switch programs/phases (is history kept)?

### Takeaway
There are three distinct models: (a) **flat routine lists** (Hevy, Strong): templates grouped in folders, with no weeks and no progression engine; (b) **multi-week programs** (Boostcamp, Liftosaur, Alpha Progression, RP): program, then weeks/blocks (mesocycles), then days, exercises and sets, with progression rules attached; (c) **no program at all** (Fitbod): each session is generated on demand. Every app keeps one continuous workout history that does not depend on which program is active. Switching programs means changing the active plan, and logged sessions stay in place.

### Cited Findings
- **Liftosaur** programs are plain text in "Liftoscript": `# Week 1` marks a week, `## Day 1` marks a day, and each exercise sits on its own line with sets and reps, e.g. `Squat / 5x5 / progress: lp(5lb)`. Loads can be % (`80%`), absolute (`60kg`) or RPE (`@8`). Rep ranges (`3x8-12`) and mixed set schemes (`1x5 @8, 1x3 @9, 1x1 @10`) are supported — [Liftosaur Liftoscript docs](https://www.liftosaur.com/docs/liftoscript)
- Liftosaur avoids repetition across weeks with `Bench Press[1-4] / 3x8` (applies to weeks 1–4), lets one exercise reuse another's sets (`Squat / ...Bench Press`), and supports unused "template" exercises (`T1 / used: none / ...`) — [Liftoscript docs](https://www.liftosaur.com/docs/liftoscript)
- Liftosaur supports "12+ week programs with automatic template replication across multiple weeks" and ships built-in programs (5/3/1 for Beginners, GZCLP and GZCL variants, Metallicadpa PPL, Starting Strength, Texas Method, Strong Curves) — [liftosaur.com](https://liftosaur.com/)
- Liftosaur: "you can switch programs at any time", and workout history stays tracked and viewable — [Liftosaur overview blog](https://www.liftosaur.com/blog/posts/liftosaur-overview/)
- Liftosaur also offers a REST API and an MCP server, so AI assistants (Claude/ChatGPT) can "create programs, log workouts, and analyze training" — [Liftosaur docs](https://www.liftosaur.com/docs)
- **Boostcamp**: a library of "11,000+ programs" (including user-made ones) plus ~130+ coach-designed programs. "Each program is a multi-week plan with its own progression and deload rules built in" — [Boostcamp /best/budget](https://www.boostcamp.app/best/budget) (vendor page)
- Boostcamp keeps "one training history when you move between goals": "a lifter who moves from a hypertrophy block into a strength cycle does not need a second app" — [Boostcamp vs RP](https://www.boostcamp.app/vs/rp-hypertrophy) (vendor page)
- Boostcamp Pro includes a personalized program builder that generates "a starter periodization plan from a goal/schedule/equipment questionnaire" which the user can then edit — [Boostcamp vs RP](https://www.boostcamp.app/vs/rp-hypertrophy)
- **Hevy**: "A gym routine on Hevy is a workout you create once and use as many times as you want." Routines are grouped in folders, which "allows you to log workouts more easily, switch between programs, and change your training style as your goals change." A "program" is effectively a folder of routines. Hevy has a library of 26 pre-built programs — [Hevy gym routines](https://www.hevyapp.com/features/gym-routines/); [Hevy help (search snippet; page returned 403)](https://help.hevyapp.com/hc/en-us/articles/34953606698903-Build-a-Workout-Program-Create-Organize-Routines)
- **Strong** is described as "the fastest pure logger — you bring the program, it stays out of the way". The free tier allows 3 templates — [sensai.fit Hevy vs Strong 2026](https://www.sensai.fit/blog/hevy-vs-strong-2026) (competitor blog)
- **RP Hypertrophy** is organized around mesocycles: "100+ premade training plans plus 45+ mesocycle templates", typically 4–6 week accumulation blocks followed by a deload — [Boostcamp vs RP](https://www.boostcamp.app/vs/rp-hypertrophy); [arvo.guru RP method](https://arvo.guru/resources/methods/rp-training)
- **Alpha Progression** organizes training into mesocycles in which "set counts, repetition targets, optional RIR targets, and training stress change across the block", with a deload before the next cycle. It also has a Plan Generator — [Alpha Progression blog](https://alphaprogression.com/en/blog/best-progressive-overload-apps) (vendor)
- **Fitbod** has no fixed program: it "generates a fresh strength-training session each time you open it, based on your goals, schedule, the equipment... and a per-muscle-group recovery model" — [tooldirectory.ai Fitbod](https://tooldirectory.ai/tools/fitbod); [Boostcamp alternatives/fitbod](https://www.boostcamp.app/alternatives/fitbod)
- **MacroFactor Workouts** (launched January 2026) can "build personalized workout plans... and guide long-term progression" — [MacroFactor Jan 2026 newsletter](https://macrofactor.com/mm-jan-2026/); [macrofactor.com/workouts](https://macrofactor.com/workouts/)

### Inferences
- The common hierarchy is **Program → (Block/Mesocycle) → Week → Day (session template) → Exercise → Set prescription (+ progression rule)**. Hevy/Strong drop the Week and Block levels entirely and still have big audiences, so a simple model can work for the majority.
- History is always stored as **logged workouts that are independent of the program**, with at most a reference to the program/day they came from. None of the apps lose history when a program changes. A "phase" can therefore be just a dated period with an active plan, with history attached to dates rather than to the plan.
- Nobody found treats "bulk phase / cut phase" as a first-class object that bundles split and diet together. Phases exist only as training blocks/mesocycles.

### Gaps
- Could not confirm whether Boostcamp or Liftosaur let you queue the *next* program automatically, e.g. run Program A for 12 weeks, then auto-start Program B. No source found.
- The Hevy help center returned 403. Details of Hevy's program features (any week concept) come only from search snippets and marketing pages.

## 2. Scheduling: fixed weekdays vs rotating "next workout"; missed days

### Takeaway
Most program apps run **sequentially**: the next workout is the next uncompleted day in the program, and the calendar only gives guidance. Missing a day just shifts the sequence instead of failing the plan. Apps add explicit "skip" and "reschedule/move" actions. Fitbod avoids the problem entirely by generating each session from muscle recovery state.

### Cited Findings
- Boostcamp "lets you reschedule sessions if your week doesn't go to plan". Programs are defined by training days per week with built-in rest days — [r/Boostcamp / Boostcamp search result summary](https://redlib.hbubli.cc/r/Boostcamp) (weak source: aggregated snippet)
- MacroFactor Workouts lets users "skip a scheduled workout without removing it from your program" (reversible), and also move a workout to a different day. Its help center has an article "What Happens If I Miss Workouts or Take Time Off?" — [MacroFactor help: how to skip a workout](https://help.macrofactorapp.com/en/articles/325-how-to-skip-a-workout)
- Fitbod gives each muscle group a recovery % (0–100%). Muscles take up to ~7 days to fully recover, 80–100% counts as fresh and below 50% as fatigued. The "Fresh Muscle Groups" split targets the two most recovered groups. It recommends 3–5 days/week, or 2–3 for a full-body split — [Fitbod help: How Fitbod creates your workout](https://help.fitbod.me/hc/en-us/articles/360004429814-How-Fitbod-Creates-Your-Workout); [Fitbod blog: algorithm](https://fitbod.me/blog/fitbod-algorithm/)
- Hevy/Strong have no schedule engine: the user picks a routine from a folder each time — [Hevy gym routines](https://www.hevyapp.com/features/gym-routines/)

### Inferences
- **Recommended pattern:** a rotating "next workout" pointer, plus optional target weekdays for reminders and adherence, plus Skip/Move actions. A missed day should never force a "restart program". Fixed-weekday-only scheduling is brittle for real lifters.
- For time-boxed phases (a 12-week cut), the end date should be soft: "week 9 of 12" advances by completed weeks or by calendar, and the user picks which. This is an inference; no app documented this choice explicitly.

### Gaps
- No primary documentation found on exactly how Liftosaur or Boostcamp advance weeks when sessions are missed (e.g., whether a week advances by calendar or only after all its days are completed). From general knowledge, Liftosaur advances day-by-day sequentially, but this is **unverified** in this research.

## 3. Automatic progression rules

### Takeaway
There is a spectrum from **declarative rules** (Liftosaur's lp/dp/sum/custom script; Boostcamp's per-program TM/AMRAP rules) to **recommendation engines** (Alpha Progression's per-set weight/rep suggestions) to **feedback-driven autoregulation** (RP's pump/soreness/workload surveys adjusting next week's volume; JuggernautAI's readiness check and set ratings) to **fully generated sessions** (Fitbod). Deloads are usually a scheduled week at the end of a block.

### Cited Findings
- Liftosaur's built-in progressions:
  - **Linear** `lp(5lb)` adds weight after all sets succeed. It supports failure deloads: `lp(5lb, 2, 1, 10lb, 3)`.
  - **Double progression** `dp(5lb, 8, 12)` adds reps from 8 up to 12, then adds 5lb.
  - **Reps sum** `sum(30, 5lb)` adds weight when total reps exceed 30.
  - **Custom** `progress: custom(attempt: 0) {~ ... ~}` runs JS-like logic with persistent `state` variables.
  - `update: custom()` modifies sets *during* a workout (e.g., adds sets based on first-set performance).
  - Deload weeks use `progress: none`.
  - [Liftoscript docs](https://www.liftosaur.com/docs/liftoscript)
- Liftoscript "has JavaScript-like syntax, with only if/else, variable assignments, and a couple of unique types like pounds or kilograms" — [Indie Hackers: Liftosaur for coders](https://www.indiehackers.com/post/liftosaur-weightlifting-tracker-app-for-coders-0f2c1d3837)
- Liftosaur has a blog post on combining a visual "Workout Planner" with Liftoscript, which suggests a UI layer on top of the text language — [Liftosaur blog](https://liftosaur.com/blog/posts/combine-workout-planner-and-liftoscript)
- Boostcamp programs carry built-in progression "so a Training Max goes up on schedule and AMRAP sets drive the next wave without you doing the math" — [Boostcamp /best/budget](https://www.boostcamp.app/best/budget)
- RP Hypertrophy: users "log pump, soreness, and workload feedback after sessions, and the app adjusts next week's volume and load targets accordingly", using MEV/MAV/MRV volume landmarks — [Boostcamp vs RP](https://www.boostcamp.app/vs/rp-hypertrophy). Typical block: roughly +1 set per muscle per week over 4–6 weeks, then a mandatory deload of ~1 week at ~50% volume — [arvo.guru RP method](https://arvo.guru/resources/methods/rp-training) (third-party summary of the RP methodology)
- Alpha Progression gives "set-specific weight and rep recommendations based on your previous performance", handles "real-world gym increments", supports optional RIR and does automatic set/rep periodization with integrated deloads — [Alpha Progression blog](https://alphaprogression.com/en/blog/best-progressive-overload-apps)
- JuggernautAI adjusts the program from set ratings and a daily readiness check (sleep, nutrition, soreness). It prescribes warm-ups, asks how they felt, and adjusts the working weight. It uses MEV/MRV concepts for accessory volume — [sensai.fit JAI vs RP vs AP](https://www.sensai.fit/blog/juggernaut-ai-vs-rp-hypertrophy-vs-alpha-progression-2026); [Garage Gym Reviews JuggernautAI](https://garagegymreviews.com/juggernautai-review)
- Fitbod "treats programming as a continuous loop: log a session, and the next one adjusts weights, sets, and exercise selection for progressive overload while steering work toward recovered muscle groups" — [tooldirectory.ai Fitbod](https://tooldirectory.ai/tools/fitbod)

### Inferences
- For a simple product, two or three presets cover most individual lifters: **double progression** (rep range → add weight), **linear** (add X on success, deload Y% after N failures), and **% of training max** with a weekly wave. Liftosaur shows that the same presets can sit on top of a power-user scripting layer.
- Feedback-based autoregulation (RP/JAI) is the premium tier and is priced at ~$35/month, which suggests users value it but it is costly to build well.

### Gaps
- No published accuracy or satisfaction data on Fitbod's or RP's algorithms was found.

## 4. Linking training phases with nutrition (bulk/cut) or bodyweight goals

### Takeaway
**No mainstream app found links a training phase to a nutrition phase in its logic.** The closest is MacroFactor (nutrition) plus MacroFactor Workouts (Jan 2026). They are two separate apps that sync body metrics, but "at launch, there are no shared coaching features or automatic program adjustments between nutrition and training". JuggernautAI's readiness check takes nutrition as an input signal only.

### Cited Findings
- MacroFactor Workouts and MacroFactor Nutrition are separate apps that share and sync "body metrics, scale weight, progress photos, select habits, and period tracking". Deeper integration "may be explored" in future and would be "intentional and evidence-based rather than automatic or reactive" — [MacroFactor help #381](https://help.macrofactorapp.com/en/articles/381-how-does-macrofactor-workouts-integrate-with-macrofactor-nutrition); [MacroFactor Dec 2025 newsletter](https://macrofactorapp.com/mm-dec-2025/)
- JuggernautAI readiness considers sleep, nutrition and soreness — [sensai.fit comparison](https://www.sensai.fit/blog/juggernaut-ai-vs-rp-hypertrophy-vs-alpha-progression-2026)
- Liftosaur tracks body measurements alongside lifting data — [liftosaur.com](https://liftosaur.com/)
- RP sells a separate diet app (RP Diet) apart from RP Hypertrophy. The RP training app's autoregulation uses training feedback only — [Boostcamp vs RP](https://www.boostcamp.app/vs/rp-hypertrophy) (implicit; the RP Diet app was not separately verified in this research)

### Inferences
- A combined "Phase" object (date range + goal: bulk/cut/maintain + training plan + calorie/macro target + bodyweight target) is a **gap in the market**. It could be eCoach's differentiator, especially for a coach-led product.
- Even MacroFactor, the market leader in adaptive nutrition, chose *not* to auto-adjust training from diet phase, citing evidence concerns. A simple version (phase label + targets + side-by-side charts) is safer than automatic coupling, e.g. auto-reducing volume on a cut.

### Gaps
- Did not verify whether apps such as Caliber, Trainerize or coach platforms offer combined phases. These are outside this scope (individual apps).

## 5. Pricing & monetization (2025–2026)

### Takeaway
There are three price bands. **Loggers** cost about $24–30/year with lifetime options (Hevy, Strong). **Program apps** cost about $60–96/year with generous free tiers (Boostcamp, Alpha Progression, Fitbod). **Coach-algorithm apps** cost about $300–350/year with no free tier (RP, JuggernautAI). Liftosaur is free with an optional paid tier that includes a lifetime purchase, though the exact price was not found.

### Cited Findings
- **Hevy** Pro: $2.99/mo, $23.99/yr, $74.99 lifetime. The free tier has unlimited logging but caps routines at 4, custom exercises at 7 and graph history at 3 months — [sensai.fit Hevy review 2026](https://www.sensai.fit/blog/hevy-review-2026) (competitor blog)
- **Strong** PRO: $4.99/mo, $19.99 per 6 months, $29.99/yr, $99.99 lifetime. The free tier has unlimited logging and 3 templates — [sensai.fit Strong review 2026](https://www.sensai.fit/blog/strong-app-review-2026)
- **Boostcamp** Pro: $59.99/yr (with a 7-day trial) or $14.99/mo. The free tier includes the whole 11,000+ program library, the logger, RPE/RIR and PRs. Pro adds exclusive coach programs, Strength Score, a muscle heatmap, personalized programs and **unlimited custom program creation** — [Boostcamp /best/budget](https://www.boostcamp.app/best/budget)
- **Fitbod**: $15.99/mo or $95.99/yr. 3 free workouts, then paywall — [tooldirectory.ai Fitbod](https://tooldirectory.ai/tools/fitbod); Boostcamp cites $12.99–15.99/mo and $79.99–95.99/yr — [Boostcamp alternatives/fitbod](https://www.boostcamp.app/alternatives/fitbod)
- **Alpha Progression** Pro: $12.99/mo or $79.99/yr (US). The permanent free tier covers logging and manual plans. Pro adds the Plan Generator, progression recommendations and charts — [Alpha Progression blog](https://alphaprogression.com/en/blog/best-progressive-overload-apps)
- **RP Hypertrophy**: $34.99/mo or $299.99/yr. No free tier and no trial, but a 30-day money-back guarantee — [Boostcamp vs RP](https://www.boostcamp.app/vs/rp-hypertrophy). The App Store lists monthly, 6-month and annual options with regional pricing, e.g. S$49.98/mo in Singapore — [App Store SG](https://apps.apple.com/sg/app/id1555614554)
- **JuggernautAI**: $34.99/mo or $349.99/yr, with a 2-week trial — [sensai.fit comparison](https://www.sensai.fit/blog/juggernaut-ai-vs-rp-hypertrophy-vs-alpha-progression-2026)
- **Liftosaur**: free on the app stores. A user review mentions buying a "lifetime subscription" — [liftosaur.com](https://liftosaur.com/); [App Store](https://apps.apple.com/app/id1661880849)

### Inferences
- The common paywall line is: **logging and following a program are free, while *creating* multiple programs, auto-progression and analytics are paid**. Hevy caps routines and Boostcamp caps custom programs, which directly affects "multiple schedules for different periods".

### Gaps
- Liftosaur's exact premium and lifetime prices were not found in accessible sources.
- MacroFactor Workouts pricing was not confirmed (the Dec 2025 newsletter had a "pricing preview", but its content was not retrieved).

## 6. What users praise / complain about

### Takeaway
Users choose based on how much they want to be told what to do. People who like **structure** go to Boostcamp, **flexibility** to Hevy, and **power** to Liftosaur (praised but "technical"). People who want to be **handed workouts** go to Fitbod, which loses users who want named programs and a free tier. Complaints focus on paywalls, rigidity versus discipline, and the learning curve.

### Cited Findings
- The 2026 Reddit consensus is "Hevy and Strong for workout logging, Boostcamp for following structured programs from real coaches" — [getfitcraft best fitness apps reddit](https://getfitcraft.com/compare/best-fitness-apps-reddit) (aggregator)
- Boostcamp "gives you a great program and expects you to bring the discipline": progression is handled, but motivation is the user's job — [gummysearch workout apps from Reddit](https://gummysearch.com/tools/best-products/workout-apps/) (aggregator)
- Hevy is liked for its "rather high level of flexibility" in customizable plans — [gummysearch](https://gummysearch.com/tools/best-products/workout-apps/)
- People leave Fitbod because they prefer "named-methodology programs over algorithmic session generation", want a permanent free tier, or want deeper set-by-set logging — [Boostcamp alternatives/fitbod](https://www.boostcamp.app/alternatives/fitbod) (competitor; treat as biased)
- Liftosaur: "It is technical, for sure, and takes some tweaking to get the hang of it - but once it is dialed in, it's amazing". Its author pitches it as "worth the learning curve", with autocomplete to help — [Indie Hackers Liftosaur](https://www.indiehackers.com/product/liftosaur); [Indie Hackers post](https://www.indiehackers.com/post/liftosaur-weightlifting-tracker-app-for-coders-0f2c1d3837)
- JuggernautAI is "the best powerlifting app, if you're actually a powerlifter", meaning it is niche — [aitoolsbakery JAI review 2026](https://aitoolsbakery.com/?p=5896)

### Inferences
- Design tension: **simplicity for most users vs. expressiveness for power users.** A good pattern is presets with a hidden "advanced" layer (as Liftosaur adds a visual planner over its script), and avoiding a scripting language as the primary interface.
- "Rigidity" complaints are best addressed with skip/move/swap-exercise actions that keep progression state, not by dropping programs.

### Gaps
- Could not directly retrieve Reddit threads (r/fitness, r/weightroom, r/Liftosaur, r/boostcamp). Opinions here come via aggregators and vendor pages, so the sentiment evidence is weak. App Store review text was not analyzed.
