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

# Transmission / Ordering Conventions

OCR work should preserve:
- sequential ordering,
- provenance,
- grouping structure,
- continuation state,
- and resumability.

The sender should explicitly specify:
- what is being sent,
- what subset it belongs to,
- and what remains to be sent.

This prevents:
- ordering ambiguity,
- premature canonicalization,
- dropped pages,
- and subset confusion.

---

# Preferred Sending Behavior

Prefer sending OCR material:
- one image at a time,
- or one logically coherent subset at a time.

Possible source types include:
- PDFs,
- image archives (`.zip`, `.tar.gz`, etc.),
- extracted image sets,
- or standalone images.

---

# PDF Transmission Conventions

## Simple PDF identification

Example:

```text
PDF containing 25 pages, file 3 of 8
```

---

## Explicit continuation state

Example:

```text
PDF containing 20 pages, file 4 of 5

More coming.
```

The phrase:

```text
More coming.
```

is important because it explicitly prevents assumptions of corpus completion.

---

# Image Transmission Conventions

When images are extracted from:
- PDFs,
- archives,
- or grouped sources,

the sender should preserve:
- global ordering,
- subset ordering,
- and local image position.

---

# Human-Readable Sequential Form

## Simple sequential form

```text
Image 14 of 25
```

---

## Subset-aware sequential form

```text
Image 7 of 72
(7 of 1st subset -- 15)
```

---

## Multi-subset continuation form

```text
Image 32 of 72
(15-from-1, 15-from-2, then 2 of 3rd subset -- 24)
```

---

# Canonical Compact Form (Machine-Friendly)

## Option A — readable compact form

```text
IMG 32/72 | subset 3/4 | local 2/24
```

Meaning:
- global image 32 of 72,
- currently processing subset 3 of 4,
- local image 2 of 24 within current subset.

---

## Option B — compact structured form

```text
IMG[G=32/72,S=3/4,L=2/24]
```

Where:
- `G` = global position,
- `S` = subset position,
- `L` = local position within subset.

This form is:
- compact,
- machine-readable,
- grep-friendly,
- and resilient under copy/paste.

---

# Recommended Terminology

To reduce ambiguity, prefer distinct terms:

| Concept | Preferred Term |
|---|---|
| Entire OCR project | corpus |
| Multi-part PDF grouping | segment |
| Image grouping | subset |
| Individual image/page | image or frame |

Example:

```text
Corpus: 72 pages
Segment: 3 of 4
Subset: 2 of 24
Global image: 32 of 72
```

---

# Canonical Recommendation

Preferred default human-readable transmission form:

```text
Image 32 of 72
(15-from-1, 15-from-2, then 2 of 3rd subset -- 24)
```

Preferred compact canonical form:

```text
IMG[G=32/72,S=3/4,L=2/24]
```

Both may be used simultaneously.

---

# ERP / Scope-Control Rule

Previously finalized pages are NOT reopened unless absolutely necessary.

Process improvements apply forward unless:
- critical correctness,
- broken rendering,
- or canonical consistency requires back-propagation.

This is intentional anti-perfectionism scope control.
