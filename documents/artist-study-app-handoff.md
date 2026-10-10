# Skill Study App — Project Handoff

**Status:** Planning done, ready to build
**Time:** ~10 hrs/week, solo

---

## 1. Concept

A small web app (mobile later) that helps self-taught learners stay consistent while learning a subject on their own. It's aimed at the core problem of self-learning: breaking down a complex topic such as art or programming and sticking with it over time.

**Design goals:**
- **Minimal setup:** start practicing within a minute. The default app is small, with no long onboarding or required configuration.
- **Flexible by design:** features are modules the user turns on and off as their needs change, not a fixed bundle shown upfront.
- **Consistency without pressure:** small sessions count, and missed days are never punished.
- Light rewards only, no heavy gamification.

**Toggleable modules (examples):**
- Streak tracker
- Quick links to resources
- Pomodoro timer
- Contribution graph
- Journal and reflections
- Prompt randomizer
- Spaced repetition

Each learner builds the setup that supports their own goals. A feature that helps one person stays out of the way for someone who doesn't need it.

---

## 2. Inspirations and Competition

**Why this app**
- No app combines a roadmap, practice sessions, progress tracking, and prompts for learning a skill. This is open space.
- Self-taught learners mix many tools and lose track. Music practice apps (Modacity, Pract.is) show learners want a timer, lists, notes, and tracking in one place.
- Users need a flexible ecosystem. This app lets users toggle features on as they need them instead of showing everything upfront.
- Most productivity apps are built for tasks, not long-term skill planning and learning. Many feel heavy or punish missed days, which drives users away.
- This app: one place to plan, practice, and see progress for any skill. Lightweight, flexible, no shame, and cozy.

**Art study tools**
- **Sketch a Day:** daily prompt, streak, and community. Closest competitor. Users complain about shallow prompts, fixed streak settings, and paywalled core features. Avoid these.
- **Drawabox, Proko, Ctrl+Paint:** structured lessons. No planning or progress tracking.
- **Notion:** DIY study plans shared by communities. Flexible but slow to set up and easy to abandon. The goal is Notion-level flexibility without the setup cost.
- **Line of Action:** free timed gesture practice. Practice only, no tracking.
- **Prompt generators** (ArtPrompts.org, RandomlyFun, The Pigeon Letters): random word combos. Not personalized.
- **Anki:** some artists adapt it, but it's built for facts, not drawing practice.

**Productivity and Journaling apps**
- **Todoist:** fast, simple tasks. Inspiration for labeling commits with the task name.
- **Habitica:** gamified habits. Habitica and gamified Steam productivity apps show how gamification can get heavy. Keep rewards light.
- **Avva Health:** tracks the menstrual cycle alongside daily symptoms. Reference for the optional cycle overlay.
- **[Super Productivity](https://github.com/super-productivity/super-productivity)** clean organization of daily tasks and individual projects
- **[Kagelin](https://github.com/Achyuth072/kagelin)** simple study app example with habit/streak tracking, notes section
- **[Momo](https://github.com/jp1337/momo)** open-source example of a self-hosted solution.
- **[Apple Journal]** journal app for iPad.
- [Ruri Ohama](https://www.youtube.com/watch?v=U6O95TeUPZw)
- [Bullet Journal](https://www.youtube.com/watch?v=GDMmxmn-p8I)

**Design inspiration**
- **DdingDaily (띵또뽀모도로):** pomodoro, schedule, and checklist with stickers, themes, and a "did great today" stamp. The cozy feel to aim for.
- https://www.postype.com/en/@wl0001131/post/23299677?utm_source=link&utm_medium=social&utm_content=if_sh_wl&utm_campaign=post
- https://www.postype.com/en/@cookids/post/21721998
- https://www.postype.com/en/@c-20220819ls/post/23096886

**Reward ideas**
- Palette sets
- Custom image and sticker sets added through a community

---

## 3. Tech Stack

- **Web:** React + Vite + TypeScript + Tailwind
- **Backend:** Supabase (database, login, storage)
- **Hosting:** Vercel or Netlify
- **Later:** React Native (Expo) for mobile. AI is called from a Supabase Edge Function, never from the browser.

**Architecture note:** build features as self-contained modules from the start. Store each user's enabled modules in a settings table so new modules can be added later without reworking the layout.

---

## 4. Costs

- Free during development.
- **AI:** pay per use. Limit usage per user from day one.
- **Images:** Supabase's free tier has 1 GB of storage. Set limits before adding image sharing.
- **Later:** domain (~$10–15/year), Apple Developer ($99/year), Google Play ($25 once).

---

## 5. MVP Checklist

- [ ] **Login** — for me and a small test group
- [ ] **Daily to-do list** — add tasks, inboxes, and recurring tasks
- [ ] **Timer/Progress tracker**
  - [ ] Stopwatch 
  - [ ] Pomodoro Timer with adjustable work time and break time
  - [ ] Records of time slots
- [ ] **Progress Journal** - easy to use, flexible journaling for progress tracking and goal planning
- [ ] **Subject Tracking**
  - [ ] Create, edit, and delete levels and benchmarks. No AI.
  - [ ] Track classes and projects.
- [ ] **Feature toggles** — a settings page to turn MVP modules on and off. New users start with a minimal default set.

**Not in MVP:** Spaced repetition, prompt randomizer, rewards and unlockables, theme customization, mobile.

**Rules to keep in mind:**
- Sessions are the main record. The graph and future features build on them.
- Every feature beyond the core (roadmap, sessions) should be toggleable.
- Setup stays minimal: a new user should reach their first session without configuring anything.

---

## 6. Timeline (~9 weeks)

| Week | Focus |
|---|---|
| 1 | Setup: repo, Supabase, database schema (including user settings for modules), deploy |
| 2 | Login and modular app layout |
| 3 | Roadmap: create, edit, delete tasks |
| 4 | Roadmap: checkbox, filters, sorting |
| 5 | Daily to-do list |
| 6 | Stopwatch and saving sessions |
| 7 | Contribution graph and commits |
| 8 | Dashboard, feature toggle settings, and polish |
| 9 | Buffer: testing and fixes |

---

## 7. Phase 2

All Phase 2 features ship as optional modules the user can toggle on or off.

**Progress Tracker**
- Contribution graph: commit a finished session to fill that day's square (one solid color), labeled with the task name
- Empty days stay neutral (no red, no "missed")
- Streak tracker (off by default): adjustable rules such as practice days per week and allowed rest days, so a missed day doesn't reset progress

**Learning support**
- AI roadmap (editable draft) with "make this smaller"
- Spaced repetition (daily cap, spreads out overdue reviews)
- Prompt randomizer with "pick fun idea for me"
- Check-in: life mode for the week (busy/normal/crunch), energy for the day
- Rest days and logging past days
- Weekly/Monthly/Yearly goals
- Optional cycle overlay (off by default, private, deletable)

**Tools**
- Resource Quick Access: save, edit, and delete links with icons

**Customization**
- Feature toggles for every module, with starter presets (e.g. "Just a timer", "Structured study")
- Themes with presets
- Skill colors on the graph
- Desk/scrapbook dashboard with stickers
- Share themes and images as one bundle, with clear docs (like Pixquare)

**Rewards**
- Unlock theme palettes
- Community artwork as stickers and stamps