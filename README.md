# ReleaseTrackerHub

A simple control panel for tracking music releases across platforms — without noise, clutter, or lock-ins.

ReleaseTrackerHub helps you keep track of submissions, statuses, and release timelines across Spotify, Apple Music, Audiomack, YouTube, Boomplay, and more — all in one place.

**No accounts. No sign-ups. No tracking. Your data stays on your device.**

---

## What is this?

ReleaseTrackerHub is a lightweight, privacy-first release tracking tool built for:

- Music distributors  
- A&Rs  
- PR managers  
- Labels  
- Artists managing their own releases  

### What it is NOT

- Not a distributor (you still submit via DistroKid, TuneCore, UnitedMasters, etc.)  
- Not a streaming analytics dashboard  
- Not a cloud SaaS  

### What it IS

- A release control panel  
- A submission tracking system  
- A clear view of your release pipeline  

---

## Features

### Core

- Track releases across unlimited platforms  
- Status flow: Submitted → Live → Rejected → Delayed  
- Platform analytics with interactive charts  
- Duplicate prevention (add, edit, import)  
- Search by title, artist, platform, status, or ID  
- Date-based highlights (today / tomorrow)  

### Data Management

- LocalStorage persistence (fast & private)  
- CSV import & export  
- Automatic duplicate skipping  
- Undo delete (7-second window)  
- Inline editing with cancel  
- Permanent unique release IDs  

### User Experience

- Dark / Light mode  
- Fully responsive  
- Color-coded platforms  
- Toast notifications  
- Click-to-copy release IDs  

---

## Getting Started

Open the app link and start adding releases. Everything saves automatically on your device.  

**No setup. No downloads. No accounts.**

### CSV Import & Export

- Exports include permanent release IDs  
- Imports support old and new CSV formats  
- Missing IDs are auto-generated  
- Duplicates are skipped automatically  

### Privacy

- All data stays on your device  
- No tracking or analytics  
- No external servers  
- Clear browser data = data removed (export first)  

---

## Why I Built This?

Managing releases across multiple platforms gets messy fast — especially when handling multiple artists or projects.  

ReleaseTrackerHub exists to bring clarity and structure to that process without forcing you into another account-based system.  


## What's New
What's Changed (Changelog)
🐛 Bug Fixes
Platform Normalization

Added normalizePlatform() — "Spotify", "SPOTIFY", "spotify" all map to the same entry now
Added formatPlatform() — displays properly cased names (Apple Music, YouTube, SoundCloud etc.)
Platform is normalized on form submit, inline edit save, and CSV import
Chart grouping and duplicate checks now use normalized names — no more phantom duplicates

CSV Parsing (Big One)

Replaced the broken row.split(',') with PapaParse — titles like "Song Title, Remix" now import correctly
Added row filtering to silently skip malformed/empty rows
Added detailed import feedback: "Imported 5, skipped 2 duplicates"

Date Input

Removed the iOS ::before pseudo-element hack that broke on Safari
Replaced with a proper <label for="date"> tied to the input for accessibility

ID Generation

Upgraded from Date.now() + Math.random() to crypto.randomUUID() with a fallback for older browsers


✨ New Features
Platform Datalist

Platform field now has a <datalist> with 13 common platforms (Spotify, Apple Music, Audiomack, Boomplay, YouTube, YouTube Music, SoundCloud, Tidal, Deezer, Amazon Music, TuneCore, DistroKid, UnitedMasters)
Free typing still allowed — suggestion only, not locked

Notes Per Release

Every release card has a collapsible notes section
Collapsed by default — cards stay clean
Green dot indicator on the toggle when a note exists
"Add note" label changes to "Note" once saved
Notes export and import with CSV (Notes column added)


🎨 UI Upgrade
Typography

Switched to Inter via Google Fonts across the whole app
Tighter letter-spacing on headings (-0.02em to -0.03em)
Stats bar now shows large bold numbers with small labels underneath — proper dashboard feel

Cards

Subtle green top-border line slides in on hover
Spring-physics hover animation (cubic-bezier(0.34, 1.56, 0.64, 1))
Card info uses <strong> label + value layout (Artist / Platform / Release Date)

Form

Form now lives inside a card container with a "New Release" section label
Press / keyboard shortcut hint displayed next to the label with a styled <kbd> badge

Filters

Pill-shaped filter buttons (border-radius: 999px) instead of square
Search bar has an embedded SVG search icon via background-image

Toasts

Completely redesigned — dark background, green left accent border
Slides up from bottom with spring bounce (cubic-bezier keyframe)

Shadows & Depth

Three-tier shadow system: --shadow-sm, --shadow-md, --shadow-lg
Cards, form, chart, stats all use consistent elevation

Dark Mode

Deeper dark background (#0b0f1a) and card (#111827) — less flat than before


⚡ Micro UX
Auto-focus after submit

Cursor jumps back to Track Title field immediately after adding a release — no clicking required

Keyboard shortcut

Press / from anywhere on the page to jump focus to the form (smart — won't fire if you're already typing in an input or textarea)

Confirm before delete

Dialog: "Delete 'Track Name'? You can undo within 7 seconds." — reminds users undo exists too

**Crafted with ❤️ by Bobbykay**
