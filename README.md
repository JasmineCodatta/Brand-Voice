# Humanbased Brand

This repository contains Humanbased's writing guidelines and two Claude skills built on top of them — one for reviewing copy, one for generating it.

---

## Contents

```
Brand/
├── Humanbased Writing Guidelines.md   — canonical writing reference
└── skills/
    ├── brand-review/SKILL.md          — review copy against the guidelines
    └── content-writer/SKILL.md        — generate on-brand copy from a brief
```

---

## Humanbased Writing Guidelines

`Humanbased Writing Guidelines.md` is the canonical reference for all Humanbased external-facing copy — social posts, announcements, press, long-form, founder appearances.

### Voice: Calm · Anatomical · Accountable

The three-word brief that governs everything:

- **Calm** — No hype, no urgency theater. State what's true. Let the substance carry the weight.
- **Anatomical** — Name things exactly. The right word, not the impressive-sounding one. Specific nouns and action verbs over adjective stacks.
- **Accountable** — Say what happened, what it means, and what comes next. No vague gestures. Own the claim.

### What the document covers

The guidelines are organized in four sections:

**§1 Voice and Tone** — The three-word brand voice above, plus tone adjustments per content piece (brief and punchy for short-form, no jargon, max one emoji) and a list of patterns to actively avoid (fake warmth openers, unverified superlatives, passive voice as default, emoji storms).

**§2 Clarity and Flow** *(social media only)* — Rules for sentence construction: favor action verbs over be-verbs, plain word choices, active over passive, short sentences. Plus flow rules: no fragments, varied rhythm and structure.

**§3 Nuances** — Four subsections:
- *Canonical Terminology* — the approved vocabulary (`contributor` not `worker`, `campaign` not `project`, `accepted` not `approved`, `onchain` not `on-chain`) plus brand name formatting (`Humanbased` one word, `humanbased.ai` always lowercase, `$XNY` / `XnY` for the token, `Outtrain AI Limited` in legal copy)
- *Capitalization* — Title Case for headlines, Purdue OWL as baseline
- *Punctuation* — Oxford comma, em dash spacing, ampersand rules, parenthetical period placement
- *Numbers, Dates, and Times* — spell out 0–9, use K/M/B abbreviations, date format, time format with timezone

**§4 Base-Specific Rules** *(apply only when writing Base-related content)* — Naming rules (`Base` not `BASE`), brand order (`Humanbased × Base`), relationship language (`built on Base` not `partnership with Base`), six writing principles aligned to Base's mission, a detailed list of amplification red lines (financial language, token focus, missing context, unverified superlatives), and a pre-publish checklist.

---

## Skills

Both skills are designed to be used with [Claude](https://claude.ai) or the [Claude Agent SDK](https://docs.claude.com). Drop a `SKILL.md` into your Claude Code setup or reference it in a system prompt.

### `skills/brand-review/` — Brand Review

**What it does:** Takes any draft (tweet, thread, announcement, email, press release) and reviews it against the Writing Guidelines. Flags each deviation with a severity level and a concrete rewrite suggestion.

**Severity tiers:**
- 🔴 **Critical** — hard rule violation; must fix before publishing (wrong brand name spelling, financial language in Base content, unauthorized partnership claim, unverified superlative)
- 🟡 **Warning** — weakens the voice or risks Base amplification rejection (passive voice throughout, fake warmth opener, emoji storm)
- 🟢 **Note** — minor style preference worth considering (missing Oxford comma, sentence that could be split)

**Output format:**
```
Review: [content type] — [channel]

[Quoted line]
🔴 [Rule violated]
→ Fix: [rewritten version]

Summary: X critical, Y warnings, Z notes.
[Verdict: ready / revise before publishing / do not publish]
```

**When to use:** Before any post goes live. Especially useful for Base-related content where amplification eligibility depends on strict rule compliance.

---

### `skills/content-writer/` — Content Writer

**What it does:** Generates on-brand Humanbased copy from a brief. Applies the full Writing Guidelines — voice, terminology, channel formatting, and Base rules where relevant.

**Intake (asks if not provided):**
1. Channel — Twitter/X, Discord, Telegram, email, press, long-form
2. Content type — Product Education / Community / Ecosystem / Event / Announcement / Deep Dive
3. Topic and angle — what this is about and what it should land
4. Does it involve Base? — determines whether §4 rules apply
5. Tone target — matter-of-fact / celebratory / inviting (all within Calm·Anatomical·Accountable)

**Channel rules applied automatically:**
- Twitter/X: max one emoji, two short sentences over one long one, no "…and more." endings, each tweet in a thread is standalone-legible
- Discord/Telegram: slightly more conversational, bold used sparingly for key terms
- Announcements/Press: Title Case headlines, lead with the fact, Oxford comma throughout
- Long-form: ends when the thought is complete (no word count floors), prose over bullet-point walls

**When to use:** Any time you need to produce external copy from scratch. If you're unsure whether the output is on-brand, run it through the brand-review skill afterward.

---

## Usage with Claude

You can load either skill into a Claude conversation by pasting the `SKILL.md` contents into your system prompt, or by pointing a Claude Code plugin at the file path.

To invoke brand review:
> "Review this tweet against the Humanbased writing guidelines: [paste copy]"

To invoke content writing:
> "Write a Twitter post announcing that [X]. Content type: Announcement. No Base involvement."

---

## Maintenance

When the Writing Guidelines are updated, the skills should be reviewed to ensure their embedded rules stay in sync. The canonical source of truth is always `Humanbased Writing Guidelines.md`.
