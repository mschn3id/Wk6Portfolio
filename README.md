# Wk6Portfolio

Static portfolio site — HTML, CSS, and assets only. **No install, build step, or server required** to edit files. Open `index.html` in a browser to preview locally.

## Add a new project (recommended)

Use **Cursor Agent** and ask it to create a project page. Example prompt:

> Create a portfolio project page for **Recipe Finder**.

The agent should use the **portfolio-project-page** skill (see below). It will:

1. Create a project folder (e.g. `RecipeFinder/`)
2. Add `content.md` for you to fill in (or generate the page if content is ready)
3. Build `index.html` matching existing case studies (`TaskTracker/index.html`)
4. Add a card on the home page and footer links on `index.html`, `about/`, and `contact/`

### What you provide

| Item | Example |
|------|---------|
| Project folder | `RecipeFinder/` (PascalCase, no spaces) |
| `content.md` | Copy structure from `TaskTracker/content.md` |
| Cover mockup | `assets/RF_Mockup_desktop-mobile.png` |
| Journey screenshots | `assets/RF_Process_1.png`, `_2.png`, … |
| Demo video (optional) | `assets/RF_Video.mp4` |

Asset prefix = acronym of the folder name (`RecipeFinder` → `RF`). See `DESIGN.md` → **Portfolio Site Application** for layout and naming rules.

### Two-step workflow

1. **First ask** — Agent creates `content.md` with placeholders. Fill in overview, challenge, process, solution, user journey captions, features, and outcomes.
2. **Second ask** — *"Generate the Recipe Finder project page from content.md"* — Agent builds the HTML and updates the home page.

## If you lose the Cursor skill

Skills live in your Cursor account folder, not in this repo. To get the workflow back:

1. **Easiest:** Ask Cursor Agent: *"Read DESIGN.md and create a new project page for [name] following the same pattern as TaskTracker."* Point it at this repo.
2. **Reinstall the skill:** Copy the `portfolio-project-page` skill into `~/.cursor/skills/portfolio-project-page/` (from a backup or by recreating it from `DESIGN.md`).
3. **Manual fallback:** Duplicate `TaskTracker/`, rename files, edit `content.md` and `index.html`, then add a project card in root `index.html`.

## Preview and publish

- **Preview:** Open `index.html` in a browser, or use Cursor’s Simple Browser / Live Preview.
- **Publish:** Push to GitHub and deploy with Netlify, GitHub Pages, or any static host. No build command needed.

## Key files

| File | Purpose |
|------|---------|
| `index.html` | Home page + featured project grid |
| `DESIGN.md` | Design system and case study section order |
| `{ProjectName}/content.md` | Source copy for each case study |
| `{ProjectName}/index.html` | Generated case study page |
| `css/styles.css` | Shared styles for the whole site |
