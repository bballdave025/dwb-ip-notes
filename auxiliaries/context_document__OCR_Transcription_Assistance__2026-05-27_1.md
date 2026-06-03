# CONTEXT DOCUMENT — Continuation

## Project

**Name:**  
OCR Transcription Assistance

**Description:**  
This project performs clean-room OCR transcription of redacted Jupyter notebook scans into canonical Markdown. The workflow preserves OCR uncertainty, redactions, notebook structure, rendering semantics, and iterative approval state while generating cumulative downloadable Markdown artifacts suitable for archival, reproducibility, and future notebook reconstruction.

---

## Continuation Metadata

**Prepared at:**  
1748356900_2026-05-27T09:08:20-0400  
(Generated via: `date +'%s_%Y-%m-%dT%H:%M:%S%z'` in Boston time)

**Continued from chat:**  
OCR Transcription Assistance

**Also involving:**  
- Canonical OCR workflow specification
- Jupyter notebook reconstruction conventions
- Redaction / uncertainty annotation conventions
- Clean-room IP-preserving transcription workflow
- Markdown rendering robustness
- OCR transmission / ordering protocol
- *(plus incidental workflow and commuting discussion)*

---

## Author / Source

**User (GitHub):**  
@bballdave025

**User (ChatGPT):**  
thebballdave025@gmail.com

---

## Intent for This Context

Resume canonical OCR transcription and notebook reconstruction with minimal re-derivation. Preserve all established conventions concerning OCR uncertainty, redaction semantics, notebook rendering, cumulative-file generation, approval-state semantics, and transmission-order metadata.

---

## Usage Instructions (for next chat)

- Treat this document as **authoritative state** / **contract document**
- Continue from this point with **minimal re-derivation**
- Preserve all established OCR formatting conventions unless explicitly changed
- Prefer forward-only refinement rather than reopening finalized pages
- Preserve notebook-style rendering semantics
- Maintain distinction between:
  - OCR uncertainty,
  - intentional editorial correction,
  - and true redaction

---

# Established OCR / Markdown Conventions

## Redaction Marker

Inline redactions use:

```text
███
```

Approximate width matching is encouraged but not mandatory.

Whole-line or multi-line redactions may use:

```text
[line redacted]
[multiple lines redacted]
[project-related markdown documentation redacted]
```

Prefer semantic descriptions when safely possible.

---

## Uncertainty Marker

Inline OCR uncertainty uses:

```text
⌨
```

The `⌨` marker should appear:
- inline,
- at or immediately after the uncertainty location.

Example:

```python
CONTACT Dave⌨ (b███████), THE CURRENT MAINTAINER
```

---

## Uncertainty Explanation Format

After uncertain regions, use Markdown blockquote formatting:

```markdown
>        ^⌨v explanation text
```

Example:

>        ^⌨v redacted maintainer/contact information preserved intentionally

These explanations:
- preserve epistemic honesty,
- prevent silent hallucinated cleanup,
- and support targeted later review.

---

# Notebook Rendering Conventions

## Notebook Output Style

Notebook output is rendered separately from code cells.

Example:

```html
<sup><code>Out&nbsp;[FIRST]:</code></sup>
```

Subsequent notebook outputs use semantic labels such as:

```html
<sup><code>Out&nbsp;[SECOND]:</code></sup>
<sup><code>Out&nbsp;[THIRD]:</code></sup>
<sup><code>Out&nbsp;[FOURTH]:</code></sup>
```

These intentionally distinguish OCR reconstruction from literal historical execution counters.

---

## Notebook Cell Headers

Canonical style:

```python
#=============
# FIFTH CELL   ^^^ LOOK ABOVE ^^^
#               |||            |||
#=============
```

Spacing should be preserved carefully.

---

## Keyboard Instructions

Outside code cells:
- prefer rendered HTML:

```markdown
<kbd>Shift</kbd> + <kbd>Enter</kbd>
```

Inside code cells:
- prefer plain-text notation:

```text
[Shift] + [Enter]
```

---

# Markdown Fence Strategy

Use an outer fence longer than any fence that appears inside it.

Example notation:

| Part of Code Block | Markdown to Use |
| :--- | :--- |
| OUTER OPEN: | four backticks + `markdown` |
| INNER OPEN: | five backticks + `python` |
| PYTHON CONTENT: | ... |
| INNER CLOSE: | five backticks |
| PLAIN TEXT CONTENT: | ... |
| OUTER CLOSE: | four backticks |

where the ` + ` should be read as concatenation. i.e. we could rewrite the whole thing, looking forward to replacing all contiguous strings of `B` having length greater than three so that each `B` gets replaced with a backtick

| Part of Code Block | Markdown to Use |
| :--- | :--- |
| OUTER OPEN: | `BBBBmarkdown` |
| INNER OPEN: | `BBBBBpython` |
| PYTHON CONTENT: | ... |
| INNER CLOSE: | `BBBBB` |
| PLAIN TEXT CONTENT: | ... |
| OUTER CLOSE: | `BBBB` |

Do not rely on this section rendering perfectly in all Markdown renderers. It is a protocol note, not executable Markdown.

This prevents internal notebook fences from breaking rendering.

---

# OCR Approval-State Semantics

## Penultimate Approval

Example:

```text
Dave:
> Penultimate approval.
```

Meaning:
- current OCR state is sufficient for rendered preview generation,
- but may still receive rendering or formatting corrections.

Penultimate approval does NOT authorize:
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
- current OCR state is canonical,
- and may now be appended to the cumulative Markdown file.

At this stage, kaMMA may:
- append approved page to cumulative Markdown,
- generate downloadable cumulative Markdown,
- update canonical conventions moving forward.

---

# Canonical OCR Workflow

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

# OCR Transmission / Ordering Conventions

OCR transmission should preserve:
- sequential ordering,
- grouping semantics,
- provenance,
- continuation state,
- and resumability.

---

## Human-Readable Sequential Form

Example:

```text
Image 8 of 75
(8 of 1st subset -- 15)

More coming.
```

Example:

```text
Image 32 of 72
(15-from-1, 15-from-2, then 2 of 3rd subset -- 24)

More coming.
```

---

## Compact Canonical Form

Preferred compact canonical representation:

```text
IMG[G=32/72,S=3/4,L=2/24]
```

Where:
- `G` = global position,
- `S` = subset position,
- `L` = local position within subset.

---

# Canonical Filename Convention

Preferred filename pattern:

```python
f"{cumulative_filename_prefix}_{now:%Y-%m-%dT%H%M%S%z}.md"
```

Example:

```text
jupy_nb_dwb_2026-05-27T075431-0400.md
```

This preserves:
- chronology,
- sortability,
- synchronization clarity,
- and reproducibility.

---

# ERP / Scope-Control Rule

Previously finalized pages are NOT reopened unless:
- critical correctness,
- broken rendering,
- or canonical consistency
requires back-propagation.

Prefer:
- forward-only refinement,
- stable cumulative progress,
- and lean-to iteration
over recursive perfectionistic cleanup.

---

# Current OCR Progress State

Current completed / finalized pages:
- through Image 8 of 75

Current working page:
- Image 9 of 75
- (9 of 1st subset -- 15)

Current notebook region:
- beginning of FIFTH CELL
- explanatory `c1=''' ... '''` setup/documentation block
