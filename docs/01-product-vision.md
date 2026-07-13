# Product Vision

**Status:** Locked v1.0
**Phase:** 1 of 19 — Product Vision

## Problem Statement
Skilled non-native and early-career professionals lose real opportunities — interviews, promotions, client trust — not because they lack expertise, but because they haven't had enough reps speaking under pressure. Existing tools don't fill this gap well: pronunciation apps (ELSA) drill sounds in isolation with no career context, and delivery-coaching tools (Yoodli) are built for enterprise sales teams, not individuals building a long-term communication habit. Nobody gives an individual a coach that remembers who they are and what they're working toward.

## Vision Statement (5–10 year horizon)
A world where anyone, regardless of accent or background, can walk into any interview, meeting, or high-stakes conversation with the confidence of someone who's had a career coach since college.

## Mission Statement (1–2 year horizon)
Give every user a personal AI mentor that learns their voice, tracks their growth across real career scenarios, and turns a few minutes of daily practice into a compounding habit — the way Duolingo turned language learning into a daily ritual.

## Target User (v1)
Career-driven, non-native-English-speaking professionals (India and similar markets as the initial wedge) who need to level up spoken communication for specific, high-stakes moments: interviews, client calls, stakeholder meetings, performance conversations.

**Explicitly not (v1):** casual public-speaking hobbyists, pure accent/pronunciation seekers, enterprise L&D buyers.

## Core Differentiator
Continuity. Not a scoring engine — an AI mentor with memory. It remembers the last session, adapts scenarios to the user's actual goals (an upcoming interview, a recurring client call), and its coaching style itself evolves as the user improves.

*Trade-off accepted knowingly:* this requires real cross-session memory and retrieval, not a stateless LLM call. Meaningfully harder than a bolt-on GPT wrapper — accepted because it's the differentiator and it directly showcases agentic AI engineering skills.

## Non-Goals (v1)
- Not a pronunciation/accent-reduction tool (ELSA's territory)
- Not an enterprise/L&D analytics platform (Yoodli's territory)
- Not a general language-learning curriculum (vocabulary/grammar)
- Not every gamification mechanic on day one — full feature cut happens in Phase 5

## North Star Metric
Weekly active practice rate + 4-week retention. This is a habit-formation product; retention *is* the product working.

## Competitive Landscape (snapshot)
- **Yoodli** — AI roleplay + delivery coaching (filler words, pacing, eye contact), enterprise/sales-leaning, thin gamification.
- **ELSA Speak** — phoneme-level pronunciation/accent AI, strong gamified habit loop, ~$13+/mo, doesn't address broader communication skills.
- **Duolingo** — owns habit-loop mechanics (streaks, XP, leaderboards), doesn't touch spoken communication.
- **The gap:** nobody pairs Duolingo-grade daily-habit gamification with real spoken-communication training and a persistent AI mentor, for this specific audience.
