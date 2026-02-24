# Shmaya Makes It Tasty (שמאיה עושה לכם טעים)

Single-page Hebrew (RTL) website for a food/experience business in Pardes Hanna, Israel.

## Commands

- No build tools, frameworks, or package managers
- Open `index.html` directly in a browser (`open index.html` on macOS)
- No test runner, linter, or type checker — this is a static HTML/CSS/JS site
- Validate HTML: `npx html-validate index.html` (optional, requires Node.js)

## Architecture

- `index.html` — Single file containing all HTML, embedded CSS, and embedded JS
- `images/business/` — Business logo (1 image)
- `images/tali/` — Tali (Indian thali) gallery photos (5 images)
- `images/suflaki/` — Souvlaki gallery photos (5 images)
- `content.txt` — Raw text content from the business owner
- `PLAN.md` — Detailed site plan with section specs, design, and image mappings
- Note: No images yet for "טיולי יער" and "אירועי חברה" sections

## Code Style

- **Language:** HTML5 + CSS3 + vanilla JS (no frameworks, no build tools)
- **Direction:** RTL (right-to-left) — all layout must respect `dir="rtl"`
- **HTML:** Semantic elements (`<section>`, `<nav>`, `<header>`, `<footer>`)
- **CSS:** Embedded in `<style>` tag; mobile-first responsive design
- **JS:** Embedded in `<script>` tag; vanilla JS only, no libraries
- **Fonts:** Google Fonts — Heebo or Assistant (Hebrew-friendly)
- **Naming:** Kebab-case for CSS classes, camelCase for JS variables
- **Images:** Clean short names (e.g., `tali-1.jpeg`, `suflaki-3.jpeg`, `logo.jpeg`)
- **Encoding:** UTF-8 for Hebrew text support

## Workflow

- Open `index.html` in browser to test changes
- Test on both desktop and mobile viewports
- Verify all links work (Waze, Instagram, Facebook, WhatsApp)
- Verify RTL layout renders correctly
- Check image loading and gallery scroll behavior
- Conventional commits: feat:, fix:, refactor:, chore:, docs:
- Branch naming: feature/<name>, fix/<name>

## Task Board (MANDATORY)

If MCP task board tools are available, you MUST use them to track all work:

- `list_tasks` — List all tasks (optional status_filter: pending/in_progress/for_review/done)
- `create_task` — Create a new task (title required, description optional)
- `update_task_status` — Move task between columns (task_id, status)
- `get_task_details` — Task details + status change history

**Workflow:**
1. BEFORE starting work: move the task to `in_progress`
2. AFTER completing work: move the task to `for_review` (NOT `done`)
3. If no task exists yet, `create_task` first, then move to `in_progress`

NEVER move tasks straight to `done`. Only the user moves tasks to `done` after reviewing.

## Available Commands

- `/session-start` — Load context, suggest work
- `/wrap-up` — End-of-session cleanup
- `/catchup` — Branch changes, build health
- `/pr` — Full PR workflow
- `/ship-check` — Pre-release readiness

## Instruction Precedence

1. **CLAUDE.md** (this file) — project-specific rules
2. **MEMORY.md** (`~/.claude/projects/-Users-orperelman-moms-website/memory/MEMORY.md`) — learned gotchas
3. **`.claude/rules/`** — path-scoped rules

If there's a conflict, the most specific instruction wins.

## Session Wrap-Up

At the end of every session, you MUST:

1. **Verify** — Open index.html in browser, check for visual issues
2. **Update TODO.md** — Mark completed items as [x], add new items
3. **Update CLAUDE.md** — If architecture, commands, or conventions changed
4. **Write NEXT-SESSION.md** — What was completed, in progress, blocked, key context
5. **Update MEMORY.md** — Record gotchas, patterns, lessons

Do NOT skip any step. Work is NOT complete until docs reflect reality.

## Critical Rules

- NEVER commit .env or credential files
- NEVER force-push to main/master
- All text content MUST be in Hebrew
- All layout MUST be RTL
- Keep everything in a single index.html file (CSS and JS embedded)
- Images use relative paths from index.html
- No external JS/CSS libraries (except Google Fonts)
- Mobile-first responsive design is required
- Test Waze/WhatsApp/social links before shipping

## Current State

Project is in planning phase. PLAN.md has the full spec. Image files exist in `images/business/`, `images/tali/`, and `images/suflaki/`. No images for forest walks or company events yet. The `index.html` file has not been created yet. Image filenames need renaming from WhatsApp defaults to clean names (see PLAN.md for mapping).
