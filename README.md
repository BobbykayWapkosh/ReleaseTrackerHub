# ReleaseTrackerHub

**A clean control panel for tracking music releases — without the noise.**

ReleaseTrackerHub helps you manage submissions, statuses, and release timelines across Spotify, Apple Music, Audiomack, YouTube, Boomplay, and more — all in one place. No accounts. No sign-ups. No tracking. Your data stays on your device.

---

## What It Is (and Isn't)

Built for music distributors, A&Rs, PR managers, labels, and artists managing their own releases.

| It IS | It is NOT |
|---|---|
| A release control panel | A distributor (use DistroKid, TuneCore, etc.) |
| A submission tracking system | A streaming analytics dashboard |
| A clear view of your release pipeline | A cloud SaaS |

---

## Features

### Core Tracking
- Track releases across unlimited platforms
- Status flow: **Submitted → Live → Rejected → Delayed**
- Platform analytics with interactive charts
- Duplicate prevention on add, edit, and import
- Search by title, artist, platform, status, or ID
- Date-based highlights for today and tomorrow

### Data Management
- LocalStorage persistence — fast and private
- CSV import & export with permanent unique release IDs
- Automatic duplicate skipping on import
- Undo delete (7-second window)
- Inline editing with cancel
- Collapsible notes per release (exports with CSV)

### Experience
- Dark / Light mode
- Fully responsive
- Color-coded platforms
- Toast notifications
- Click-to-copy release IDs
- Keyboard shortcut — press `/` anywhere to jump to the form

---

## Getting Started

Open the app and start adding releases. Everything saves automatically to your device.

**No setup. No downloads. No accounts required.**

### CSV Import & Export
- Exports include permanent release IDs
- Imports support old and new CSV formats
- Missing IDs are auto-generated on import
- Duplicates are skipped automatically with a summary (e.g. *"Imported 5, skipped 2 duplicates"*)

### Privacy
- All data lives on your device — nowhere else
- No external servers, no tracking, no analytics
- Clearing your browser data removes your data — export first

---

## Changelog

### Bug Fixes

**Platform Normalization**
Added `normalizePlatform()` so "Spotify", "SPOTIFY", and "spotify" all map to the same entry. `formatPlatform()` handles proper display casing (Apple Music, YouTube, SoundCloud, etc.). Normalization runs on form submit, inline edit, and CSV import — fixing phantom duplicates in charts and duplicate checks.

**CSV Parsing**
Replaced the broken `row.split(',')` with PapaParse so titles like *"Song Title, Remix"* now import correctly. Added row filtering to silently skip malformed or empty rows.

**Date Input**
Removed the iOS `::before` pseudo-element hack that broke on Safari. Replaced with a proper `<label for="date">` tied to the input for accessibility.

**ID Generation**
Upgraded from `Date.now() + Math.random()` to `crypto.randomUUID()` with a fallback for older browsers.

---

### New Features

**Platform Datalist**
The platform field now suggests 13 common platforms (Spotify, Apple Music, Audiomack, Boomplay, YouTube, YouTube Music, SoundCloud, Tidal, Deezer, Amazon Music, TuneCore, DistroKid, UnitedMasters). Free typing is still allowed — it's a suggestion, not a lock.

**Notes Per Release**
Every release card has a collapsible notes section, collapsed by default so cards stay clean. A green dot appears on the toggle when a note exists. Notes export and import with CSV.

---

### UI Upgrades

**Typography**
Switched to Inter via Google Fonts. Tighter letter-spacing on headings. Stats bar now shows large bold numbers with small labels — proper dashboard feel.

**Cards**
Subtle green top-border slides in on hover. Spring-physics hover animation (`cubic-bezier(0.34, 1.56, 0.64, 1)`). Card info uses a `label + value` layout.

**Form**
Lives inside a card container with a "New Release" section label. Keyboard shortcut hint displayed with a styled `<kbd>` badge.

**Filters**
Pill-shaped filter buttons instead of square. Search bar has an embedded SVG icon.

**Toasts**
Completely redesigned — dark background, green left accent border, slides up from bottom with a spring bounce.

**Shadows & Depth**
Three-tier shadow system (`--shadow-sm`, `--shadow-md`, `--shadow-lg`) applied consistently across cards, form, chart, and stats.

**Dark Mode**
Deeper dark background (`#0b0f1a`) and card (`#111827`) — less flat than before.

---

### Micro UX

- **Auto-focus after submit** — cursor jumps back to the Track Title field immediately, no clicking required
- **Keyboard shortcut** — press `/` from anywhere to focus the form (won't fire if you're already typing)
- **Confirm before delete** — dialog reminds you that undo is available within 7 seconds

---

## Why I Built This

Managing releases across multiple platforms gets messy fast — especially when handling multiple artists or projects. ReleaseTrackerHub exists to bring clarity and structure to that process, without forcing you into another account-based system.

---

Crafted with ❤️ by [Bobbykay](https://lifeofbobbykay.name.ng)