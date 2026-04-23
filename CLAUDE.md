# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Git workflow

After completing any meaningful unit of work, commit the changes AND push to GitHub immediately. Use clear, descriptive commit messages (e.g. `Add AI opponent with minimax algorithm`, not `update stuff`). Never leave significant work uncommitted — push frequently so progress is never lost.

## Internship search

- User is a 2nd year International Business student with a focus on Supply Chain Management
- Looking for an internship starting August or September 2026
- Dutch national, native Dutch speaker
- Location: Rotterdam region, Netherlands — open to anywhere within ~1.5 hours (covers most of the Netherlands incl. Amsterdam)
- Interests/target industries: aviation, sports, automotive, food, finance
- Special interest in EVs — grew up around it through father's work; highlight this in automotive applications
- All internship-related files go in the `Intership/` folder (always .xlsx format, close Excel before editing)
- Save any new internship info (companies applied to, documents created, etc.) back into this file and commit

## Internship progress (last updated 2026-04-23)

### Files created in `Intership/`
- `target_companies.xlsx` — 33 target companies across aviation, sports, automotive (incl. EV), food, finance
- `recruitment_contacts.xlsx` — 31 entries with career pages, LinkedIn tips, and real recruiter emails
- `application_tracker.xlsx` — tracker to log every application sent

### Specific openings found
- **Polestar** — Marketing & Events Intern, Beesd (Hybrid), Sep 2026, min 5 months. Needs driver's license. URL: https://polestar.teamtailor.com/jobs/7520907-marketing-events-intern
- **Adidas** — Intern Buying eCommerce, Amsterdam (Hybrid), Sep 1 2026, 5 months, EUR 1200/mo. Apply via portal only. URL: https://jobs.adidas-group.com/job/Amsterdam-Intern-Buying-eCommerce-NH/1383461633/

### Real recruiter contacts found
- **Unilever** — interns.benelux@unilever.com
- **Heineken** — werkenbijheinekennederland@heineken.com
- **Tesla** — hr@tesla.com / +31 85 482 2966
- **Feyenoord** — format: first.last@feyenoord.nl (find name on LinkedIn first)
- **Adidas** — career portal only, no email applications accepted

### Next steps
- [ ] Build CV
- [ ] Write motivation letter template
- [ ] Start reaching out to companies

## Running the project

Open `tictactoe.html` directly in a browser — no build step, server, or dependencies required.

## Architecture

The entire game lives in `tictactoe.html` as a single self-contained file:

- **HTML** — a 3×3 grid of `.cell` divs, a score display, and a restart button.
- **CSS** — dark-themed inline styles; winning cells get a `.win` pulse animation.
- **JavaScript** (inline `<script>`) — plain DOM manipulation, no frameworks or libraries.
  - `WINS` — array of all 8 winning index combinations.
  - `board` / `current` / `over` — the only mutable game state.
  - `scores` — persists across rounds (resets on page reload).
  - `init()` — resets board and DOM for a new round.
  - `checkWin()` — scans `WINS` and returns the winning triple or `null`.
  - Click listener on each cell drives all game logic; `updateScores()` syncs the score display.
