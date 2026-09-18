# Claude Skills (Personal)

A collection of reusable Claude skills designed to extend Claude's capabilities with specialized workflows, templates, and best practices for specific problem domains.

## Overview

This repository contains carefully-crafted **skills** — structured instruction sets that teach Claude how to approach particular types of work with rigor, consistency, and depth. Each skill is self-contained, well-documented, and ready to use in your Claude sessions.

Skills are triggered contextually based on what you ask Claude to do, and they persist across conversations, so the patterns and disciplines they encode stay sharp and consistent over time.

## Skills Included

### 1. **Fact & Information Forensics**

Rigorous fact-checking and information verification across a 10-step pipeline.

**What it does:**
- Checks whether a claim is a recycled/recurring hoax before re-investigating from scratch
- Traces claims back to their original primary source
- Assesses source credibility, identifies distortions (trimmed quotes, misleading stats, out-of-context media)
- Renders verdict on confidence tiers: Confirmed, Partially True, Unverified, False
- Measures how widely a claim spread and whether spread looks organic or coordinated
- Checks political framing/lean separately from factual accuracy
- Maps who benefits from a claim being believed
- Applies adversarial reasoning (argues the opposite) before finalizing a verdict

**Use it for:**
- Fact-checking articles, claims, statistics, quotes
- Verifying whether news is true or out of context
- Assessing source credibility or bias
- Measuring how viral/spread a rumor has become
- Understanding who benefits from misinformation
- Checking if something is an old hoax resurfacing

**Trigger phrases:**
- "fact-check this"
- "is this real?"
- "trace this back to the source"
- "who said this first?"
- "was this astroturfed?"
- "has this been debunked before?"
- "debunk this"

**Files:**
- `SKILL.md` — the full 10-step skill with detailed guidance
- `references/verdict-examples.md` — three worked end-to-end examples showing the pipeline in practice

---

## How to Use

1. **In Claude chat:** Simply ask Claude to fact-check, verify, or investigate a claim. Claude will automatically apply the skill if it's relevant.

2. **Reference the skill:** Paste or mention a claim, article, quote, statistic, image, or link, plus your question about it. The skill will handle the investigation.

3. **Customize depth:** The skill adapts — simple yes/no questions get a concise answer; multi-claim investigations get the full pipeline with structured per-claim verdicts.

---

## Structure

```
claude-skills-personal/
├── README.md                          (this file)
├── fact-forensics/
│   ├── SKILL.md                       (main skill definition)
│   ├── references/
│   │   └── verdict-examples.md        (worked examples)
│   └── assets/                        (diagrams, reference images if any)
├── [future skills]/
│   ├── SKILL.md
│   └── references/
└── .gitignore
```

Each skill is a self-contained directory with:
- **SKILL.md** — the full, detailed skill definition with step-by-step procedures
- **references/** — supporting materials (worked examples, templates, checklists, guides)
- **assets/** — visual aids, diagrams, or supplementary content

---

## Skill Format

Each skill's `SKILL.md` includes:

- **Frontmatter** — name, description, trigger conditions
- **Why this matters** — context and value proposition
- **Step-by-step procedure** — the core methodology
- **Common patterns** — what to watch for, edge cases
- **Output format** — how to structure the result
- **References** — pointers to examples and supporting materials

This structure ensures skills are clear, consistent, and easy to apply without ambiguity.

---

## Philosophy

These skills embody a few core principles:

1. **Rigor over speed** — better to be thorough than quick
2. **Transparency** — always show reasoning and confidence levels
3. **Separation of concerns** — don't let one verdict cover multiple distinct questions
4. **Adversarial thinking** — argue against your own conclusion before finalizing it
5. **Humble uncertainty** — "unverified" is honest; confident guessing is not

---

## Adding New Skills

To add a new skill to this repository:

1. Create a directory: `<skill-name>/`
2. Write `SKILL.md` following the format above
3. Add `references/` with examples, templates, or supporting guides
4. Update this README to list the skill
5. Commit and push

---

## License

These skills are provided as-is for personal use. Feel free to fork, modify, and adapt them for your own needs.

---

## Contact

Created by [@Syedsmaeel](https://github.com/Syedsmaeel) | Reach out with improvements, suggestions, or new skill ideas.

---

**Last updated:** September 2026
