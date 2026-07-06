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

See the most recent `fence_addendum_<date>.md`

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

# Example OCR / Canonicalization Dialog

## Image Transmission Example

Dave:

> Image 8 of 75
> (8 of 1st subset -- 15)
>
> More coming.

or

> Image 32 of 72
> (15-from-1, 15-from-2, then 2 of 3rd subset -- 24)
>
> More coming.

or, more compactly:

> Image 2 of 24
>
> More coming

though that last, more-compact form should not be preferred.

---

## Canonical OCR Interaction Example

Dave:

> Image 32 of 72
> (15-from-1, 15-from-2, then 2 of 3rd subset -- 24)

[Dave uploads image.]

---

kaMMA:

[performs OCR]

[displays first-attempt OCR as unrendered Markdown]

[POSSIBLY (1.1): includes inline `⌨` uncertainty markers]

[POSSIBLY (1.2): includes `█` redaction markers]

[POSSIBLY (1.3): includes Markdown blockquote uncertainty explanations]

[POSSIBLY (1.4): separates notebook output from notebook code cells]

[POSSIBLY (1.5): preserves notebook-style rendering conventions]

---

Dave:

[reviews OCR attempt]

[POSSIBLY (2.1): corrects OCR mistakes]

[POSSIBLY (2.2): improves formatting]

[POSSIBLY (2.3): requests rendered version]

[POSSIBLY (2.4): reminds kaMMA of formatting conventions]

[POSSIBLY (2.5): changes redaction style]

[POSSIBLY (2.6): changes uncertainty formatting conventions]

[POSSIBLY (2.7): clarifies notebook-rendering intent]

[POSSIBLY (2.8): updates canonical workflow conventions]

Example:

> Please separate the output block from the next code cell.
>
> Also, use `███` instead of `▮▮▮`.
>
> And place the `⌨` inline at the exact uncertainty location.

---

kaMMA:

[POSSIBLY (3.1): incorporates corrections]

[POSSIBLY (3.2): produces rendered preview]

[POSSIBLY (3.3): explains uncertainty decisions]

[POSSIBLY (3.4): comments on notebook UX or OCR structure]

[POSSIBLY (3.5): updates formatting conventions moving forward]

---

Dave:

[POSSIBLY (4.1): "Penultimate approval."]

or

[POSSIBLY (4.2): requests further edits]

or

[POSSIBLY (4.3): requests downloadable cumulative Markdown]

---

kaMMA:

[POSSIBLY (5.1): renders final version]

[POSSIBLY (5.2): appends approved page to cumulative canonical Markdown]

[POSSIBLY (5.3): generates downloadable cumulative file]

[POSSIBLY (5.4): updates canonical workflow conventions]

---

Dave:

> Final approval.
>
> Ready for next image.

---

kaMMA:

> Ready for Image 33 of 72.

---

---

# OCR Approval-State Semantics

The OCR workflow distinguishes between:
- iterative OCR correction,
- rendered-preview approval,
- and canonical append approval.

These are distinct states.

---

## Penultimate Approval

Example:

```text
Dave:
> Penultimate approval.
```

Meaning:

- the current OCR state is sufficiently correct to generate:
  - a rendered Markdown preview,
  - or a candidate final rendering.

At this stage:
- rendering may still expose:
  - formatting problems,
  - Markdown ambiguities,
  - rendering inconsistencies,
  - or notebook-style issues.

Penultimate approval does NOT yet authorize:
- canonical append,
- cumulative-file generation,
- or workflow finalization.

---

## Final Approval

Example:

```text
Dave:
> Final approval.
```

Meaning:

- the OCR for the current page is considered canonical,
- and may now be appended to the cumulative Markdown file.

At this stage, kaMMA may:

```text
[POSSIBLY (5.1): append approved page to cumulative canonical Markdown]

[POSSIBLY (5.2): generate updated downloadable cumulative Markdown]

[POSSIBLY (5.3): update canonical rendering conventions moving forward]
```

---

# Canonical Short-Form OCR Flow

```text
D: [indicates page P]

k: [first OCR attempt, unrendered Markdown]

D: [possible corrections]

k: [updated OCR]

D: Penultimate approval.

k: [rendered Markdown preview]

D: [possible final corrections]

D: Final approval.

k: [append page to cumulative Markdown]
   [generate updated downloadable file]

D: [tests rendering externally, e.g. StackEdit]

D: [sends next page]
```

---

# Recommended Canonical Filename Convention

Example:

```python
f"{cumulative_filename_prefix}_{now:%Y-%m-%dT%H%M%S%z}.md"
```

Example rendered filename:

```text
jupy_nb_dwb_2026-05-27T075431-0400.md
```

This preserves:
- chronology,
- sortability,
- reproducibility,
- and synchronization clarity.

---

# Horizontal-Rule Recommendation

Avoid excessive horizontal separators.

Preferred style:

```markdown
Dave — OCR comments and corrections

kaMMA — rendered candidate preview
```

instead of repeated:

```markdown
--
```

Use a single horizontal rule:
- between major protocol sections,
- between ordinary conversational transitions.

Basically, if Dave puts, "blah -- blah blah," change those two hyphens to one horizontal line of whatever letter's width you feel is appropriate, but prefer CMOS.

---

---


# ERP / Scope-Control Rule

Previously finalized pages are NOT reopened unless absolutely necessary.

Process improvements apply forward unless:
- critical correctness,
- broken rendering,
- or canonical consistency requires back-propagation.

This is intentional anti-perfectionism scope control.
