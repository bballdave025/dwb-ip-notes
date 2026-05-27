# Canonical OCR + Clean-Room Notebook Transcription Process

## Purpose

This workflow is designed for:
- clean-room transcription of redacted Jupyter notebook scans,
- uncertainty-preserving OCR,
- incremental canonicalization,
- and executable Markdown reconstruction.

The process intentionally preserves uncertainty, redactions, and OCR ambiguity rather than silently “fixing” them.

---

# Core Principles

1. Preserve uncertainty explicitly.
2. Separate OCR uncertainty from intentional editorial corrections.
3. Preserve redactions without guessing.
4. Favor stable cumulative progress over recursive perfectionism.
5. Treat the cumulative Markdown file as canonical state.

---

# Canonical Output Structure

Each page is first produced as:
- an unrendered Markdown code-fenced block,
- then optionally rendered for visual inspection,
- then appended to the cumulative Markdown file after final approval.

---

# Redaction Rules

## Inline redactions

Use:

```text
█
```

Example:

```python
api_key = "████████████"
```

Approximate width is encouraged but not mandatory.

---

## Whole-line or block redactions

Use bracketed annotations:

```text
[line redacted]
[multiple lines redacted]
[project-related markdown documentation redacted]
```

Prefer semantic descriptions when safely possible.

---

# Uncertainty Rules

## Inline uncertainty marker

Use:

```text
⌨
```

Place directly at the uncertainty location.

Example:

```python
print("CO⌨ Dave ████████), THE CURRENT MAINTAINER")
```

Do not overfit exact character counts.

---

## Uncertainty descriptions

Immediately after uncertain regions, use Markdown blockquotes:

```markdown
>        ^⌨v explanation text
```

Example:

>        ^⌨v unclear beginning of contact instruction; redacted portion follows visible “Dave”

These annotations:
- preserve epistemic honesty,
- prevent hallucinated cleanup,
- and help targeted later review.

---

# Jupyter Reconstruction Conventions

## Cell headers

Example:

```python
#=============
# THIRD CELL   ^^^ LOOK ABOVE ^^^
#              |||            |||
#=============
```

---

## Output blocks

Notebook output is separated from code cells.

Use:

```html
<sup><code>Out&nbsp;[FIRST]:</code></sup>
```

or:

```html
<sup><code>Out&nbsp;[SECOND]:</code></sup>
```

These intentionally preserve notebook feel while distinguishing OCR structure from true execution history.

---

# Markdown Fence Strategy

Outer fences use 4 backticks:

````markdown
`````python
...
`````
````

This allows literal internal notebook fences without breaking rendering.

---

# Canonical Workflow

1. User uploads one page image.
2. OCR draft generated.
3. User corrects/improves content.
4. Rendered preview inspected.
5. Final approval issued.
6. Page appended to cumulative Markdown.
7. New downloadable cumulative file generated.

---

# ERP / Scope-Control Rule

Previously finalized pages are NOT reopened unless absolutely necessary.

Process improvements apply forward unless:
- critical correctness,
- broken rendering,
- or canonical consistency requires back-propagation.

This is intentional anti-perfectionism scope control.
