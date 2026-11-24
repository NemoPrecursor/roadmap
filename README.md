# roadmap

A self-contained, single-file study tracker for moving from IT support into platform engineering.

**Live page:** https://nemoprecursor.github.io/roadmap/

The page is encrypted. Opening it without a passphrase shows a lock screen and nothing else — the content is not in the page source.

There are two passphrases. The owner's unlocks the full tracker. A guest one opens a read-only view: no ticking, no glossary tooltips, no calendar, no saved progress, and the owner's private notes omitted — not hidden with CSS, but absent from the ciphertext the guest passphrase can open.

---

## What it is

A 74-week plan running November 2026 to April 2028 at 5–7 hours a week, built against a real job posting: Y TREE's *Platform Engineer (Mid) – AWS, Kubernetes & IaC*, which names **Kubernetes, Terraform and AWS** as its requirements.

| Weeks | Stage | Milestone |
|---|---|---|
| 1–4 | CompTIA A+ (220-1201 / 220-1202) | Core 1 & Core 2 exams |
| 5–19 | CompTIA Network+ (N10-009) | Exam, 29 Mar 2027 |
| 20–33 | CompTIA Security+ (SY0-701) | Exam, 5 Jul 2027 |
| 34–43 | Linux, shell, Git, Docker | Portfolio checkpoint, 13 Sep 2027 |
| 44–48 | Proxmox, Terraform, Ansible | Infrastructure checkpoint, 18 Oct 2027 |
| 49–60 | AWS | Solutions Architect Associate, 10 Jan 2028 |
| 61–74 | Kubernetes | CKA, 17 Apr 2028 |

Weeks 34–48 form one stage in the page itself; the table splits them because they carry two separate checkpoints. 190 tasks, about 210 hours of planned work, and no gap of more than 15 weeks between milestones.

Every week has a plain-English explanation of the concepts, numbered tasks with time estimates, direct links to the study material, a hands-on lab, and a workplace action. 41 of the fiddlier tasks carry step-by-step instructions and a note on why they are worth doing.

CompTIA A+ leads the plan as a short, gap-driven Stage 0 (four weeks, two exams). It certifies a lot of work already done day to day, so it is deliberately compressed — sit a practice exam cold, study only what you miss — and it is included for a complete stackable foundation: A+ with Network+ and Security+ earns CompTIA's Secure Infrastructure Specialist title. The CCNA was considered and deliberately left out; its Cisco-specific depth is largely not what platform work needs.

## How it works

One HTML file. No build step, no dependencies, no framework, no backend.

- **Encryption** — the roadmap is encrypted under a random AES-256-GCM data key, and that key is wrapped separately for each passphrase using PBKDF2-SHA256 at 250,000 iterations. Two passphrases open one copy of the content, and which wrapper opened determines the access level. All of it happens in the browser via the Web Crypto API, which is what makes the page safe to host publicly on GitHub Pages — free accounts cannot serve private sites.
- **Progress** — ticking a task writes a bitfield into the URL fragment. The address bar *is* the save file, so copying the link to another device carries progress with it. A local copy is kept per browser as a convenience.
- **Focus mode** — opens showing only the current week; the other 73 collapse to single lines. A "do this next" panel always names one action and how long it should take.
- **Pace tracking** — compares today's date against the schedule and reports on track, slightly behind, or far enough behind that the exam date should move.
- **Calendar** — ticking a task offers a prefilled Google Calendar event for that evening's study session, so the pace figures reflect sessions actually done rather than intentions.
- **Videos** — all 208 Professor Messer videos for Network+ and Security+ are assigned to their week with runtimes, individually tickable, rolling up into the parent task.
- **Glossary** — 265 terms across 16 groups, searchable, with hover tooltips on any term appearing in the text. 195 of them say which week teaches the concept, most with a link to the specific video.

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
