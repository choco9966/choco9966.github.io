# Compact News + Publications Selected/All

## Context

Comparing the site against https://minstar.github.io/ surfaced two readability/structure gaps:

- **News** used bordered, padded card-style list items with an absolutely positioned date column — much heavier than minstar's dense, single-line `**date.** description` format.
- **Publications** only offered a full year-grouped list. minstar splits this into a **Selected** view (a handful of curated highlights) and an **All** view (everything), toggled by two plain-text tab links, so a visitor skimming the page sees the highlights first without scrolling past every entry.

## Design

**News**: flat `<ul><li>` list, no borders/cards. Each entry is `**YYYY.MM.** description with inline links.` Bold date prefix, no separate date column.

**Publications tabs**: two links, `Selected` / `All`, styled as plain text with an active-state underline in green (matching the site's existing green accent used on the Projects poster pages). Vanilla JS toggle (`showPubTab('selected' | 'all')`) shows/hides two `<div>`s — no framework, matching the rest of the site.

- **Selected** (3, newest first, flat — no year headers): SOLAR 10.7B → Open Ko-LLM Leaderboard (ACL 2024) → SAAS. Same `.pubs` list markup as today.
- **All**: unchanged — today's full 13-entry, year-grouped list (`<h3>` per year), hidden by default.

Color: the tab active-state and any accent for this feature use **green**, not the site's default blue `--accent`, consistent with the Projects poster pages.

## Verification

Playwright at desktop + ~390px mobile width: `scrollWidth === clientWidth`, no console errors, no broken images, toggle switches both panels' visibility correctly.

## Process

1. Branch `compact-news-publications` (already created) + GitHub Issue documenting the two gaps and this checklist.
2. Implement News compaction (done) and Publications tabs (green).
3. Verify, commit, push, open PR referencing the issue.
