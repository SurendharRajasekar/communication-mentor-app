# API Design

**Status:** Locked v1.0
**Phase:** 9 of 19 — API Design
**Depends on:** `07-architecture.md`, `08-database-design.md`

All routes prefixed `/api/v1/`. All routes except health-check require a Firebase ID token (`Authorization: Bearer <token>`), verified via a FastAPI dependency.

## Endpoints

| Method & Path | Purpose |
|---|---|
| `POST /users/sync` | Upsert user by `firebase_uid` — idempotent, safe to call on every app launch |
| `PATCH /users/me` | Save onboarding answers (`onboarding_goal`, `comfort_level`) |
| `GET /scenarios/next?mode=` | Next recommended scenario for a mode, excluding ones already completed |
| `POST /sessions` | Core endpoint — see below |
| `GET /sessions?limit=` | Recent session list (session history view) |
| `GET /progress/me` | Current streak, confidence meter value, computed level |

## `POST /sessions`
Multipart request: `audio_file` + `scenario_id`.

```json
{
  "session_id": "uuid",
  "transcript": "...",
  "feedback": {
    "strengths": ["..."],
    "growth_areas": ["..."],
    "star_adherence_score": 78,
    "filler_word_count": 6,
    "mentor_note": "Last time you rambled through the setup — tighter this time."
  },
  "progress": {
    "current_streak": 5,
    "confidence_meter_value": 340,
    "current_level": "Building Confidence",
    "confidence_delta": 12
  }
}
```

## Key Decisions

### 1. Feedback and updated progress return in one response
The post-session screen needs both to render. One round trip means the client has a single source of truth for "what just happened," instead of feedback and streak/meter potentially arriving out of sync across two calls.

### 2. Rate limiting on `POST /sessions` via Redis
This is the one endpoint that costs real money per call (STT + LLM). A per-user request cap protects the AWS bill from day one — not something to bolt on after a surprise invoice.

### 3. Distinct error codes, not a generic 500
`422` for unprocessable audio, `503`/`504` if the AI pipeline times out. Lets Flutter show "couldn't hear that, try again" versus "something's wrong on our end" instead of one undifferentiated error screen.
