# Gamification Design

**Status:** Locked v1.0
**Phase:** 6 of 19 — Gamification Design
**Depends on:** `01-product-vision.md`, `03-personas.md`, `05-feature-prioritization.md`

## Design principle
Priya trusts this app because it's private and judgment-free. Standard gamification mechanics — public leaderboards especially — can cut against that. Every mechanic here is chosen to serve retention without reintroducing the social anxiety the product exists to relieve.

## v1 Mechanics

### Streak
Simple daily counter. Increments on any completed session, in either mode. Resets if a day is missed. No streak-freeze/grace-period mechanic in v1 — real added complexity for a marginal early benefit.

### Confidence Meter (replaces XP)
A visual meter, not a raw number. Same underlying mechanic as XP — accumulates with each completed session — but reframed to match the product's actual value prop, with one deliberate design constraint:

**The meter only grows. It never depletes.** A literal video-game health/stamina meter that can drop after a bad session would punish exactly the vulnerability this product is meant to make safe. Session quality affects *how much* the meter fills — a strong session fills it more than a so-so one — but a rough session still adds something. Showing up always counts.

### Levels (cosmetic, no functional unlocks in v1)
Crossing meter thresholds moves the user through named tiers that mirror the coaching narrative:
`Getting Started → Building Confidence → Finding Your Voice → Confident Communicator`

The meter is visually the user's confidence growing toward the next stage — tighter thematic coupling than an abstract XP number mapping to an arbitrary label.

### The relationship itself
No separate mentor-leveling system needed in v1. The mentor referencing session history (already a Must-Have) is what makes the relationship feel like it's deepening — that mechanic is already doing real work without additional gamification layered on top.

## V2 Mechanics (deferred, with reasoning)
- **Streak freeze** — protect a streak once per week/month; worth the complexity once there's a real user base
- **Quests** — weekly goals across modes; more useful once there are more than two modes to balance
- **Achievements/badges** — milestone-based (7-day streak, first interview scenario, 10 sessions); cheap and purely additive later
- **Leaderboards** — held back deliberately, not just sequenced. If built at all: opt-in, small private cohorts (invite friends), never global rankings. A public ranking is in direct tension with "judgment-free" and needs a real design answer before shipping, not a checkbox.
