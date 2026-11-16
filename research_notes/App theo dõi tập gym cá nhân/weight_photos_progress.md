# Weight, Progress Photos & Progress Review in Individual Fitness Apps (2025-2026)

Research date: 2026-10-16. Scope: apps for individuals (not coaches). Note: several sources are app-store aggregators (appfollow, mwm.ai, appgoblin) or competitor blogs (gainframe.app, sensai.fit); flagged where relevant.

## Weight: trend smoothing, fluctuations, goal projection, sync, reminders, widgets

### Takeaway
The proven pattern is "log raw daily weight, show a smoothed trend line as the headline number, and project time-to-goal from the trend". Hacker's Diet's exponentially smoothed moving average (10% weight on today) is the classic form. Happy Scale (iOS), Libra (Android) and MacroFactor all build on it. Auto-import from smart scales or health platforms is the biggest effort reducer.

### Cited Findings
- Hacker's Diet formula: `A[d] = A[d-1] + 0.1 (M[d] - A[d-1])`, a smoothing constant of 0.9, so each new weigh-in moves the trend by 10% — [Fourmilab / The Hacker's Diet](https://fourmilab.ch/hackdiet/www/subsubsection1_4_1_0_8_3.html)
- The point of the Hacker's Diet is to adjust using the long-term trend and not be discouraged by short-term fluctuations — [Wikipedia: The Hacker's Diet](https://en.wikipedia.org/wiki/The_Hacker%27s_Diet)
- Some implementations use a 0.05 coefficient (smoother) instead of 0.1. Products choose different constants — [search summary of community implementations, e.g. Wikiversity](https://en.wikiversity.org/wiki/One_man%27s_look_at_The_Hacker%27s_Diet) (low confidence on exact attribution)
- **MacroFactor:** first fills gaps by linear interpolation (e.g. 151 lb Monday, 150 lb Wednesday, so Tuesday is assumed to be 150.5). It then applies a proprietary moving average that "places greater emphasis on more recent weigh-ins". The chart shows a pale raw line and a deep-purple trend line, and "Current Trend" differs from the raw scale weight. It is "resilient to missing weight entries" but recommends daily weigh-ins, or at least 3 per week. Smart-scale data sources allow automatic weigh-ins — [MacroFactor Help: Weight Trend](https://help.macrofactorapp.com/dashboard/weight_trend/)
- MacroFactor philosophy: don't react to a few days off baseline. If weight stays different by day 4–5, the trend adapts. The weight trend drives its expenditure estimate — [MacroFactor algorithms & philosophy](https://macrofactor.com/macrofactors-algorithms-and-core-philosophy/)
- **Happy Scale (iOS, Front Pocket Software):** moving-average trend, predictions of future weight (you can name and share them, e.g. "weight at my wedding"), goals split into smaller milestones, two-way opt-in Apple Health sync, custom chart date ranges, BMI with WHO/NHS ethnicity-adjusted modes. Rated 4.9/5 from 58,000+ ratings — [App Store: Happy Scale](https://apps.apple.com/us/app/happy-scale/id532430574)
- Happy Scale is often recommended on r/loseit as a companion to calorie apps (LoseIt/MFP) because it shows smoothed trends rather than daily numbers — [GummySearch Reddit aggregation](https://gummysearch.com/tools/best-products/weight-loss-app/); [iPhoneJD review](https://www.iphonejd.com/?p=5491)
- **Libra (Android, net.cachapa.libra):** trend line so daily fluctuations don't make the chart jump. Easy entry, zoomable chart, BMI, goal plus time-to-goal estimate, daily calorie estimate, CSV import/export, cloud sync, historically Withings scale sync. Free with a one-time paid unlock — [AlternativeTo: Libra](https://www.alternativeto.net/software/libra---weight-manager/about/); [Nerdschalk](https://nerdschalk.com/being-in-shape-with-libra-weight-manager/); [Withings blog (2011)](https://blog.withings.com/2011/03/09/withings-synchs-with-libra-an-android-app-for-weight-monitoring-2/)
- Android Health Connect exposes a standard `WeightRecord` (API 34+) that apps can read and write, which is the modern way to get smart-scale data on Android — [Android Developers: WeightRecord](https://developer.android.com/reference/kotlin/android/health/connect/datatypes/WeightRecord)
- Newer "calm" weight apps use a 7-day moving average (Steady), weekly-focused tracking (Weighra), or a hide-number mode where you log without seeing the value (Kind Scale) — [mwm.ai: Steady](https://mwm.ai/apps/steady-weight-tracker/6754262894); [hunted.space: Weighra](https://hunted.space/product/weighra); [appgoblin: Kind Scale](https://appgoblin.info/apps/6757439233)

### Inferences
- For a "lazy tracker": the headline number should be the trend weight, with raw weight secondary. The app should interpolate missed days rather than treat them as failure. Auto-import via Apple Health / Health Connect turns logging into zero effort for smart-scale owners.
- An EMA with alpha around 0.1 (Hacker's Diet) is simple, explainable and good enough. MacroFactor-style interpolation plus a recency-weighted average is the more polished version. Goal projection should come from the trend slope (e.g. last 2–4 weeks) and be shown as a date range, not a single date.
- An optional hide-number mode and a 7-day-average view address weigh-in anxiety.

### Gaps
- Could not confirm whether Libra currently supports Health Connect, widgets or reminders. The Play Store page failed to load, and Libra's development status in 2025-2026 is unverified.
- Happy Scale's widget and reminder features were not confirmed from the listing text retrieved.
- MacroFactor's exact smoothing constant is proprietary or undisclosed.

## Photos: poses, ghost overlay, comparisons, timelapse, privacy, linking to weight/date

### Takeaway
Ghost-overlay alignment, front/side/back pose sets, side-by-side or slider comparison, and timelapse export are now standard in dedicated photo apps. Privacy is a selling point: on-device storage, own-iCloud sync, and photos that stay private even on public profiles. Gym loggers like Hevy offer a lighter version: one photo per day, an overlay, and side-by-side comparison.

### Cited Findings
- **Hevy:** photo can be logged with or without measurements, one photo per day. The in-app camera has an "Overlay" button showing your last progress photo for alignment. Photos are visible only to you unless you share them outside Hevy — [Hevy Help: Body composition, measurements & progress photos](https://help.hevyapp.com/hc/en-us/articles/35385479603479-Body-Composition-Tracking-Measurements-and-Progress-Photos) (page content via search snippet; direct fetch returned 403)
- Hevy: side-by-side comparison with any photo in your library plus a shareable image. Photos stay private "even if your profile is public". It advises the same pose, time, lighting and camera, and photos every 4–5 weeks rather than weekly because "visual changes are often too small" — [Hevy: Progress photos feature](https://www.hevyapp.com/features/progress-photos/)
- Hevy's one-photo-per-day limit is "awkward for multiple poses" (front/side/back) — [GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/) (competitor-authored)
- **Progress – Body Tracker (Lasmit):** tracks measurements, weight, BMI, body fat and photos, and compares any two photos side by side. Two-way Apple Health sync plus Fitbit. Data is "stored privately on your device and synced through your own iCloud". Pro unlocks photos, unlimited measurement areas, custom reports and past-data entry, so core photo features sit behind the paywall — [appfollow: Progress Body Tracker](https://apps.appfollow.io/ios/progress-body-tracker-my-bmi/583840813?country=tr); [GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/)
- **Dedicated photo apps (2025-2026 wave):** Progressly has a ghost overlay, front/side/back shots, a before/after slider and timelapse. ProgressCam shows a ghost overlay of the previous photo in the viewfinder. Progress Pics: Body Tracker has an angle-organised timeline, timelapse export and on-device storage. Solo.Shots and Time-Lapse Photo are on-device with a ghost overlay. Metamorph offers auto-alignment and GIF/video export with reminders — [appgoblin: Progressly](https://appgoblin.info/apps/6789591055); [mwm.ai: ProgressCam](https://mwm.ai/apps/progresscam-progress-photos/6760968159); [App Store: Progress Pics](https://apps.apple.com/us/app/-/id6758867697); [mwm.ai: Time-Lapse Photo](https://mwm.ai/apps/time-lapse-photo/6774660000); [GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/)
- AI physique analysis is emerging. GainFrame offers AI body-fat estimates and a 12-muscle-group analysis, but selected photos are sent to an AI service, and estimates depend on photo quality — [GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/) (self-promotional)
- SnapTrack, a legacy app, was last updated in June 2017, which shows churn in this category — [GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/)

### Inferences
- Minimum viable photo feature for eCoach: a pose set (front/side/back) per session, not one per day; a ghost overlay; a link to the date's trend weight and measurements; a slider and side-by-side view; optional timelapse.
- Privacy expectations: photos stay out of the camera roll, are stored in the app sandbox, sync is optional and user-owned, app lock is optional, and photos are never public by default. Any AI analysis that uploads photos must be explicit opt-in.
- A prompt every 2–4 weeks fits better than daily photos for a lazy user, since Hevy itself recommends 4–5 weeks.

### Gaps
- I found no verified source on which apps hide photos from the camera roll or offer encryption or biometric app lock. Most listings say only "private" or "on-device".
- Pricing for the Progress (Lasmit) Pro tier and for the newer photo apps was not retrieved.

## Body measurements and body-fat estimates

### Takeaway
Weight plus waist is the common free baseline. Full circumference sets and body fat are usually Pro features. Body fat is mostly user-entered (from a smart scale or tape) or, newly, AI-estimated from photos.

### Cited Findings
- Hevy free tier: weight and waist only. Hevy Pro: body fat plus waist, neck, shoulders, chest, biceps, forearms, abdomen, hips, thighs and calves, charted in the Measures section — [Hevy Help](https://help.hevyapp.com/hc/en-us/articles/35385479603479-Body-Composition-Tracking-Measurements-and-Progress-Photos) (via search snippet)
- Progress (Lasmit): unlimited measurement areas and past-data entry are Pro features — [appfollow listing](https://apps.appfollow.io/ios/progress-body-tracker-my-bmi/583840813?country=tr)
- Wao (VN) includes body measurements and BMI on Asian standards — [wao.vn](https://wao.vn/)

### Inferences
- For a lazy user, default to weight daily, waist weekly or monthly, and the rest optional. Body fat should accept smart-scale imports but carry an "estimate" label.

### Gaps
- No source here on how accurate photo-AI body-fat estimates are.
- Strong's measurement features were not verified in this pass.

## Progress review: weekly check-ins, summaries, reports, year in review

### Takeaway
Weight-specific apps review progress through the trend chart, milestones and goal-date predictions. Gym loggers use PR and volume stats and weekly stats. I found no strong evidence of rich weight-plus-photo "weekly review" automation in mainstream individual apps. This looks like a gap.

### Cited Findings
- Happy Scale motivates through milestones (sub-goals) and predictions. Users say it "changed my relationship with the scale" and that weighing daily with a moving average means "I don't flip out over occasional weight gain". It helped them stick with it through plateaus — [App Store: Happy Scale](https://apps.apple.com/us/app/happy-scale/id532430574)
- MacroFactor uses the weight trend for weekly target adjustments and "Weekly Budget Safeguards" against noise — [MacroFactor Help](https://help.macrofactorapp.com/dashboard/weight_trend/); [MacroFactor goal adjustment article](https://help.macrofactorapp.com/en/articles/222-how-does-macrofactor-make-adjustments-for-a-weight-gain-or-weight-loss-goal)
- Gym-log apps such as Gym Ting give weekly stats to show improvement. Vietnamese media list Strong and JEFIT as progress trackers — [XTmobile (VN)](https://www.xtmobile.vn/app-tap-gym)
- Hevy limits chart history to 3 months on Free; Pro is unlimited — [SensAI Hevy review 2026](https://www.sensai.fit/pt/blog/hevy-review-2026) (competitor-authored)
- Wao (VN) offers daily and weekly nutrition reports, plus weekly weight graphs — [wao.vn](https://wao.vn/)

### Inferences
- An opportunity: an auto-generated weekly or monthly "check-in card" combining trend change, rate per week against goal, projected goal date, adherence (days logged), workouts and PRs, and a photo comparison against 4 weeks ago. Few individual apps combine all of these.
- Motivating: trend change, milestones and the projected date. Noise: daily raw deltas and red/green day judgements.

### Gaps
- Could not verify details of Hevy's or Strong's monthly report or "year in review" features. Searches returned nothing authoritative.
- No Reddit thread-level evidence was retrieved on which summaries users find motivating.

## Retention: what keeps lazy users logging vs. annoys them

### Takeaway
Users stay when the app reduces emotional friction (trend over raw number) and data entry is near zero (scale sync). A newer cohort of apps deliberately removes streaks, judgement and number display, which signals that streak and "bad day" mechanics annoy part of the audience.

### Cited Findings
- Kind Scale deliberately avoids streaks, calorie counting and "good/bad day" labels, and offers a hide-number mode — [appgoblin: Kind Scale](https://appgoblin.info/apps/6757439233)
- Weighra is "weekly-focused" on the premise that "consistency matters more than perfection" — [hunted.space: Weighra](https://hunted.space/product/weighra)
- Happy Scale reviews credit its trend view with helping long-term adherence and praise responsive developer support — [App Store](https://apps.apple.com/us/app/happy-scale/id532430574)
- MacroFactor reduces logging burden through smart-scale data sources and tolerates missed days via interpolation — [MacroFactor Help](https://help.macrofactorapp.com/dashboard/weight_trend/)
- Paywalling core features (e.g. photos in Progress Pro, overlays and imports in SnapTrack) is a recurring con — [GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/)

### Inferences
- Use one gentle, user-timed morning reminder (snoozable, auto-silenced once a scale sync arrives). Prefer "logged X of last 7 days" over hard streaks that reset, a home-screen widget for one-tap entry, and no guilt messaging.

### Gaps
- No quantitative retention data (D30 and similar) for any of these apps. Widget support per app was not verified.

## Vietnamese individual fitness apps

### Takeaway
Vietnamese-made apps are almost entirely nutrition and calorie trackers (Wao, Caloer, Eatsy, Dietfit AI) with basic weight logging. I found no notable Vietnamese-made app focused on gym logging plus trend weight plus private progress photos. Gym-log coverage in Vietnamese media points to foreign apps (Strong, JEFIT, Hevy).

### Cited Findings
- **Wao (BEWAO Corporation):** claims "#1 nutrition app in Vietnam", 1.5M+ users, 4.8/5 (824 reviews) and 350k+ meals logged daily, and says it was the first Vietnamese health app featured on App Store Spotlight (Aug 2025). It has AI photo and voice food logging and 2M+ Vietnamese dishes. Weight tracking shows a weekly graph, with body measurements and BMI on Asian standards. Free: database, calorie tracking, basic reports, weight and water. Premium: ₫39,000/week, ₫79,000/month or ₫599,000/year, with a 14-day trial — [wao.vn](https://wao.vn/) (self-reported numbers)
- **Caloer:** calorie and weight-loss app for Vietnamese users with 20,000+ Vietnamese dishes — [App Store: Caloer](https://apps.apple.com/us/app/caloer-t%C3%ADnh-calo-gi%E1%BA%A3m-c%C3%A2n/id6474173293); [Google Play](https://play.google.com/store/apps/details?id=com.iwritin.caloer&hl=en_SG)
- **Eatsy:** meal logging, calorie deficit, weight and body measurement updates, and menu suggestions for Vietnamese users — [FPT Shop roundup](https://fptshop.com.vn/tin-tuc/giai-tri/app-tinh-calo-162169)
- **Dietfit AI:** nutrition and weight tracking personalised for Vietnamese users — [Unikorn](https://unikorn.vn/p/dietfit-ai)
- Vietnamese gym-app roundups recommend foreign apps (Seven, Strong, JEFIT, Gym Ting) — [XTmobile](https://www.xtmobile.vn/app-tap-gym); [Viettablet](https://www.viettablet.com/app-tap-gym)

### Inferences
- Gap for eCoach: a Vietnamese-language, privacy-first tracker combining gym logging, trend weight, a progress photo vault and periodic reviews. Local apps focus on food databases; foreign apps lack Vietnamese UX and VND pricing.
- Wao's pricing (₫79k/month, ₫599k/year) is a useful local price anchor.

### Gaps
- Searches did not surface any Vietnamese-made gym workout logger with traction. This may reflect search limits rather than absence.
- No Vietnamese user complaint data (app reviews, Facebook groups) was retrieved.

## Pricing (2025-2026) and praise/complaints

### Takeaway
Single-purpose weight and photo apps are cheap (around $12/yr or a lifetime unlock). Gym loggers are around $24/yr, and nutrition-coaching apps are $60–72/yr.

### Cited Findings
- Happy Scale: the free core plus in-app purchases of $1.99/month, $11.99/year or $39.99 lifetime, with tips of $0.99–$9.99 — [App Store](https://apps.apple.com/us/app/happy-scale/id532430574). Older sources describe a $5 one-time unlock — [AlternativeTo / aggregators](https://alternativeto.net/software/happy-scale/about). This suggests the app has moved to subscription; the conflict is noted.
- Hevy Pro: $2.99/month, $23.99/year or $74.99 lifetime (US, Sept 2026). Free caps: 4 routines, 7 custom exercises, 3-month chart history. "Advanced measurements" are Pro only — [SensAI Hevy review 2026](https://www.sensai.fit/pt/blog/hevy-review-2026). Another source claims plans start at $8.99/month — [subger](https://subger.com/en/deal/hevy-pro) (conflicting, likely regional or outdated)
- MacroFactor: listed IAPs include $11.99/month, $47.99 per 6 months and $71.99/year, with other tiers ($9.99/month, $59.99/year, $89.99 bundle) — [AppPricingLab](https://apppricinglab.com/iap/apple/1553503471) (aggregator; tiers may vary by region and date)
- Libra: free with a one-time paid unlock — [AlternativeTo](https://www.alternativeto.net/software/libra---weight-manager/about/)
- Wao (VN): ₫39k/week, ₫79k/month, ₫599k/year — [wao.vn](https://wao.vn/)

### Inferences
- Lazy users are price-sensitive to subscriptions for a "just log weight" use case. A lifetime or one-time option, or a generous free core (trend plus photos), is likely to be well received.

### Gaps
- Strong pricing, Progress (Lasmit) Pro pricing and Libra's exact unlock price for 2026 were not verified.
- Limited direct Reddit quotes were retrieved, because aggregator summaries were used instead.
