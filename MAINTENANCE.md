# Maintaining this roadmap

`index.html` is a **compiled artifact**. It is generated from a data file and an HTML template, encrypted at build time, and the source does not live in this repository. Do not hand-edit `index.html` — the content is ciphertext.

This file exists because the roadmap has several pieces that drift apart if only one of them is changed. If you are Claude, or Ozan, and you are changing the plan: **work through this checklist every time.**

---

## The five things that must stay in sync

Whenever the plan changes — a week added, dates moved, a stage restructured, a resource replaced — all five of these need updating together:

1. **The page itself** (`index.html` here, plus the unencrypted copy in the Cowork artifact gallery). Both are rebuilt from the same source, so they can never disagree — but both must be re-delivered and re-uploaded.
2. **This repository.** Upload the new `index.html`. Same filename, so it replaces rather than duplicates. Check the download did not arrive as `index (1).html`.
3. **The README.** Week count, stage table, milestone dates, task and glossary counts, and the feature list. It goes stale faster than anything else because none of it is generated.
4. **The GitHub repository description** at the top of the repo page. It still says whatever it said when the repo was created.
5. **The Friday scheduled task.** It carries its own copy of the full week schedule, because each run starts fresh with no memory. If the weeks change and this is not updated, the weekly brief will confidently describe a plan that no longer exists.

## Also worth checking

- **Commit messages** follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/): `feat:`, `fix:`, `docs:`, `chore:`, lowercase, imperative, no trailing full stop.
- **Progress links.** Ticks are stored as a bitfield positional to the task list. Adding or reordering weeks invalidates any saved progress link. If Ozan has real progress, say so before restructuring.
- **Both passphrases still work** after a rebuild — owner and guest are separate ciphertexts.
- **The guest copy is still redacted.** The "At work" notes must be absent from the guest payload, not merely hidden.
- **Nothing hardcodes a week count.** Header, strip heading and intro text all derive from the data. Keep it that way.

## Facts with a shelf life

These were correct in August 2026 and will not stay correct. Re-verify before relying on them:

- CompTIA **N10-009** retires around June 2027; **SY0-701** is current with SY0-801 unreleased.
- **CKA** is curriculum v1.35 — etcd backup/restore was removed in 2025; Helm, Kustomize, Gateway API, CRDs and HA control plane are in. killer.sh ships with the standard registration but **not** with CKA-SINGLE.
- **AWS SAA-C03** is current; there is no SAA-C04, whatever course sellers claim.
- **AWS free tier** changed in July 2025 — new accounts get $200 in credits, not 12 months free, and the Free Plan deletes the account if it lapses.
- **Oracle Cloud Always Free** is 2 cores / 12GB since June 2026, and reclaims instances idle for 7 days.
- Hardware and exam prices move. The mini PC figure assumes the post-2025 DRAM shortage.
