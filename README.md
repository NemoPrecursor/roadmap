# roadmap

A self-contained, single-file study tracker for moving from IT support into platform engineering.

**Live page:** https://nemoprecursor.github.io/roadmap/

The page is encrypted. Opening it without the passphrase shows a lock screen and nothing else — the content is not in the page source.

---

## What it is

A 56-week plan running August 2026 to September 2027 at 5–7 hours a week, in four stages:

| Weeks | Stage | Ends with |
|---|---|---|
| 1–15 | CompTIA Network+ (N10-009) | Exam, Nov 2026 |
| 16–29 | CompTIA Security+ (SY0-701) | Exam, Mar 2027 |
| 30–39 | Linux, shell, Git, Docker | Portfolio checkpoint, May 2027 |
| 40–56 | Proxmox, Kubernetes, CKA | CKA exam, Sep 2027 |

Every week has a plain-English explanation of the concepts, a set of tasks, direct links to the free study material, a hands-on lab, and a workplace action. A 234-term glossary covers everything from *what is a server* through to *etcd*, and any glossary term appearing in the text can be hovered for its definition.

CompTIA A+ and the CCNA were considered and deliberately left out — A+ certifies work already being done day to day, and the CCNA's Cisco-specific depth is largely not what platform work needs.

## How it works

One HTML file. No build step, no dependencies, no framework, no backend.

- **Encryption** — the roadmap data is AES-256-GCM ciphertext with a PBKDF2-SHA256 key (250,000 iterations), decrypted in the browser via the Web Crypto API. This is what makes it safe to host publicly on GitHub Pages, which cannot serve private sites on a free account.
- **Progress** — ticking a task writes a compact code into the URL fragment. The address bar *is* the save file, so copying the link to another device carries progress with it. A local copy is also kept per browser as a convenience.
- **Pace tracking** — the page compares today's date against the schedule and reports whether the plan is on track, slightly behind, or far enough behind that the exam date should move.
- **Calendar** — ticking a task offers a prefilled Google Calendar event for that evening's study session, so the pace figures reflect sessions actually done rather than intentions.

## Running it locally

Download `index.html` and open it in any browser. There is nothing to install and it works offline once loaded.

## Deploying

GitHub Pages, serving `index.html` from the root of `main`. Any static host works equally well — the file has no server-side requirements.

## Licence

Personal study material. Take anything useful.
