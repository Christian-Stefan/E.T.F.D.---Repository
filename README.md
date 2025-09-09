# Website Content Mirror — README

This repository mirrors the website’s **menu structure and order** (e.g., the *Students* drawer). Folder names and their sequence are **identical to the site’s tabs and sub-pages** so editors can find content where they expect it. This is **not** the live site.

## Structure (example)
    .
    ├── Collaborative Initiatives/
    ├── Courses/
    ├── Graduation Project/
    ├── Internships/
    └── Set Programs/
Create subfolders only when a matching sub-page exists on the site. If you must keep a specific sort order, prefix with numbers (e.g., `01-Overview`, `02-Guidelines`).

## How to use
1. Go to the folder that matches the page.
2. Edit or add `index.md` (page text).
3. Put images/files in `media/` and link relatively (e.g., `media/file.png`).
4. Open a PR that mentions the matching site page/URL.

## Limits (must know)
- **No synchronization/fetch mechanism exists.** Changes here **do not deploy**, and changes on the website **do not appear here automatically**—this includes the site’s **appearance**, **underlying software backbone**, and **page content**.
- This repo is for **editorial structure and content drafts**, not a backup of production code, database, or uploads.

*Last updated: YYYY-MM-DD.*
