# Feature Prioritization

**Status:** Locked v1.0
**Phase:** 5 of 19 — Feature Prioritization
**Depends on:** `01-product-vision.md`, `02-prd.md`, `03-personas.md`, `04-user-journey.md`

Framework: MoSCoW, plus one engineering principle layered on top — de-risk the biggest unknown first. Even within the locked MVP scope, build order determines whether a solo 3-month timeline survives contact with reality.

## Must Have (MVP cannot ship without these)
1. Authentication (Firebase — email/social)
2. Voice recording + playback
3. Speech-to-text pipeline
4. AI mentor feedback engine — Interview Practice scenarios only, to start
5. Session save + basic memory (mentor references the last session)
6. Streak + XP
7. Simple progress view

## Should Have (right after Must-Have works end-to-end)
1. Workplace Communication mode (second mode — cheap once the pipeline is shared and proven)
2. Onboarding personalization questions
3. Feedback engine tuning (structured STAR-method scoring, not generic notes)
4. Milestone check-in prompt

## Could Have (cut first if the timeline gets tight)
1. Scenario variety within each mode
2. Profile/settings customization
3. Detailed session history view (beyond aggregate progress)

## Won't Have (v1)
Random Topic Practice, Free Talk, leaderboards/quests/achievements, iOS, payments, admin dashboard, push notifications — see `02-prd.md` Out of Scope and Roadmap sections.

## Build Order (within the Must-Haves)
1. **De-risk the AI loop before touching Flutter.** Prototype record → transcribe → LLM feedback outside the app first, on Interview Practice scenarios only. If feedback quality isn't good, nothing downstream matters — find out in week one, not week ten.
2. **Backend skeleton + single-mode core loop, end-to-end in the real app.** Auth, DB, API, Interview Practice only, working start to finish.
3. **Session memory + gamification basics** wired in — mentor references history, streak/XP live.
4. **Second mode (Workplace Communication) + progress view + polish.**

This ordering produces a genuinely working, demo-able product after step 2 — not scattered pieces — which matters both for solo-builder morale and for showing real progress on the portfolio side.
