# Reviewer Patterns

## Outdated Content
When content is replaced but should be kept for history, wrap the old content in an `Outdated` blockquote.

```markdown
> ⚠️ Outdated: 2026-04-06
> The previous project naming convention was based on [Old System].
> (Old content remains here)
```

## Input Required
Flag areas where a human decision is needed but not yet made.

```markdown
<!-- input-required: Need to define the metadata field for 'Contractor Type' -->
```

## Decision Log Entry
Append to `.decisions/decision-log.md` in this format:

```markdown
### 2026-04-06: [Decision Title]
- **Summary:** [Brief description of the change]
- **Affected Files:**
  - [file_path_1]
  - [file_path_2]
```
