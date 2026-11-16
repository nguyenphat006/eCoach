# Nutrition / meal tracking for a "lazy" gym-goer, with a focus on Vietnamese food (state as of Oct 2026)

Source-quality note: many 2026 "review" pages (nutrola.app, fitia.app, recime.app, nutriscan.app, unstar.app, fitbudd.com) are content marketing from competing apps. They are used here only for price and feature facts that match other sources, and are flagged where used. I found no Reddit threads specifically about logging Vietnamese food. Vietnamese "top app" lists come from electronics retailers (dienthoaivui, fptshop, thegioididong). They are SEO content, not independent reviews.

## 1. Logging UX: which methods reduce friction most?

### Takeaway
All the major apps now offer search, barcode, AI photo, voice/text description and copy/saved-meal logging. For someone who eats the same things repeatedly, copy/paste plus saved meals or favorites cut the most work. AI photo and text logging help most with mixed dishes that have no barcode, which describes most Vietnamese meals. MacroFactor recommends adding a text description to the photo for regional dishes.

### Cited Findings
- MacroFactor AI logging (beta, Apr 2025): "capture a meal with a photo and automatically populate your Plate with nutrient complete, editable food entries". It breaks the meal into ingredients and recipes by querying its own verified database. A "Photo & Text" mode adds a short description "for improved accuracy on complex or regional dishes". After the AI step, users can keep scanning or searching on the same plate. — [MacroFactor](https://macrofactor.com/ai-food-logging/)
- MacroFactor also has Favorites for saving staple foods with preferred serving sizes, and an Apple Watch app for fast logging. — [MacroFactor Jan 2025 update](https://macrofactor.com/mm-january-2025/); [MacroFactor site/search summary](https://macrofactor.com/macrofactor/)
- The MyFitnessPal 2025 Summer Release puts scan, speak and search in one unified view. Meal Scan (AI photo), Barcode Scan and Voice Log are paid-only (Premium/Premium+). Voice Log lets users "say what they ate" and the app suggests matches. — [Eastern Progress / MFP press release](https://www.easternprogress.com/myfitnesspal-announces-its-2025-summer-release/article_0c108ad7-c8f9-5cbe-bbc6-eca09b6be312.html); [fitbudd summary](https://fitbudd.com/post/myfitnesspal-app-cost)
- Lose It! has a "previous meals" feature that adds a whole earlier meal in one tap. Several apps offer "Copy Previous Day" and multi-select copy to a future day. — [search summary of forum/help pages: Cronometer forums](https://forums.cronometer.com/discussion/comment/501), [MacrosFirst help](https://help.macrosfirst.com/en/articles/8-create-a-saved-meal-from-a-meal-on-your-daily-log)
- Cronometer forum users have asked for label-scanning to create custom foods and for meal copy/paste, which shows these are recurring friction points. — [Cronometer forum](https://forums.cronometer.com/discussion/5014/feature-request-scanning-food-labels-to-create-custom-foods-copying-pasting-meals)
- MacroFactor tells users to make "a good-faith effort to log as accurately as you can with whatever method is convenient and feasible for you to apply consistently". It says estimating is sometimes fine, because the expenditure algorithm absorbs consistent logging errors. — [MacroFactor help](https://help.macrofactorapp.com/en/articles/201-how-accurately-do-i-need-to-log-my-food); [MacroFactor help 140](https://help.macrofactorapp.com/en/articles/140-do-i-need-to-log-everything-i-eat-and-drink-to-have-an-accurate-expenditure-and-use-macrofactors-coaching-features)
- Vietnamese app Caloer offers AI photo recognition, nutrition-label scanning and "AI voice input" for logging. — [App Store: Caloer](https://apps.apple.com/us/app/caloer-t%C3%ADnh-calo-gi%E1%BA%A3m-c%C3%A2n/id6474173293)

### Inferences
- For a lazy tracker whose diet repeats (the same "1 chén cơm + ức gà" every day), the best tools are saved or favorite meals and copy-day/copy-to-tomorrow. AI photo plus text is the best fallback for eating out (cơm tấm, phở). Barcode matters less for Vietnamese street food, which mostly has no packaging.
- Consistency matters more than precision when targets adapt (MacroFactor's view). That supports deliberately approximate "standard portion" presets for Vietnamese dishes.

### Gaps
- I found no quantitative user data comparing friction across logging methods, and no Reddit threads about Vietnamese dishes specifically.
- I found no independent accuracy benchmark for AI photo logging of Vietnamese dishes.

## 2. Meal plans vs. logging; macro targets per phase; adaptive targets

### Takeaway
MacroFactor does not offer premade plans, but it supports planning ahead. Users can pre-log foods to future hours or days and copy or multi-paste across the week, and its expenditure algorithm adjusts targets weekly for bulk, cut or maintenance. MyFitnessPal Premium+ ($99.99/yr) generates weekly recipe plans with grocery lists that can be logged. I did not find any of these apps offering an explicit "planned → confirm eaten" state.

### Cited Findings
- MacroFactor Timeline 2.0: users can "tap on the Add shortcut next to any hour of the day to log to that hour in advance". They can copy and paste items, hours or whole days, with "To Today" and "To Tomorrow" shortcuts. Multi-Paste puts foods into each day "without removing them from the clipboard" for weekly planning. A calendar lets users jump across weeks. — [MacroFactor Timeline](https://macrofactor.com/timeline-based-food-logger/)
- MacroFactor "empowers users to create their own personalized eating plans and does not provide pre-made meal plans". — [search summary; secondary](https://dev.asburyseminary.edu/manual/does-macrofactor-app-provide-meal-plans-l0xr.html) (low-quality source)
- MacroFactor bases its calculations and adjustments on "what you actually did, not what you were supposed to do". It adjusts calorie and macro targets from logged intake and weight trend. — [MacroFactor](https://macrofactor.com/macrofactor/)
- Inaccuracies "will be reflected in your calculated expenditure, which informs your energy intake targets", and are reviewed at the check-in. — [MacroFactor help 201](https://help.macrofactorapp.com/en/articles/201-how-accurately-do-i-need-to-log-my-food)
- MyFitnessPal Meal Planner (Premium+, $99.99/yr) builds weekly plans from 1,500+ recipes based on goals, budget, dietary preferences and household size. It produces grocery lists and add-to-cart, and meals "can then be logged directly". MFP added it after acquiring Intent in Feb 2025. It launched in US/UK/IE/CA/AU/NZ only, not Vietnam. — [Nutrition Insight](https://nutritioninsight.com/news/nutrition-tracker-meal-planner-diet-health-fitness-app-myfitnesspal-intent.html); [Android Authority](https://androidauthority.com/myfitnesspal-acquires-intent-3525696)
- Lose It! Premium includes personalized meal plans and recipes (low-carb, high-protein, etc.). — [fitbudd (secondary)](https://www.fitbudd.com/post/lose-it-premium-review)
- Vietnamese apps: Eatsy says it "plans meals daily" and has Vietnamese recipes with pre-calculated calories. Caloer offers "personalized meal plans designed by nutrition experts". — [App Store: Eatsy](https://apps.apple.com/app/id1537221492); [App Store: Caloer](https://apps.apple.com/us/app/caloer-t%C3%ADnh-calo-gi%E1%BA%A3m-c%C3%A2n/id6474173293)

### Inferences
- There is a clear opportunity for a "planned meal → one-tap confirm / swap / skip" flow tied to the training phase (bulk/cut templates). Western apps either pre-log, which mixes planned and eaten food, or produce recipe-based plans that don't fit a Vietnamese routine of rice, eating out and street food.
- Adaptive targets in the MacroFactor style work best with consistent weigh-ins and consistent (not necessarily precise) logging, which suits lazy users.

### Gaps
- I could not verify how MacroFactor handles a phase switch (bulk→cut) inside its coaching UI, or whether any app has a true planned/eaten flag.

## 3. Food database quality; Vietnamese coverage; Vietnamese apps; national food composition table

### Takeaway
MacroFactor and Cronometer use verified databases. MyFitnessPal relies on crowd-sourced entries. Vietnamese dish coverage in Western apps comes mostly from user entries with widely varying values. Local apps (Eatsy ~6,000 items, Caloer, iEatBetter, WAO) cover Vietnamese dishes and have Vietnamese UIs but are small and lightly reviewed. The official NIN food composition table exists only as a book-style publication. I found no open, downloadable, licensed digital version.

### Cited Findings
- MacroFactor uses "a verified food search database", in contrast to MyFitnessPal's "unverified user-generated entries". — [MacroFactor](https://macrofactor.com/macrofactor/)
- Cronometer's core database is NCCDB plus USDA, research-grade rather than crowdsourced. Free users get full database access. — [nutrola (competitor content, consistent with Cronometer's known positioning)](https://nutrola.app/en/blog/is-cronometer-free-2026); [calorie-trackers.com](https://www.calorie-trackers.com/reviews/cronometer/)
- Calorie values for Vietnamese dishes vary widely across Vietnamese health sites. A bowl of phở is quoted as averaging 350 kcal. Bún bò is quoted as ~165 kcal for 150 g noodles alone, while full bowls are cited at 500 to 650+ kcal. — [Long Châu (search snippet; page returned 403)](https://nhathuoclongchau.com.vn/bai-viet/giai-dap-thac-mac-1-to-bun-bo-bao-nhieu-calo-70150.html); [Pharmacity](https://www.pharmacity.vn/bun-bo-hue-mot-to-bun-bo-bao-nhieu-calo-va-an-co-beo-khong.htm)
- A hobby dataset on Hugging Face lists ~300 Vietnamese foods (e.g. phở bò 450 kcal, phở gà 380 kcal). Phở at 350 vs 450 kcal shows how far sources disagree. — [Hugging Face vn_food_db](https://huggingface.co/spaces/lapnt3/my-gradio-app/blob/main/data_mining/vn_food_db.py)
- FatSecret has Vietnamese dish entries (e.g. phở bò, bánh mì), many from members or brands. FatSecret Android has ~50 million downloads. — [FatSecret pho bo entry](https://www.fatsecret.es/calor%C3%ADas-nutrici%C3%B3n/vitasia/pho-bo/100g?frc=True); [FPT Shop](https://fptshop.com.vn/tin-tuc/giai-tri/app-tinh-calo-162169)
- Vietnamese retailer lists (2025-2026) recommend Yazio (Vietnamese UI, broad food database), FatSecret, MyFitnessPal, Eatsy and Caloer. One list dated 30/08/2026 names iEatBetter ("based on Vietnamese menus", free) and Eatsy (6,000+ foods, about 1.788M VND/yr premium). — [FPT Shop](https://fptshop.com.vn/tin-tuc/giai-tri/app-tinh-calo-162169); [Điện Thoại Vui](https://dienthoaivui.com.vn/app-tinh-calo-ung-dung-do-calo-tieng-viet/)
- Eatsy (Vietnamese UI) has a database of up to 6,000 items covering dishes from all three regions plus international food. It claims to have "helped 40,000+ Vietnamese" users, with an average loss of 6 kg (marketing claim). — [App Store: Eatsy](https://apps.apple.com/app/id1537221492)
- Caloer (developer Nguyen Hai Anh) has "thousands of foods from across Vietnam" and is rated 4.4★ from only 72 ratings on the US store. Some reviews report data loss after updates. — [App Store: Caloer](https://apps.apple.com/us/app/caloer-t%C3%ADnh-calo-gi%E1%BA%A3m-c%C3%A2n/id6474173293)
- WAO markets itself as an AI calorie tracker built for Vietnamese food, claiming "2,000,000+ Vietnamese dishes" (phở, bún bò, cơm tấm, bánh mì, lẩu). The claim is unverified and almost certainly counts generated variants. — [search snippet, AppFollow listing](https://apps.appfollow.io/ios/wao-food-calorie-counter/6737834587?country=sc)
- National Institute of Nutrition (Viện Dinh dưỡng, NIN) food composition tables: "Nutritive Composition Tables of Vietnamese Foods" (2000) and a "Vietnamese Food Composition Table" (Medical Publishing House, 2017) are cited in research. — [search summary of INDDEX24 Vietnam supplement / nutrition literature](https://resolve.cambridge.org/core/journals/public-health-nutrition/article/issues-in-the-development-and-use-of-food-composition-databases/BD20AF5AF62F3899D85E18E2256057D0)
- NIN keeps analyzing processed and street foods to update the table. One example is a 2006 study of 27 traditional foods with 15 parameters per 100 g. — [viendinhduong.vn research record](https://viendinhduong.vn/en/lookup/de-tai-nghien-cuu-khoa-hoc/68035cf4359ef722321fcd6c)
- A 2022-2024 project built "Vietnam's first agri-food composition database" from 100 raw products in 7 groups, noting "Vietnam has lacked such a comprehensive and standardized national resource". It covers raw agricultural foods, not cooked dishes. — [AJAD/SEARCA](https://ajad.searca.org/article?p=5270)
- Open Food Facts has a Vietnam edition with crowd-sourced packaged-food data (open ODbL licence). — [vn.openfoodfacts.org](https://vn.openfoodfacts.org/ingredients)

### Inferences
- A Vietnam-focused app will probably need its own curated "standard portion" table for ~100-300 common dishes (cơm tấm sườn bì chả, phở bò tái, bún bò, 1 chén cơm ≈ 130-150 g rice). It could be built from ingredients using NIN raw-food values and labelled as estimates. Using crowd-sourced values directly would bring in the wide variance shown above.
- Vietnamese apps win on dish coverage and language but have small user bases and weak trust signals. Western apps win on algorithms and UX but handle Vietnamese dishes poorly.

### Gaps
- I could not confirm the exact food counts in the NIN tables (commonly said to be ~500+ foods in the 2007 edition). I found no official statement on their digital availability or licensing. No official open API or CSV was found on viendinhduong.vn.
- I found no download or MAU figures for Eatsy, Caloer, WAO or iEatBetter, and no independent accuracy tests.
- I could not confirm whether Yazio's Vietnamese UI includes curated Vietnamese dishes.

## 4. Pricing and monetization (2025-2026)

### Takeaway
Paywalls on the fastest logging tools (barcode, AI photo, voice) are now the norm at MyFitnessPal and reportedly at Lose It!. Cronometer is the main exception, keeping barcode scanning free. MacroFactor has no free tier. Vietnamese apps cost much less (~$15-18/yr or ~1.8M VND/yr).

### Cited Findings
- MyFitnessPal 2026: Free; Premium $79.99/yr or $19.99/mo; Premium+ $99.99/yr or $24.99/mo (Meal Planner). Barcode scanner, custom macros and ad-free are paid. — [unstar.app](https://unstar.app/blog/is-myfitnesspal-premium-worth-it-paywall-app-reviews-2026); [fitbudd](https://fitbudd.com/post/myfitnesspal-app-cost)
- MFP moved barcode scanning behind the Premium paywall in Aug 2022, which drew wide criticism. — [Slashdot/The Verge](https://news.slashdot.org/story/22/08/25/1955238/myfitnesspal-paywalls-barcode-scanner-that-made-counting-calories-easy); [Droid Life](https://droid-life.com/?p=289067)
- MacroFactor: $11.99/mo, $47.99 per 6 months, $71.99/yr. — [nutrola (competitor)](https://nutrola.app/en/blog/why-is-macrofactor-so-expensive)
- Cronometer Gold: $49.99/yr. The free tier includes barcode scanning and NCCDB access. — [nutrola (competitor)](https://nutrola.app/en/blog/how-much-does-cronometer-cost-now-2026)
- Lose It! Premium was reportedly raised from $39.99 to $79.99/yr, often discounted to $19.99 for the first year. Barcode scanning reportedly moved to Premium for most new users in 2026. — [search summary of brainbound/nutriscan (secondary, not verified on official site)](https://www.brainbound.blog/lose-it-cost-premium-guide)
- Other prices from a VN list: Yazio Premium $47.90/yr; Lifesum $99.99/yr; FatSecret Premium $59.99/yr. — [Điện Thoại Vui](https://dienthoaivui.com.vn/app-tinh-calo-ung-dung-do-calo-tieng-viet/)
- Caloer: Premium $7.99/3 mo, $12.99/6 mo, $14.99/12 mo. Eatsy: ~1.788M VND/yr. — [App Store: Caloer](https://apps.apple.com/us/app/caloer-t%C3%ADnh-calo-gi%E1%BA%A3m-c%C3%A2n/id6474173293); [Điện Thoại Vui](https://dienthoaivui.com.vn/app-tinh-calo-ung-dung-do-calo-tieng-viet/)

### Inferences
- In Vietnam, Western prices ($50-100/yr) are high relative to local purchasing power. Local apps price at roughly 1/5 of that. A free core with copy, saved meals and search, plus paid AI logging, is the common pattern.

### Gaps
- Vietnam-store localized prices for MFP, MacroFactor, Yazio and Cronometer were not collected. The Lose It! barcode paywall is not confirmed from an official source.

## 5. User praise and complaints

### Takeaway
Praise centres on MacroFactor's adaptive algorithm and verified data, and on Cronometer's accuracy and free barcode scanning. Complaints centre on MFP's paywalls and crowd-sourced errors, and on high subscription prices. Vietnamese-app reviews are few, with occasional reports of data loss.

### Cited Findings
- Users saw the MFP barcode paywall as removing "the feature that made counting calories easy". — [Slashdot/The Verge](https://news.slashdot.org/story/22/08/25/1955238/myfitnesspal-paywalls-barcode-scanner-that-made-counting-calories-easy)
- MacroFactor's verified database is positioned against MFP's unverified entries. — [MacroFactor](https://macrofactor.com/macrofactor/)
- MacroFactor's food log redesign drew 500+ feedback submissions and a 1,400-participant beta, a sign of a heavily engaged user base. — [MacroFactor](https://macrofactor.com/timeline-based-food-logger/)
- Caloer reviewers praise its Vietnamese food support but report data loss in some updates (72 ratings). — [App Store: Caloer](https://apps.apple.com/us/app/caloer-t%C3%ADnh-calo-gi%E1%BA%A3m-c%C3%A2n/id6474173293)
- Recurring requests on the Cronometer forums for copy/paste meals and label scanning show re-entering repeat meals is a common pain point. — [Cronometer forum](https://forums.cronometer.com/discussion/5014/feature-request-scanning-food-labels-to-create-custom-foods-copying-pasting-meals)

### Inferences
- The tedium of repeated entry and paywalled shortcuts drive abandonment. A lazy-tracker design should make the repeat path (planned meal → confirm) free and as close to one tap as possible.

### Gaps
- I could not reach Reddit (r/loseit, r/MacroFactor) threads directly, so there are no direct user quotes. I also could not access Vietnamese Facebook gym/eat-clean groups.
