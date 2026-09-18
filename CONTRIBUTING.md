# Contributing to Claude Skills (Personal)

Welcome! This guide explains how to contribute new skills or improvements to this repository.

## What is a Skill?

A **skill** is a reusable instruction set that teaches Claude how to approach a specific type of work with rigor, consistency, and depth. Skills are self-contained, well-documented, and designed to be triggered contextually based on what you ask Claude to do.

Not everything needs to be a skill:
- **Good candidates:** recurring workflows, multi-step procedures, domain-specific disciplines, decision frameworks
- **Not skills:** one-off answers, quick tips, general knowledge, personal preferences

## Adding a New Skill

### 1. Plan the Skill

Before writing, think through:
- **What problem does it solve?** Be specific about the use case.
- **What's the procedure?** Map out the step-by-step approach.
- **When should it trigger?** What phrases or requests should invoke it?
- **How does it output?** What should the result look like?
- **Any gotchas?** Where do people usually go wrong?

### 2. Create the Directory Structure

```
your-skill-name/
├── SKILL.md                    (required)
├── references/
│   ├── example-1.md            (worked examples)
│   ├── template.md             (reusable templates)
│   └── checklist.md            (step-by-step checklists)
└── assets/                     (optional: diagrams, reference images)
    └── diagram.png
```

### 3. Write SKILL.md

Follow this frontmatter and structure:

```markdown
---
name: your-skill-slug
description: One-line description of what the skill does and when to use it. Keep under 1024 characters. Include trigger phrases.
---

# Skill Title

## Why this matters

2-3 sentences explaining the value of this skill and the problem it solves.

## Step-by-step procedure

Break the skill into clear, numbered steps. Each step should:
- Have a short title
- Explain what to do in plain language
- Include examples or gotchas
- Link to reference materials where relevant

### Example: Step 1 — First major phase

Clear explanation of what this step entails. Include:
- What you're looking for
- Common mistakes
- When to skip this step

## Common pitfalls

- **Mistake 1:** What goes wrong and how to avoid it
- **Mistake 2:** Another common error

## Output format

Show what a successful output looks like, with an example or template:

```
## Verdict: <claim>
**Status:** Confirmed / Unverified / False
**Evidence:** <summary>
```

## Worked examples

Point to reference materials or include a brief example showing the skill in action.
```

### 4. Add Reference Materials

Create `references/` directory with:

- **Worked examples** (`examples.md`) — 2-3 full walkthroughs showing the skill applied to real scenarios
- **Templates** (`templates.md`) — reusable forms, checklists, or scaffolds
- **Checklists** (`checklist.md`) — step-by-step verification checklist
- **Guides** (`guide-*.md`) — deep dives on particular subtopics

Each reference should be standalone and usable without reading SKILL.md.

### 5. Test the Skill

Before submitting:
- [ ] Read the skill as if you've never seen it before — is it clear?
- [ ] Try applying it to a real-world problem — does it work?
- [ ] Check for ambiguous instructions — where could someone get stuck?
- [ ] Verify all references exist and are accurate
- [ ] Ensure the description is <1024 characters and includes trigger phrases

### 6. Update README.md

Add your skill to the README's **Skills Included** section with:
- Skill name and purpose
- What it does (2-3 sentences)
- Use cases (trigger scenarios)
- File structure
- Link to the skill

### 7. Create a Pull Request

1. Fork or branch off `main/root`
2. Commit with a clear message:
   ```
   git commit -m "Add <skill-name> skill

   - Brief description of what the skill does
   - Any notable features or methodology
   - References or inspirations"
   ```
3. Push to your branch
4. Open a PR with:
   - **Title:** `Add <skill-name> skill`
   - **Description:** What the skill is for, why it matters, and how to use it

## Style Guidelines

### Writing

- **Clarity over formality.** Write as if explaining to a colleague, not a textbook.
- **Active voice.** "Check the source" not "The source should be checked."
- **Concrete examples.** Show, don't tell. Include real-world scenarios.
- **Avoid jargon.** If you use a technical term, explain it the first time.

### Structure

- Keep steps under 200 words each; break longer ones into substeps
- Use examples liberally — worked examples are better than abstract instructions
- Link to reference materials; don't repeat them inline
- Group related steps together with headers

### References

- Make them actionable — a reference should stand alone
- Title them clearly ("Example: X scenario," "Checklist: Y process")
- Include enough detail to use without reading the main skill
- Add "When to use this" section if it's not obvious

## Code of Conduct

- Be respectful and constructive in feedback
- Assume good intent
- Welcome diverse approaches — there's often more than one right way
- Prioritize clarity and usefulness over brevity

## Skill Review Checklist

When reviewing a PR or submitting your own, verify:

- [ ] Skill solves a real, recurring problem
- [ ] Step-by-step procedure is clear and unambiguous
- [ ] Trigger phrases are included in the description
- [ ] Worked examples demonstrate the skill in action
- [ ] Output format is clear (with example)
- [ ] Common pitfalls are addressed
- [ ] SKILL.md follows the template structure
- [ ] Description is under 1024 characters
- [ ] README.md is updated
- [ ] No typos or formatting issues
- [ ] References are accurate and complete

## Questions?

Open an issue to discuss:
- A skill idea you're considering
- Feedback on an existing skill
- Questions about the format or process

---

**Thank you for contributing!** Skills improve with real-world use and community feedback.
