# Humanbased Brand Review

Review any Humanbased external copy against the Writing Guidelines and flag deviations with severity and concrete fixes.

## When to use

Use this skill when the user asks to:
- "review this", "check this post", "does this sound on-brand"
- "proofread this tweet / announcement / email"
- screen copy before publishing to Twitter, Discord, Telegram, or any public channel
- check for Base amplification eligibility

## Input

The user provides a draft — tweet, thread, announcement, email, press release, or any external-facing copy.

If the user doesn't specify channel or content type, ask before reviewing (channel affects which rules apply).

## How to review

Work through the guidelines in order. For each deviation, assign a severity:

- 🔴 **Critical** — breaks a hard rule; must fix before publishing (wrong brand name spelling, financial language in Base content, unauthorized partnership claim, unverified superlative)
- 🟡 **Warning** — weakens the voice or risks amplification rejection; should fix (passive voice throughout, fake warmth opener, emoji storm)
- 🟢 **Note** — minor style preference; worth considering (Oxford comma missing, sentence could be split)

## Output format

```
**Review: [content type] — [channel]**

[Quote the flagged line]
🔴/🟡/🟢 [Rule violated]
→ Fix: [rewritten version]

---
[Repeat for each flag]

---
**Summary**: X critical, Y warnings, Z notes.
[One-line overall verdict: ready / revise before publishing / do not publish]
```

If no issues found, say so directly — "No deviations found. Ready to publish."

## Guidelines reference (apply in full)

### Voice — Calm · Anatomical · Accountable
- **Calm**: No hype, no urgency theater. State what's true.
- **Anatomical**: Name things exactly. Right word, not the impressive-sounding one.
- **Accountable**: Say what happened, what it means, what's next. No vague gestures.

### Hard "what to avoid" flags (always 🔴 if present)
- "Join the revolution" or equivalent empty rallying cry
- "The most advanced / best / first" without evidence
- Emoji count > 1 per post
- Passive voice used as the default (not occasional)
- "We're so excited to announce" or fake warmth openers

### Canonical terminology (flag wrong usage as 🟡)
| Wrong | Right |
|---|---|
| worker, user, talent | contributor |
| project, task group | campaign |
| approved, passed | accepted (task status) |
| on-chain, on chain | onchain |

### Brand name spelling (🔴 if wrong)
- **Humanbased** — one word, no hyphen, no space
- **humanbased.ai** — always lowercase in URLs
- **$XNY** or **XnY** — token
- **Outtrain AI Limited** — legal/payment copy only

### Base-specific (apply only if content involves Base — flag violations as 🔴)
- BASE / Base Chain / $BASE / Base Network → **Base**
- on-chain / on chain → **onchain**
- Brand order must be **Humanbased × Base** (not Base × Humanbased)
- No "partnership" / "collaboration with Base" → use "built on / launched on / integrated with Base"
- No financial language (gains, profits, investments, high yields, leverage)
- Post must include project context — not just a standalone feature or milestone
- No unverified superlatives
- Visuals must not over-emphasize tokens, prices, or investment returns

### Punctuation quick checks (🟢)
- Oxford comma: "apples, oranges, and bananas" ✅
- Em dash spacing: `—` with one space each side ✅
- & only in proper names or standard abbreviations, not substituting "and"
