---
name: onc-atlas-question-framer
description: Use when the user wants to prepare clear, non-technical questions for decision-makers or stakeholders. Scans the onc-atlas knowledge base for unresolved items (e.g., input-required tags, missing detail files) and frames them for a meeting agenda.
---

# ONC-Atlas Question Framer

This skill prepares a structured, jargon-free question set for meetings with stakeholders who will make or validate decisions about the ONC-Atlas system.

## When Activated

The user may provide a specific scope (e.g., "focus on naming conventions"), a concern (e.g., "we haven't agreed on revision logic"), or ask for a general scan of the full outline.

## Workflow

1. **Collect Open Items:** Scan `ONC_atlas_outline.md` and all detail `.md` files in the repository for:
   - Sections or fields marked `<!-- input-required -->`.
   - Sections in the outline that lack a corresponding detail `.md` file.
   - Explicit open questions or unresolved items in `.decisions/decision-log.md`.
   - Specific topics flagged by the user in their prompt.
2. **Frame Questions:** For each identified item, write one primary question suitable for a non-technical decision-maker.
   - **Audience:** Management and stakeholders, not engineers.
   - **Language:** Avoid technical jargon (no file paths, Git commands, or implementation details).
   - **Precision:** Do not invent decisions or make assumptions. Surface lack of clarity as a question.
3. **Format Output:** Group questions by their corresponding outline section.

## Output Structure

For each section group, use the following format:

```markdown
## [Section Number] — [Section Title]

**Q:** [Primary Question]
  - [Sub-question if needed]
  - [Sub-question if needed]

**Context:** [One sentence explaining why this decision matters and who is affected]
**Default if undecided:** [What happens or what is assumed if the meeting produces no answer]
```

At the end of the report, include a **## Open Items Summary** which is a simple numbered list of all questions for easy copy-pasting into a meeting agenda.

## Hard Rules

- **Read-Only:** Do not modify any files in the repository. This skill is for information gathering and synthesis only.
- **Audience Focus:** Keep questions high-level. If a question feels too technical, rephrase it to focus on the *business impact* or *operational workflow* rather than the implementation.
- **No Inventions:** If the source material is silent on a topic, do not fill in the blanks with assumptions.
