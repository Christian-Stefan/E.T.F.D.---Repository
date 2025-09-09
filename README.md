# Website Content Mirror — Repository Guide

This repository mirrors the **top-level navigation** of the website so that anyone browsing the codebase can find content in the **same order and wording** they see in the site’s menu.

> **Important:** This repo is an organizational mirror of the site’s structure. It is **not** the running website.

---

## 1) Purpose

- Provide a **clear, predictable folder hierarchy** that matches the site’s menus and sub-menus.
- Make it easy for contributors to locate or propose content for a specific page/section.
- Serve as a **history** of edits and proposals via Git.

**Bold caution:** Designing a repository **by presentation (menu order)** is convenient for editors, but it can be brittle if the site navigation changes. See **§7 Risks & Limits**.

---

## 2) Structure Overview

The root folders correspond 1:1 with the items in the website’s **Students** drawer (and other menu tabs, if applicable). Example (abbreviated):

    .
    ├── Collaborative Initiatives/
    ├── Courses/
    ├── Graduation Project/
    ├── Internships/
    └── Set Programs/

Within each top-level section, you may create subfolders that correspond to sub-pages or content blocks on the site. Keep the on-screen order by prefixing with two-digit numbers if needed (e.g., `01-Overview`, `02-Guidelines`) to preserve sorting without renaming titles.

---

## 3) Design Principles

1. **Same names, same order:** Folder names match the visible labels on the site.
2. **Minimal friction:** Browsing this repo should feel like browsing the website menu.
3. **Human-first:** Favor readable names over cryptic slugs inside folder names; use slugs inside files if needed.

---

## 4) What Goes in Each Folder (recommended)

Inside each section or sub-section folder:

- `README.md` — human-readable overview of that section (purpose, audience, owners).
- `index.md` — proposed or canonical text for the page.
- `media/` — images or documents referenced by the markdown (keep originals here).
- `meta.yaml` (optional) — owners, update cadence, and source URLs.

Example:

    Courses/
    ├── README.md                 # section overview and rules of use
    ├── index.md                  # page content or draft
    ├── media/
    │   └── course-grid.png
    └── meta.yaml                 # owner: Faculty Office, review: quarterly

---

## 5) How to Contribute

1. **Find the matching folder** for the page you’re working on.
2. **Edit `index.md`** (or add it if missing). Keep links relative (e.g., `media/image.png`).
3. **Add media** to the local `media/` folder, not to the repo root.
4. **Commit message format:**  
   `Section: short action — detail`  
   Examples:  
   - `Courses: update prerequisites — clarified ECTS rules`  
   - `Internships: add partner list — Fall 2025`
5. **Open a PR** describing which site page your change maps to.

---

## 6) Mapping to the Website

- Each top-level folder mirrors a menu item.
- Each subfolder mirrors a sub-page or expandable drawer item.
- If a page exists on the site but **not** here, create a folder with the *exact* visible label.
- If the site label is long, you may keep the folder readable (same text) and add a slug in `meta.yaml` (e.g., `slug: graduation-project`).

---

## 7) Risks & Limits (read this)

- **No automatic sync:** There is **no fetch or sync mechanism** between this repository and the live site. **Changes here do not deploy** and **site changes will not magically appear** in this repo.
- **Navigation drift:** If the website menu changes (labels, order, nesting), this mirror can drift. **When the site changes, update the folders immediately** (rename/move with Git to preserve history).
- **Binary bloat:** Large files (videos, archives) should **not** live in Git. Store them in object storage and link from markdown.

**Bold caution:** Treat this repo as the **source of truth for editorial intent**, not as a backup of the running website’s code or database.

---

## 8) Workflow We Expect

1. Draft or edit content in the appropriate folder.
2. Submit a PR; reviewers focus on clarity, accuracy, accessibility, and link hygiene.
3. Once merged, the website editor/developer **manually** ports approved changes into the CMS or codebase.
4. Add a short note in the PR description like:  
   `Ported to site on YYYY-MM-DD — URL: /students/courses`

---

## 9) Naming & Formatting Conventions

- **Titles:** Sentence case in markdown (`# Course catalog`), keep folder names matching site labels.
- **Links:** Prefer relative paths; avoid absolute links to the repo.
- **Images:** Use descriptive filenames (`lab-schedule-2025.png`), include alt text in markdown.
- **Tables:** Use markdown tables; keep them narrow for readability.

---

## 10) Ownership & Review

- Each top-level folder should list **content owners** and **review cadence** in `meta.yaml` or the folder `README.md`.
- Suggested cadences:
  - Courses — each term
  - Internships — monthly during application windows
  - Graduation Project — pre-semester + mid-semester
  - Set Programs & Collaborative Initiatives — quarterly

---

## 11) Roadmap (nice to have)

- Add a `SITEMAP.md` that lists every folder → site URL mapping.
- Introduce labels (e.g., `needs-sync`, `outdated`) for PRs/issues.
- Optional CI that lints markdown (links, headings, alt text) to keep quality high.

---

## FAQ

**Q: Does this repo back up the live site?**  
**A:** No. It mirrors structure and stores text/media drafts. The site’s code, database, and uploads live elsewhere.

**Q: Why mirror menu order instead of domain taxonomy?**  
**A:** It reduces cognitive load for editors. **Trade-off:** more maintenance when the menu changes (see §7).

**Q: Can we auto-pull content from the site?**  
**A:** Not currently. There is **no fetch mechanism** to synchronize appearance, software, or content with these folders.

---

*Last updated: YYYY-MM-DD. Replace this line when you make structural changes.*
