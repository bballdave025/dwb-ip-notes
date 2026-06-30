# Template --- `docs/context_documents/README.md`

This directory contains **continuation-ready context documents** (Lab
Notebook / LN files).

These are structured restart points that allow work to resume with
minimal re-derivation after a pause or in a new chat.

## Purpose

Each context document should answer:

> **If I had to resume this project in a fresh environment, what would I
> need to know?**

They capture current architecture, terminology, design decisions, active
constraints, current milestone, immediate next steps, and important
insights.

Think of them as **checkpoint files for thinking**, not summaries.

## Documentation hierarchy

``` text
README.md
    ↓
Project Charter
    ↓
Lab Notebook / Context Documents
    ↓
Experiment Notes
```

## Header template

Use **double-brace placeholders** (`{{...}}`) instead of angle brackets.

Include: - Project name - Project description - Prepared timestamp -
Originating chat - Related chats/topics - Author attribution - Intent
for continuation - Usage instructions

## Naming

``` text
LN_<project>_YYYY-MM-DD_<optional-tag>_-_<slug>.md
```

Examples:

``` text
LN_ncjn_2026-05-01_ctx01_-_config-class-architecture.md
LN_dial_2026-06-30_ctx01_-_experiment-000-setup.md
```

## Retrieval

1.  Sort by filename.
2.  Open the newest `LN_*`.
3.  Resume from the "Immediate Next Steps" section.

## Pre-Context-Document Prompt (PCDP)

Before pasting a context document into a new chat, optionally send a
short PCDP that contains:

-   Current work
-   Immediate next steps
-   Name of the upcoming context document
-   Previous chat title
-   Preparation timestamp
-   Immediate focus

### Important note

In practice, the **Instructions for Next Message** block is usually
**omitted**.

Experience has shown that models respond more reliably when the PCDP
simply establishes context and immediate focus. The context document
itself should remain the authoritative project state.

------------------------------------------------------------------------

*End of template README*
