# roadmap

A self-contained, single-file study tracker for moving from IT support into platform engineering.

**Live page:** https://nemoprecursor.github.io/roadmap/

The page is encrypted. Opening it without a passphrase shows a lock screen and nothing else — the content is not in the page source.

There are two passphrases. The owner's unlocks the full tracker. A guest one opens a read-only view: no ticking, no glossary tooltips, no calendar, no saved progress, and the owner's private notes omitted — not hidden with CSS, but absent from the ciphertext the guest passphrase can open.

---

## What it is

A 70-week plan running August 2026 to December 2027 at 5–7 hours a week, built against a real job posting: Y TREE's *Platform Engineer (Mid) – AWS, Kubernetes & IaC*, which names **Kubernetes, Terraform and AWS** as its requirements.

| Weeks | Stage | Ends with |
|---|---|---|
| 1–15 | CompTIA Network+ (N10-009) | Exam, 23 Nov 2026 |
| 16–29 | CompTIA Security+ (SY0-701) | Exam, 1 Mar 2027 |
| 30–44 | Linux, containers and your own infrastructure | Portfolio checkpoint, 10 May 2027 |
| 45–56 | AWS | Solutions Architect Associate, 6 Sep 2027 |
| 57–70 | Kubernetes | CKA, 13 Dec 2027 |

179 tasks, about 190 hours of planned work.

Every week has a plain-English explanation of the concepts, numbered tasks with time estimates, direct links to the study material, a hands-on lab, and a workplace action. 33 of the fiddlier tasks carry step-by-step instructions and a note on why they are worth doing.

CompTIA A+ and the CCNA were considered and deliberately left out — A+ certifies work already being done day to day, and the CCNA's Cisco-specific depth is largely not what platform work needs.

## How it works

One HTML file. No build step, no dependencies, no framework, no backend.

- **Encryption** — the roadmap is encrypted under a random AES-256-GCM data key, and that key is wrapped separately for each passphrase using PBKDF2-SHA256 at 250,000 iterations. Two passphrases open one copy of the content, and which wrapper opened determines the access level. All of it happens in the browser via the Web Crypto API, which is what makes the page safe to host publicly on GitHub Pages — free accounts cannot serve private sites.
- **Progress** — ticking a task writes a bitfield into the URL fragment. The address bar *is* the save file, so copying the link to another device carries progress with it. A local copy is kept per browser as a convenience.
- **Focus mode** — opens showing only the current week; the other 69 collapse to single lines. A "do this next" panel always names one action and how long it should take.
- **Pace tracking** — compares today's date against the schedule and reports on track, slightly behind, or far enough behind that the exam date should move.
- **Calendar** — ticking a task offers a prefilled Google Calendar event for that evening's study session, so the pace figures reflect sessions actually done rather than intentions.
- **Videos** — all 208 Professor Messer videos for Network+ and Security+ are assigned to their week with runtimes, individually tickable, rolling up into the parent task.
- **Glossary** — 262 terms across 15 groups, searchable, with hover tooltips on any term appearing in the text. 192 of them say which week teaches the concept, most with a link to the specific video.

## Accessibility

Every prose element meets WCAG AAA contrast (7:1) in both light and dark mode, at roughly 74 characters per line. The typography was measured rather than eyeballed.

## Running it locally

Download `index.html` and open it in any browser. Nothing to install, and it works offline once loaded.

## Deploying

GitHub Pages, serving `index.html` from the root of `main`. Any static host works — the file has no server-side requirements.

## Maintaining it

The page is built from source that does not live in this repository; `index.html` is a compiled artifact. See [MAINTENANCE.md](MAINTENANCE.md) for what has to be updated together whenever the plan changes.

## Licence

Personal study material. Take anything useful.
