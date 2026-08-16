# Smart PLE — Upper Primary Practice App
### UI/UX prototype (no academic content)

**File:** `ple-app/index.html` — one self-contained file. No internet, no build step, no dependencies. Opens on any phone or laptop browser and works offline.

---

## Screens built (14)

| # | Screen | Notes |
|---|--------|-------|
| 1 | **Home** | Greeting + avatar, big **Continue Practice** card with progress, 4 large tiles (Practice / Past Papers / Topics / My Progress), offline strip |
| 2 | **Practice** | "Choose Practice" → Quick, Topic, Mixed, Exam. Icon + title + one short line each |
| 3 | **Subject selection** | 2-up grid (3-up on tablet), big icon + name + % done |
| 4 | **Topic selection** | Vertical cards: topic name, % , progress bar, questions practised, offline badge |
| 5 | **Question** | Question x of y + progress bar, big question card, 4 tall answer buttons (68px) |
| 6 | **Answer feedback** | Bottom sheet: 🎉 "Well done!" / 💡 "Good effort!" — never "wrong/failed" |
| 7 | **Results** | Emoji hero, animated count-up %, score fraction, 4 stat tiles, confetti |
| 8 | **Review answers** | Per-question correct/try-again with the right option shown |
| 9 | **Past Papers** | List with subject, question count, duration, offline + best-score pills |
| 10 | **Paper detail** | Title, subject, questions, time allowed, one **START EXAM** button |
| 11 | **Exam confirm** | Simple sheet: 3 facts + Start / Not yet |
| 12 | **Exam question** | Live countdown timer, back/next, visible **SUBMIT EXAM**, no distractions |
| 13 | **Progress** | Donut, 4 mini-stats, weekly bar chart, per-subject bars, recent activity, badges |
| 14 | **Profile** | Avatar, name, class, 3 stats + Change avatar / Offline content / Settings / About |

Plus: avatar picker, offline manager, settings (2 toggles only), about, quit/submit confirmation sheets, toasts.

---

## Design decisions

- **One obvious action per screen.** The primary button is always the biggest, most saturated element.
- **Touch targets:** minimum 60px; answer rows 68px; nav tabs full-height.
- **Type:** system UI font (loads instantly, no CDN). Questions 21px/800, answers 17.5px/700, nothing important below 12.5px.
- **Colour is never the only signal.** Correct = green + ✓ icon + "Well done!"; try-again = amber + ✕ icon + text. Offline = green pill + download icon + the word "Offline".
- **Palette:** one blue primary, plus green/amber/violet used only as subject identity. Bright, not noisy.
- **Navigation depth is flat:** Home → Practice → Subject → Topic → Question → Next. Bottom tabs are always one tap away; no hamburger anywhere.
- **Auto-advance:** 1.4s after a correct answer, 2.4s after a miss (extra time to read the feedback). A NEXT button is always there too, and the behaviour can be turned off in Settings.
- **Exam mode is deliberately plainer** — no feedback, no celebration, just question, timer, progress, submit.
- **Responsive:** mobile-first single column → 3-up grids at 760px → floating device-style card at 1024px. Bottom nav stays.
- **Motion:** all under 450ms, and fully disabled under `prefers-reduced-motion`.

## Placeholders
Every question, answer, topic and paper name is deliberately generic ("Answer option B", "Topic 3 · Placeholder", "Practice Paper 1"). Swap the `SUBJECTS`, `MODES`, `PAPERS` and `topicsFor()` data blocks at the top of the script for real content later — no layout changes needed.

## Try it
- Home → **CONTINUE** → answer with taps (or keys A/B/C/D on desktop) → finish → Results → Review
- Papers → any paper → **START EXAM** → timer runs → **SUBMIT EXAM**
- Profile → Change avatar / Offline content
