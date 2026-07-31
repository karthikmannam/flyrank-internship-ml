# FL-01: Portfolio Sitemap & Tool Setup (Draw the Path)

**Submitted by:** Karthik Mannam
**Date:** 2026-07-31
**Status:** Complete
**Related:** `work/fl01_workflow_audit_report.md` (tool setup base confirmed there)

---

## 1. The Anchor: Proof Statement & One Action

Every block on the portfolio exists to serve exactly two things — the claim I can
defend, and the single action I want a visitor to take. If a section does not move
one of those two forward, it is cut.

**Proof statement (the claim, used verbatim on the hero):**

> ML intern who built and deployed production-grade baseline action models and
> rigorous data contracts for a search-intelligence startup.

**One action (the single conversion):**

> Email me / contact for opportunities.

**How they interact:** the proof statement gives the visitor a reason to care; the
one action tells them what to do about it. Every section states the claim in a
narrower form and ends by pointing back at the action.

---

## 2. Portfolio Sitemap & Structure

### Sitemap sketch (minimal, single page)

```text
PORTFOLIO (single page — nothing that isn't needed)

├─ HERO ─────────────────────────────────────────────
│     Proof statement (one sentence, verbatim)
│     CTA button → mailto: (the one action, above the fold)
│
├─ WORK / CASE STUDIES ──────────────────────────────
│     Case study 1 — Data Contract (ML-04)
│     Case study 2 — Baseline Action Model (ML-07)
│     (each card: problem → method → result → "Ask me about this" → mailto)
│
├─ ABOUT ────────────────────────────────────────────
│     Two short paragraphs: who I am, why this internship
│     One closing line → mailto: (the one action)
│
└─ CONTACT ──────────────────────────────────────────
      Email CTA + links to repo + deployed paper
      (zero-friction, always visible)
```

### Page-role table — why each block earns its place

| Block | Role in the story | Earns its place vs the proof statement | Feeds the one action |
|---|---|---|---|
| **Hero** | State the claim in one sentence | Carries the proof statement verbatim; the "production-grade + data contracts" promise is set here | CTA button sits above the fold; the visitor knows what to do in 3 seconds |
| **Work / Case Studies** | Prove the claim with evidence | Each case study maps to a proof element: ML-04 → "rigorous data contracts"; ML-07 → "production-grade baseline action models" | Every card ends with "Ask me about this" → mailto, so each piece of evidence converts |
| **About** | Build trust / humanize | Short and honest: who I am and why this internship, no overclaiming | One line back to the action after trust is established |
| **Contact** | The action itself | Not evidence — it is the destination; kept minimal so nothing dilutes the ask | The one action, no forms, no friction (plain `mailto:`) |

### Deliberately excluded (they earn their place by being absent)

| Excluded | Why it loses its place |
|---|---|
| Blog / journal | No proof-carrying power; drains attention from the claim and the action |
| Separate resume page | The one action is contact, not resume-download; a resume link belongs in the contact block |
| Skills list page | Skills are demonstrated by case studies, not asserted in a list |
| Long-form about me | Doesn't carry the claim; the two-paragraph About is enough for trust |

---

## 3. Free Toolkit Setup Status

| Tool | Account status | Evidence |
|---|---|---|
| **Claude (Free)** | ✅ Created | Active at claude.ai (confirmed in `fl01_workflow_audit_report.md`) |
| **ChatGPT (Free)** | ✅ Created | Active at chatgpt.com (confirmed in `fl01_workflow_audit_report.md`) |
| **Gemini (Free)** | ✅ Created | Active via Google account at gemini.google.com |
| **Perplexity (Free)** | ✅ Created | Active at perplexity.ai |

All four free accounts are live. Per the free-tooling guide, no paid plan is
required for this track; Claude is the primary assistant and ChatGPT/Gemini/
Perplexity serve as cross-check and research tools.

---

## 4. Claude Project: Portfolio Build — 8-Week Tutor

### Project name

> **AI Fluency 8-Week Tutor — Portfolio Build**

### Purpose

A dedicated project for this build: it holds the proof statement, the one action,
and the sitemap, and acts as an 8-week tutor that pressure-tests my portfolio work
each week against the claim before it ships.

### Custom instructions (pasted into the project)

> **Who I am:** ML intern who built and deployed production-grade baseline action
> models and rigorous data contracts for a search-intelligence startup.
>
> **Your role:** You are my 8-week tutor for this portfolio build. One task per
> conversation, one section per week. You pressure-test every portfolio element —
> sitemap, copy, case-study claims, page structure — against my proof statement
> and my one action: "email me / contact for opportunities."
>
> **Rules:**
> - Every section must earn its place against the claim and the action, or be cut.
> - Attack my claims like a skeptical hiring manager; never flatter.
> - Keep output direct, technical, concise, with tables where structure helps.
> - No data leaks: no client names, domains, or private internship data in any copy.

### Key settings

- Scope: this portfolio build only (separate from the FL-01 workflow/research project)
- Custom instructions: proof statement + one action + tutor role (above)
- Output style: verdict-first, evidence-backed, actionable changes only

---

## 5. Pressure-Test Prompt & Output

### The real prompt used (Claude Project)

> "Act as a skeptical hiring manager who reads a portfolio in 90 seconds. My proof
> statement is: 'ML intern who built and deployed production-grade baseline action
> models and rigorous data contracts for a search-intelligence startup.' My one
> action is: 'email me / contact for opportunities.' Here is my sitemap: HERO (claim
> + CTA) → WORK (data-contract case study, baseline-model case study) → ABOUT (2
> paragraphs) → CONTACT (email CTA). Pressure-test it: (1) which block fails to earn
> its place against the claim? (2) does every block route a visitor to the one
> action? (3) where would a skeptical reader stop believing the claim? (4) what is
> the single highest-leverage change? Give verdicts, not compliments."

### Pressure-test output (abridged)

> **Verdicts**
>
> 1. **No block fails outright** — all four earn their place, but the **About**
>    block is the weakest: as written it proves nothing and is where a skeptical
>    reader first stops trusting the claim. It must earn its place by owning one
>    concrete fact (why this internship), not generic biography.
> 2. **Routing to the one action is inconsistent** — the Hero and Contact blocks
>    end with the email CTA, but the case-study cards read as "read more," not
>    "ask me about this." Evidence without a call-to-action does not convert.
> 3. **Believability break** — the claim says "production-grade," but a case study
>    that shows only methodology and no measured result (observed metrics) will be
>    read as fluff. Each card needs at least one number or a clearly framed
>    "observed" outcome.
> 4. **Highest-leverage change:** make every block — including each case study —
>    terminate in the same visible email CTA, and add one concrete "observed"
>    result per case study card.

### Adjustments adopted (from the pressure-test output)

| # | Adjustment | Source in output |
|---|---|---|
| 1 | **Every case-study card ends with the same visible email CTA** ("Ask me about this →"), so the one action is reachable from every block, not just Hero/Contact | Verdict 2 |
| 2 | **About section earns its place with one concrete fact** — why this internship — instead of generic biography | Verdict 1 |
| 3 | **Each case study card carries one observed result** (measured/observed framing, e.g., a Precision@50 number) so "production-grade" is supported by evidence | Verdict 3 |

These three adjustments are now baked into the sitemap in Section 2.

---

## 6. FL-01 Portfolio Sitemap Checklist

| Deliverable | Status |
|---|---|
| Sitemap designed (hero, work, about, contact) | ✅ Complete |
| Every block maps to proof statement + one action | ✅ Complete |
| Excluded sections justified | ✅ Complete |
| Free accounts: Claude, ChatGPT, Gemini, Perplexity | ✅ Complete |
| Claude Project created for this build (8-week tutor) | ✅ Complete |
| Proof statement in custom instructions | ✅ Complete |
| Pressure-test prompt documented | ✅ Complete |
| ≥1 adjustment adopted from pressure-test output | ✅ Complete (3 adopted) |
