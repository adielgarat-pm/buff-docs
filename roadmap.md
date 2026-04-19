# BUFF Roadmap

_Living document — April 19, 2026_

---

## Status Legend

- 🟢 **Done** — Shipped and tested
- 🟡 **In Progress** — Being built now
- 🔴 **Critical Before May 1** — Must ship before public launch
- 🔵 **Planned** — Scheduled for post-launch
- ⚪ **Parked** — De-prioritized, may revisit

---

## Current Sprint (April 19)

### 🔴 Must ship before May 1

- [ ] Bag Prep / GearMaster (Phase 5)
- [ ] App icon — new gaming design (#4 variant)
- [ ] Privacy Policy hosted and linked in Play Console
- [ ] Medical disclaimer in all AI-related screens ✅
- [ ] Value First Flow (login after onboarding)
- [ ] Fix LanguagePicker in UStep1
- [ ] Fix family code lookup for children
- [ ] Avatar picker — 10 mascots instead of egg placeholder

### 🟡 In Progress
- Timetable Phase 5 (Bag Prep) — Claude Code planning
- Icon deployment — pending build

---

## Recently Shipped (April 15-19)

### 🟢 Auth & Navigation
- Role-based auth flow (RoleSelectionScreen)
- ChildJoinScreen — simplified (username + code only)
- WelcomeScreen — value-first intro before onboarding
- RootNavigator — child never sees onboarding

### 🟢 Timetable Feature (Phases 1-3)
- Supabase schema (timetables, lesson_progress, lesson_reflections)
- Hooks (useTimetable, useLessonProgress)
- TimetableScreen with 3 import methods (Excel, Image/OCR, Manual)
- parse-schedule Edge Function (Claude Haiku 4.5 + Sonnet 4.6)

### 🟢 Philosophy Integration
- DisclaimerFooter component (short + full variants)
- AboutScreen (6 Pillars, 4 Principles, Terminology)
- PhilosophyTip component with 3 contextual tips

### 🟢 Infrastructure
- Production build live in Google Play Internal Testing
- RevenueCat production key configured
- Google Service Account linked

---

## Deferred to Post-Launch

### 🔵 Planned
- i18n for DB content (title_en/title_he in tasks and store_rewards)
- Grid layout for rewards (2 per row)
- Progress bar in rewards ("X Buffs to reward")
- "View as Child" icon next to child name in dashboard
- Google OAuth (email/password works for now)
- Option B invite deep link (buff://join/:code)
- Placeholder insights ("Most popular mission this week?")
- Founding Members flow
- App Store / iOS submission

### ⚪ Parked — may revisit
- School Quest (lesson attendance checkboxes) — complexity without proven value
- Manual timetable creation from scratch — Excel + Image cover 95% of cases
- AI-generated avatars — using fixed SVG collection instead
- Dynamic AI task/reward generation — needs ~1000 families of data first

---

## North Star Features (Q3 2026+)

- **AI-powered mission engine** — Learn per child, suggest optimized missions
- **Family insights dashboard** — Multi-child comparison, trends over time
- **School integration** — Direct import from school systems
- **Therapist companion** — Professional view for therapists working with families

---

## Key Technical Facts

```
Project: buff-mobile (React Native Expo)
Package: com.buffapp.mobile
Backend: Supabase (gfrongfnyigxsexuofrg)
Subscriptions: RevenueCat (production)
Languages: Hebrew, English
Min Android: Android 6+ (API 23)
```

### Naming conventions (don't break)
- `tasks.assigned_to` (not `child_id`)
- `store_rewards.child_id`
- Children NEVER see WelcomeScreen or UStep screens
- `isOnboarded = hasFamilyId && onboardingComplete && hasChildren`
