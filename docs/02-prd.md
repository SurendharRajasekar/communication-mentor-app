# Product Requirements Document (PRD)

**Status:** Locked v1.0
**Phase:** 2 of 19 — PRD
**Depends on:** `01-product-vision.md`

## Platform & Scope Decisions
- **Platform:** Android first (Flutter, single codebase). iOS expansion after MVP validates.
  Rationale: primary ICP (India-first, career-driven professionals) skews Android; removes Mac/Apple Developer Program friction for a solo builder; faster Play Store review for early beta iteration.
- **Monetization:** Not decided for v1 — deferred until the core loop validates. Data model should leave room for a future "tier" field so this isn't a costly retrofit later.
- **Core input:** Voice only. Text-first was considered and rejected — it would validate a different product (answer-planning) rather than the actual problem (speaking under pressure).

## MVP Core Loop
User gets a scenario prompt ("Tell me about a time you handled conflict at work") → records a voice response → speech is transcribed → AI mentor gives structured feedback → session is logged → mentor references it in the next session → streak/XP increments.

## Functional Requirements (v1)
1. Authentication (Firebase — email/social sign-in)
2. Scenario library — curated prompts, tagged by category (interview / meeting / client call)
3. Voice recording + playback (review before submit)
4. Speech-to-text transcription pipeline
5. AI mentor feedback engine (structure, clarity, filler words — e.g. STAR-method adherence for interview prompts)
6. Session memory — transcript + feedback persist and are retrievable in the next session
7. Basic gamification — streak + XP only (no quests/leaderboards/achievements in v1)
8. Simple progress view — streak, sessions completed, recurring growth areas

## Non-Functional Requirements
- Android-first, Flutter, single codebase
- Feedback latency target: under ~15–20s — the loop needs to feel like a coach, not a batch job
- **Voice recordings are sensitive personal data.** Requires an explicit retention/deletion policy and clear user consent, to be defined before Phase 8 (Database Design)
- Graceful offline handling for recording (submission can queue)
- No architecture choices that block future scale, even though v1 doesn't need to scale yet

## Out of Scope (v1)
- Leaderboards, quests, achievements (beyond basic streak/XP)
- iOS app
- Payments/billing infrastructure
- Admin dashboard
- Non-English language support
- Social/group features

## MVP Acceptance Criteria
A user can:
- Sign up / log in
- Receive a scenario prompt
- Record a voice response
- Receive structured AI feedback within ~15–20 seconds
- See their streak increment
- Return the next day to a mentor that references the previous session

This is the definition of "MVP done."
