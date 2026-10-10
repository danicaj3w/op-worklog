# Artist Study App — Technical Design Document

**Scope:** Phase 1 MVP, targeted for delivery in under a week
**Audience:** Solo dev (self)

---

## 1. Overview

A web app for self-taught hobbyists to structure their own study practice. Phase 1 delivers the minimum feature set needed to have a usable, single-user version of the app live. Phase 2 features are listed separately at the end for future reference — not in scope for this build.

---

## 2. Tech Stack

| Layer | Choice |
|---|---|
| Frontend | React + Vite + TypeScript + Tailwind |
| Backend / DB | Supabase (Postgres, Auth, Storage, Edge Functions) |
| Hosting | Vercel or Netlify |
| Mobile (future, not phase 1) | React Native (Expo) |

Backend architecture and schema decisions are intentionally left out of this document — that's the part you're figuring out yourself.

---

## 3. Phase 1 MVP Features

The goal is the smallest set of features that makes the app functional and usable end to end.

### Auth
- Single-user (or small tester group) login via Supabase Auth
- Protected routes so the app isn't publicly accessible

### Streak Tracker
- Stopwatch/session logging
- Streak counter tied to logged sessions
- Basic handling for missed days / timezone edge cases

### Roadmap Tool (manual only)
- Create, edit, delete tasks
- Each task has: title, tag, due date, completion checkbox
- List or board view
- No AI generation — fully manual for phase 1

### Resource Quick Access
- Add, edit, delete saved links
- Basic icon/favicon handling
- Simple grid layout

### App Shell
- Basic navigation/layout connecting the above into one dashboard
- Empty and loading states for each section

---

## 4. Explicitly Out of Scope for Phase 1

- AI-assisted roadmap generation
- Spaced repetition logic
- Adaptive rescheduling / "life mode" toggle
- Pomodoro timer, reps tracker
- Topic/prompt randomizer
- Reflections/journaling tool
- Gamification, visual customization
- Mobile port

---

## 5. Phase 2 Features (for later reference)

- **AI-assisted roadmap generation** — LLM-generated draft plans, treated as editable drafts rather than final schedules
- **Spaced repetition engine** — active recall integrated with roadmap items
- **Adaptive rescheduling** — explicit "life mode" toggle (busy/normal/crunch) rather than AI-inferred state
- **Pomodoro timer & reps tracker** — additional progress-tracking modes beyond stopwatch
- **Per-feature toggle preferences**
- **Topic/prompt randomizer** — themed drawing prompts, community + customizable
- **Reflections tool** — journaling/retro notes linked to roadmap items or tracked sessions; potential double-use as retrieval-practice material alongside spaced repetition
- **Gamification & visual customization**
- **Mobile port** — React Native/Expo, sharing logic with the web app
