# GitHub Project & Idea Inventory — `bballdave025`

**Generated:** 2026-08-24  
**Purpose:** Broad inventory for career planning, résumé/portfolio work, and project prioritization.  
**Scope rule:** Include work from **idea-only** through **finished/published**. Do **not** silently upgrade planned work into completed work.

## Status legend

- **Idea-only** — documented concept; no meaningful implementation established.
- **Scaffolded** — repository/structure exists, but implementation is minimal.
- **Prototype** — working or partly working implementation exists.
- **Active** — substantial work exists and development is ongoing.
- **Substantially complete** — core goal has been demonstrated; refinement/documentation may remain.
- **Finished / published** — a stable deliverable, publication, release, or completed demonstration exists.
- **Support / training / reference** — useful work, but not best represented as an independent research/product project.
- **Needs deeper inspection** — repository is included, but this pass did not establish enough from the repository itself to describe it safely.

## Extraction principles

This inventory is intentionally broader than a polished portfolio. A whimsical repository name, a failed experiment, an abandoned direction, a learning project, a utility, or a predecessor repository is **not excluded** merely because it is unfinished or unfashionable.

For each entry, the distinction is:

1. **What the project is trying to ask or do**
2. **What actually exists**
3. **What remains planned**
4. **What skills/differentiators it can credibly demonstrate**
5. **How it relates to sibling/predecessor repositories**

Where the source material did not establish a claim, this inventory says so rather than filling the gap.

---

# A. Research / ML / scientific-computing projects

## `manuscript-waste-reuse-finder`

**Repository:** <https://github.com/bballdave025/manuscript-waste-reuse-finder>  
**Status:** **Finished/published initial phase; active research lineage**

**What it is:** The original public-facing “Fragment Finder” / RMFB project: use machine learning to find document images containing reused manuscript fragments in bindings, with applications to family history, manuscript studies, palaeography, codicology, and fragmentology.

**What actually exists:** A 2024 Family History Technology Workshop/Conference research presentation; an Academia.edu paper; a documented labeled dataset used for an early transfer-learning prototype; ResNet-50-based classification code; dataset examples with provenance/citation notes; and substantial image-preparation and reproducibility documentation. The README reports an early 622-image labeled dataset and a 96.77% test accuracy for the prototype, which should be treated as an early result rather than the endpoint of the later RMMFB program.

**Skills / differentiators:** Computer vision, transfer learning, historical-document data curation, image rights/provenance, archive/library research, reproducibility, cross-disciplinary research framing, dataset construction, and public scientific communication.

**Career relevance:** **Very high — applied science / CV / data curation / research ownership.**

---

## `binding-unwinding`

**Repository:** <https://github.com/bballdave025/binding-unwinding>  
**Status:** **Working support pipeline / prototype**

**What it is:** Data-engineering companion to the RMFB work for extracting manuscript/document images from multi-image PDFs and normalizing them into dataset-ready files.

**What actually exists:** PyMuPDF extraction code, batch-processing procedures, filename-renaming pipelines, ImageMagick conversion/checking workflows, reproducible Conda environments, error checks, and run logs. The README explicitly frames the tool as preparation for the manuscript-reuse training dataset.

**Skills / differentiators:** Bash/Cygwin, Python, PyMuPDF, ImageMagick, batch I/O, file naming/normalization, reproducibility, progress/error instrumentation, dataset preparation.

**Career relevance:** **High — practical ML data engineering and reproducibility.**

---

## `rib-wrist-in-bin-din`

**Repository:** <https://github.com/bballdave025/rib-wrist-in-bin-din>  
**Status:** **Active research/planning repository; RMMFB lineage**

**What it is:** “Reused Information Bearing Writing Surface Traces in Bindings,” a later RMMFB research/planning home.

**What actually exists:** The repository contains the important `Paper_Code_Prep_01` notebook family and project-vision / experimental-planning material used to reason about RMMFB model families, high-resolution imagery, explainability, and paper structure.

**Planned vs. actual:** Some notebook material is architectural/model planning rather than evidence that each proposed model was run. Preserve that distinction.

**Skills / differentiators:** Research synthesis, CV experiment design, model comparison planning, explainability, high-resolution image reasoning, literature-to-experiment translation.

**Career relevance:** **Very high — applied-science thinking and research direction.**

---

## `fhtw-paper-code-prep`

**Repository:** <https://github.com/bballdave025/fhtw-paper-code-prep>  
**Status:** **Active experimental infrastructure; working end-to-end prototype**

**What it is:** Experimental scaffold for RMMFB/FHTW model work across local and AWS/SageMaker environments.

**What actually exists:** Cross-platform experiment scaffolding (`structure.sh` / PowerShell counterpart), CIFAR-10 experimental stepping stones, notebook templates, environment verification, run artifacts, logging, and the `p_01` → `p_03_e2e` progression previously inspected. The README contains a deliberately constrained local end-to-end CIFAR-10 baseline and AWS/SageMaker notes.

**Interpretation:** CIFAR-10 is best understood as the proving ground for experimental machinery, not as the scientific RMMFB result.

**Career relevance:** **Very high — ML engineering, reproducibility, AWS/SageMaker readiness, experimental discipline.**

---

## `fhtw-manuscript-models`

**Repository:** <https://github.com/bballdave025/fhtw-manuscript-models>  
**Status:** **Scaffolded / model-family support repository**

**What it appears to be:** A repository in the FHTW/RMMFB family concerned with manuscript model work. This pass establishes the repository's existence but does not safely establish which planned model families were actually executed from its contents.

**Career relevance:** Potentially high, but **needs deeper file-level inspection before résumé claims are made.**

---

## `congenial-chainsaw-rmfb-html`

**Repository:** <https://github.com/bballdave025/congenial-chainsaw-rmfb-html>  
**Status:** **Historical prototype / abandoned “cathedral,” with useful artifacts**

**What it is:** An elaborate HTML-oriented RMMFB classification/helper presentation that was deliberately abandoned in favor of smaller, more usable classification documents.

**What actually matters now:** The repo preserves multiple levels of classification guidance, including simplified “1-or-2-page” material and earlier detailed versions. It is useful as ontology/documentation history, not as something to finish.

**Career relevance:** Moderate — demonstrates UX/documentation iteration and willingness to abandon overbuilt solutions.

---

## `rmfb-fragm-journal-draft`

**Repository:** <https://github.com/bballdave025/rmfb-fragm-journal-draft>  
**Status:** **Scaffolded / draft-publication repository**

**What it is:** Fragmentology-journal-facing RMFB/RMMFB drafting space.

**What actually exists:** Repository structure is present; this inventory does not claim that a submission-ready manuscript is already complete.

**Career relevance:** High once connected to the finished RMMFB manuscript; currently a publication-workspace artifact.

---

## `rmfb-tech-draft`

**Repository:** <https://github.com/bballdave025/rmfb-tech-draft>  
**Status:** **Scaffolded / technical-draft repository**

**What it is:** Technical-paper/draft branch of the RMFB/RMMFB publication family.

**Career relevance:** Supporting evidence of research planning; not independently a finished project.

---

## `nyquist-text-existence`

**Repository:** <https://github.com/bballdave025/nyquist-text-existence>  
**Status:** **Active preregistered research project**

**What it is:** NTEC — a project about representational thresholds for whether writing *exists in the sampled image at all*, distinct from whether a recognizer can read it.

**What actually exists:** Public vision/scope notes, experimental-design scaffolding, thematic examples, a preregistration submitted to OSF, and later addenda. The repository explicitly separates text existence from text recognition, model uncertainty from information-theoretic absence, and recoverable from unrecoverable historical signal.

**Skills / differentiators:** Sampling theory, imaging, falsifiable experimental design, preregistration/open science, CV failure analysis, information-theoretic reasoning, historical-document imaging.

**Career relevance:** **Very high — unusual, researchable applied-science idea with strong methodological framing.**

---

## `latent-forge`

**Repository:** <https://github.com/bballdave025/latent-forge>  
**Status:** **Active experimental/learning project**

**What it is:** Lean recommender-system laboratory centered on rank-1 and matrix-factorization baselines and small interpretable experiments that improve holdout MSE.

**What actually exists:** Jupyter experimental narrative, reusable model/evaluation code, experiment plans, tests, and leaderboard/submission workflow. The repository explicitly requires each new idea to state what assumption changes, why improvement is expected, how success will be measured, and whether added complexity is justified.

**Skills / differentiators:** Matrix factorization, collaborative filtering, recommender systems, holdout evaluation, low-rank reasoning, synthetic-data design, disciplined experiment iteration.

**Career relevance:** **High — ML fundamentals, mathematical modeling, recommender systems, experimentation.**

---

## `jabbervec-l2v`

**Repository:** <https://github.com/bballdave025/jabbervec-l2v>  
**Status:** **Prototype / active experimental project**

**What it is:** A small, inspectable character-level language-modeling laboratory for asking what geometric structure emerges when letters acquire learned embeddings from English-like text. Its playful framing is literary nonsense, but the underlying questions concern representation learning, embedding geometry, dimensionality, and information retained under low-rank approximation.

**What actually exists:** A Python-package layout, `pyproject.toml`, tests, examples, scripts, and source modules for data handling, model training, generation, visualization, and low-rank analysis. The documented minimal experiment trains a next-character model with a learned embedding matrix, generates English-ish strings, and visualizes character embeddings with PCA.

**Planned extensions:** Embedding-dimension sweeps, dictionary-vs.-corpus comparison, truncated-SVD experiments, and an arbitrary-renaming/distributional-semantics experiment are described as future work rather than completed results.

**Skills / differentiators:** Character-level language modeling, embeddings, PCA/SVD, low-rank reasoning, experimental design, Python packaging, generation/visualization tooling.

**Career relevance:** **High for applied-science/research thinking; intentionally toy-scale rather than frontier-model scale.**

---

## `bilingual-boundary-lab`

**Repository:** <https://github.com/bballdave025/bilingual-boundary-lab>  
**Status:** **Prototype / active experimental project**

**What it is:** Visualization-first investigation of what deliberately simple statistical language models can learn from Tolstoy's *War and Peace* in Russian with embedded original French passages.

**What actually exists:** Reproducible corpus builder, script-run classification/visualization, word- and character-level n-gram experiments, portable Bash/PowerShell bootstrap tooling, tests, and a first-experiment runner.

**Research question:** How far can simple models get on language switching, boundary persistence, and memorization when restricted to one bilingual literary corpus?

**Career relevance:** **High — NLP, multilingual text, visualization, controlled baselines, reproducibility.**

---

## `pocket-cocktail-party`

**Repository:** <https://github.com/bballdave025/pocket-cocktail-party>  
**Status:** **Scaffolded-to-prototype experimental project**

**What it is:** Blind source separation / cocktail-party project beginning with classical ICA and deliberately moving from synthetic geometry-derived mixtures toward messy real recordings.

**What actually exists:** Detailed mathematical and experimental design, source-first synthetic modeling, geometry-derived mixing matrices, consent/ethics documentation structure, package/test scaffold, and explicit milestones. The README's checklist still marks major experimental milestones as planned, so the design should not be represented as completed separation results.

**Skills / differentiators:** ICA/BSS, signal processing, linear algebra, harmonic modeling, geometry, ethical data collection/consent, experimental failure-mode design.

**Career relevance:** **High — signal processing + mathematical modeling + responsible experimentation.**

---

## `mendeleev-spelling-bee`

**Repository:** <https://github.com/bballdave025/mendeleev-spelling-bee>  
**Status:** **Working prototype with tests/releases**

**What it is:** Multilingual word-decoding/NLP game that finds words representable as sequences of chemical-element symbols, extending beyond Latin-script English into Cyrillic and other writing systems.

**What actually exists:** CLI, test-driven development, Latin/Cyrillic symbol handling, dictionary inputs, pytest coverage, documented passing tests, and tagged version/release work.

**Skills / differentiators:** NLP/tokenization, Unicode/multiscript handling, CLI design, TDD/pytest, Bash/web-data extraction, packaging.

**Career relevance:** **Medium-high — memorable small project demonstrating Unicode/NLP/software craftsmanship.**

---

## `marco-polo-malayalam`

**Repository:** <https://github.com/bballdave025/marco-polo-malayalam>  
**Status:** **Prototype / experimental workflow**

**What it is:** An HTR-oriented experiment applying an AGES-type workflow to Malayalam.

**What actually exists:** The README is extremely terse, so implementation depth should be established from files before making detailed claims.

**Career relevance:** Potentially high for multilingual OCR/HTR; **needs deeper inspection before résumé-level specificity.**

---

## `rwkv-lora`

**Repository:** <https://github.com/bballdave025/rwkv-lora>  
**Status:** **Experimental / substantial artifact repository**

**What it is:** RWKV/LoRA fine-tuning experimentation in the FamilySearch/volunteer-learning lineage.

**What we know safely:** Significant repository size and prior documented experimentation exist, including an attempted LoRA proof of concept. A historically observed training/validation-loss behavior needs to be revisited before summarizing the experiment as successful.

**Career relevance:** **High as an honest failed/ambiguous experiment** if reconstructed carefully: PEFT/LoRA, sequence models, training diagnostics, and willingness to analyze failure.

---

## `RWKV5-LM-LoRA`

**Repository:** <https://github.com/bballdave025/RWKV5-LM-LoRA>  
**Status:** **Experimental / related RWKV-LoRA repository**

**Relationship:** Treat as part of the same RWKV/LoRA family until file-level archaeology establishes whether it is a fork, a cleaned implementation, or a distinct experiment.

**Career relevance:** Supporting artifact; avoid double-counting with `rwkv-lora`.

---

## `info-rwkv-lora-learning-ref`

**Repository:** <https://github.com/bballdave025/info-rwkv-lora-learning-ref>  
**Status:** **Reference / learning-support repository**

**What it is:** Supporting material for learning/reconstructing RWKV + LoRA work rather than a separate portfolio research result.

---

## `discrete_fourier_transforms_and_sampling`

**Repository:** <https://github.com/bballdave025/discrete_fourier_transforms_and_sampling>  
**Status:** **Learning / scientific-computing project**

**What it is:** Repository centered on discrete Fourier transforms and sampling. This is adjacent to NTEC's sampling-theory interests but should not automatically be presented as part of NTEC without a file-level connection.

**Career relevance:** Mathematical/scientific-computing evidence; deeper inspection would be useful before drafting bullets.

---

## `higgs_boson_visualized`

**Repository:** <https://github.com/bballdave025/higgs_boson_visualized>  
**Status:** **Scientific visualization / physics project**

**What it is:** Higgs-boson/particle-physics visualization work.

**Career relevance:** Useful evidence of physics-domain communication, quantitative visualization, and scientific background. File-level review is recommended before specifying methods.

---

## `higgs_for_help`

**Repository:** <https://github.com/bballdave025/higgs_for_help>  
**Status:** **Physics support / companion repository**

**Relationship:** Likely part of the Higgs/physics visualization or explanation family; do not count as a separate major project until contents establish distinct work.

---

## `style-trajectories`

**Repository:** <https://github.com/bballdave025/style-trajectories>  
**Status:** **Idea/scaffold only**

**Evidence:** Repository exists but is currently effectively empty at repo-size level.

**Career relevance:** None yet beyond documenting an idea direction.

---

# B. NLP, OCR, text/data, and small experimental projects

## `text-cleanroom`

**Repository:** <https://github.com/bballdave025/text-cleanroom>  
**Status:** **Active tooling project**

**What it is:** Deterministic toolkit for detecting, reporting, normalizing, and repairing messy text and filename artifacts from real datasets.

**What actually exists:** Detection of literal/percent-encoded spaces and mixed encodings; structured reporting; filename/text repair; normalization/denormalization design; CLI/package structure; provenance/scope documentation.

**Design principles:** Determinism, observability before correction, reproducibility/auditability, separation of detection vs. fixing vs. normalization.

**Career relevance:** **High — data quality, Unicode/encoding, dataset hygiene, robust preprocessing.**

---

## `ancestry-freq`

**Repository:** <https://github.com/bballdave025/ancestry-freq>  
**Status:** **Finished small job-application/demo project**

**What it is:** Word-frequency/NLP comparison of an Ancestry Data Scientist (NLP) job description and résumé, with a Binder-launchable notebook.

**Career relevance:** Small but concrete NLP/job-analysis demo; not a flagship project.

---

## `job-app-word-freq`

**Repository:** <https://github.com/bballdave025/job-app-word-freq>  
**Status:** **Job-search NLP/tooling project**

**What it appears to be:** A generalized relative of the job-description/résumé word-frequency work.

**Career relevance:** Useful as pragmatic text-analysis tooling; deeper inspection needed before distinguishing it from `ancestry-freq`.

---

## `envelope-zip-reading`

**Repository:** <https://github.com/bballdave025/envelope-zip-reading>  
**Status:** **Needs deeper inspection**

**Potential domain:** The repository name suggests a document-reading/OCR task, but this pass did not establish enough from source contents to describe the implementation safely.

---

## `english-gorf`

**Repository:** <https://github.com/bballdave025/english-gorf>  
**Status:** **Needs deeper inspection**

No detailed claim is made from the repository name alone.

---

## `scripture-parsing`

**Repository:** <https://github.com/bballdave025/scripture-parsing>  
**Status:** **Text-parsing project; deeper inspection recommended**

**Career relevance:** Potential evidence for structured-text parsing/NLP, but implementation details were not established in this pass.

---

## `nlp_w_pytorch_zhongyu-pan`

**Repository:** <https://github.com/bballdave025/nlp_w_pytorch_zhongyu-pan>  
**Status:** **Training/coursework repository**

**What it is:** NLP-with-PyTorch learning work associated with Zhongyu Pan material.

**Career relevance:** Useful supporting evidence of structured study; should not be represented as original research.

---

# C. General ML/software tooling

## `multimodal-jupy-logger`

**Repository:** <https://github.com/bballdave025/multimodal-jupy-logger>  
**Status:** **Early experimental tooling**

**What it is:** General-purpose system for logging, preserving, and replaying multimodal Jupyter/IPython workflows as durable event streams.

**What actually exists:** Jupyter/IPython magics, manifest-based logging, MIME-aware artifact persistence, HTML/Markdown replay output, notebook backup helpers, and optional PDF-export support.

**Skills / differentiators:** Jupyter internals, MIME bundles, provenance/logging, reproducible experiment capture, software architecture.

**Career relevance:** **High for ML engineering / reproducibility / developer tooling.**

---

## `no-code-jupyter-nb`

**Repository:** <https://github.com/bballdave025/no-code-jupyter-nb>  
**Status:** **Working toolkit / package**

**What it is:** Lightweight no-code/low-code interface toolkit inside Jupyter.

**What actually exists:** Dropdown factories, file selectors, native file dialogs, clipboard helpers, URI buttons, Markdown helpers, structured configuration objects, editable/installable package workflow.

**Career relevance:** **High for human-centered tooling, notebook UX, and enabling non-programmer workflows.**

---

## `dwb_python_util`

**Repository:** <https://github.com/bballdave025/dwb_python_util>  
**Status:** **General utility library**

Reusable Python helpers. Treat as supporting software-engineering evidence rather than a flagship project unless specific utilities are selected for discussion.

---

## `dwb_util`

**Repository:** <https://github.com/bballdave025/dwb_util>  
**Status:** **General utility repository**

Likely cross-language/general utilities; deeper inspection needed for a specific résumé claim.

---

## `dwb-aws-nb-typings`

**Repository:** <https://github.com/bballdave025/dwb-aws-nb-typings>  
**Status:** **AWS/notebook support project**

Substantial repository devoted to notebook/AWS-related developer workflow. Deeper inspection is appropriate before deciding whether this is portfolio-worthy or primarily personal tooling.

---

## `dotfiles`

**Repository:** <https://github.com/bballdave025/dotfiles>  
**Status:** **Developer-environment tooling**

Career signal: Linux/shell fluency and reproducible environment configuration; not a standalone research project.

---

## `gtgtdd-sys`

**Repository:** <https://github.com/bballdave025/gtgtdd-sys>  
**Status:** **Active personal workflow/system tooling**

A GTD/task-system repository. Useful evidence of workflow/tool design, but usually peripheral to ML/applied-science applications.

---

# D. Learning, portfolio, and demonstration repositories

## `aws-udemy-pacing`

**Repository:** <https://github.com/bballdave025/aws-udemy-pacing>  
**Status:** **Working personal automation**

Python tooling that creates spreadsheet-based pacing/progress tracking for technical courses/certifications. The README reports completed pacing work for AWS Cloud Practitioner and AWS ML Specialist coursework, with plans to generalize input creation.

**Career relevance:** Small automation / spreadsheet-generation evidence.

---

## `didactic-spoon`

**Repository:** <https://github.com/bballdave025/didactic-spoon>  
**Status:** **Training/course-notes repository**

DeepLearning/Keras/TensorFlow tutorial/course notebook work based on deeplizard resources. Good evidence of self-study, but not original research.

---

## `educative-interview-prep`

**Repository:** <https://github.com/bballdave025/educative-interview-prep>  
**Status:** **Interview-preparation/coursework repository**

Keep in the broad inventory, but do not present as an original project unless it contains clearly independent extensions.

---

## `palmerpenguins`

**Repository:** <https://github.com/bballdave025/palmerpenguins>  
**Status:** **Data-science learning/demo repository**

Likely uses the Palmer Penguins dataset. Treat as learning/demo material unless deeper inspection reveals an independent analytical contribution.

---

## `visualization_portfolio`

**Repository:** <https://github.com/bballdave025/visualization_portfolio>  
**Status:** **Portfolio / visualization collection**

Potentially useful supporting evidence for data communication and plotting. Individual exhibits should be selected after file-level review.

---

## `portfolio-amz-agi`

**Repository:** <https://github.com/bballdave025/portfolio-amz-agi>  
**Status:** **Portfolio-assembly repository**

A job/AGI-facing portfolio surface; should primarily point to stronger underlying projects rather than be counted as another independent project.

---

## `portfolio-resume`

**Repository:** <https://github.com/bballdave025/portfolio-resume>  
**Status:** **Portfolio/resume support repository**

Career-material assembly, not an independent technical project.

---

## `stem-showcase`

**Repository:** <https://github.com/bballdave025/stem-showcase>  
**Status:** **Demonstration/showcase repository**

Potentially useful science/education portfolio material; deeper inspection needed to identify which pieces deserve independent mention.

---

# E. Historical / support / web / reference repositories

## `general_reference_info_and_logs`

**Repository:** <https://github.com/bballdave025/general_reference_info_and_logs>  
**Status:** **Reference/log archive**

Large supporting archive. Mine selectively for provenance, methods, or reproducibility evidence; do not treat the archive itself as one coherent project.

---

## `yahoo-verizon-turbify-html`

**Repository:** <https://github.com/bballdave025/yahoo-verizon-turbify-html>  
**Status:** **Web/HTML support or migration repository**

Include in full inventory, but probably peripheral to ML/applied-science positioning.

---

## `fhtw-pre-ravi-sagemaker-flask`

**Repository:** <https://github.com/bballdave025/fhtw-pre-ravi-sagemaker-flask>  
**Status:** **Small FHTW/AWS/Flask scaffold**

Likely an early precursor/support branch for deployment or SageMaker work. Treat as historical infrastructure until contents establish a distinct deliverable.

---

## `start-pirate`

**Repository:** <https://github.com/bballdave025/start-pirate>  
**Status:** **Tiny scaffold / needs deeper inspection**

---

## `start-pirate-now`

**Repository:** <https://github.com/bballdave025/start-pirate-now>  
**Status:** **Small scaffold/prototype / needs deeper inspection**

Likely related to `start-pirate`; avoid double-counting until contents establish the relationship.

---

## `solid-rotary-phone`

**Repository:** <https://github.com/bballdave025/solid-rotary-phone>  
**Status:** **Needs deeper inspection**

No content-level claim is made from the generated repository name.

---

## `double-p-double-n`

**Repository:** <https://github.com/bballdave025/double-p-double-n>  
**Status:** **Needs deeper inspection**

No content-level claim is made from the repository name alone.

---

## `upgraded-waffle`

**Repository:** <https://github.com/bballdave025/upgraded-waffle>  
**Status:** **Large repository; needs deeper inspection**

Its large size suggests substantial artifacts, but size is not evidence of project maturity or originality. Worth a targeted pass.

---

## `vayzday`

**Repository:** <https://github.com/bballdave025/vayzday>  
**Status:** **Needs deeper inspection**

No speculative description is assigned.

---

## Personal-domain repository intentionally not mined

One owned repository appears to be a personal-domain tracker. It is **intentionally excluded from substantive career/project analysis** here; the existence of a GitHub repository does not make its private-domain subject matter useful or appropriate for a job-search inventory.

---

# F. `dwb-ip-notes`: idea-stage and vision-stage inventory

**Repository:** <https://github.com/bballdave025/dwb-ip-notes>  
**Repository status:** **Active public idea/provenance registry**

This repository is explicitly an intellectual-property hygiene and precedence system: concise, dated, public notes for independently developed project ideas. It is not itself a claim that every note is novel, implemented, or ready for commercialization.

The following entries are therefore classified **Idea-only / vision-stage unless a separate implementation repository exists.**

## Ideas with separate implementation/research repositories

### RMFB / RMMFB
- `IP_Notes_-_RMFB_2025-12-29.md`
- `IP_Notes_-_RMFB_2026-01-06.md`
- Implementation/research family: `manuscript-waste-reuse-finder`, `rib-wrist-in-bin-din`, `fhtw-paper-code-prep`, journal/draft repos.

### Nyquist Text Existence
- `IP_Notes_-_Nyquist_Text_Existence`
- Implementation/research repo: `nyquist-text-existence`.

### Latent Forge recommender systems
- `IP_Plus_Vision_-_LatentForge_Recommender_Systems_2026-06-09.md`
- Implementation repo: `latent-forge`.

### Multimodal Jupy Logger
- `IP_Notes_-_Multimodal_Jupy_Logger_2026-06-08.md`
- Implementation repo: `multimodal-jupy-logger`.

### No-Code Jupyter Notebooks
- `IP_Notes_-_No_Code_Jupyter_Notebooks_2026-05-18.md`
- Implementation repo: `no-code-jupyter-nb`.

### Pocket Cocktail Party / BSS / ICA
- `IP_Plus_Vision_-_Pocket_Cocktail_Party_BSS_ICA_2026-06-24.md`
- Implementation repo: `pocket-cocktail-party`.

## Idea/vision notes without a separately identified implementation repo in this pass

### Ambiguity Corpus
- `IP_Notes_-_Ambiguity_Corpus_2025-12-30.md`
- `IP_Notes_-_Ambiguity_Corpus_2026-01-06.md`
- **Status:** Idea/vision lineage; later note supersedes or extends earlier one.
- **Potential signal:** Data curation / ambiguity / model evaluation. Read note before drafting a résumé claim.

### Cyrillic Through Latin OCR
- `IP_Notes_-_CyrillicThruLatinOCR_2025-12-31.md`
- **Status:** Idea-only / vision-stage.
- **Potential signal:** OCR, cross-script representation, transliteration/encoding.

### DIAL DSL Experiment 000
- `IP_Notes_-_DIAL_DSL_Experiment_000_2026-06-30.md`
- **Status:** Idea/experiment note.
- **Description:** Acronym/title alone is insufficient for a safe technical summary; note-level reading required.

### ED / SPL / CF
- `IP_Notes_-_ED_SPL_and_CF_2026-06-15.md`
- **Status:** Substantial idea note.
- **Description:** Acronyms are intentionally not expanded here without reading the note.

### Measuring Instruction Inconsistency
- `IP_Notes_-_Measuring_Instruction_Inconsistency_2025-12.md`
- **Status:** Idea/measurement proposal.
- **Potential signal:** LLM/instruction evaluation and quantitative consistency analysis.

### Mechanics — Lagrange / Hamilton / T-V simulations
- `IP_Notes_-_Mechanics_Lagrange_Hamilton_T_V_Sims_2026-06-04.md`
- **Status:** Idea/vision-stage computational-physics project.
- **Potential signal:** Classical mechanics, simulation, mathematical modeling, scientific computing.

### MorphoGender
- `IP_Notes_-_MorphoGender.md`
- **Status:** Idea-only.
- **Potential signal:** Morphology/linguistics/NLP; read note before making more specific claims.

### NORa
- `IP_Notes_-_NORa_2026-01-0x.md`
- **Status:** Placeholder-level note (very small).
- **Career value now:** Minimal until expanded.

### RLHF incomplete ontology / related ideas
- `IP_Notes_-_RLHF_Incomplete_Ontology_etc_2026-06-04.md`
- **Status:** Idea/vision-stage.
- **Potential signal:** RLHF, ontology completeness, annotation/evaluation design.

### Text and filename encoding / decoding / normalization
- `IP_Notes_-_Text_and_Filename_Encoding_Decoding_Normalization_2026-03-30.md`
- **Status:** Idea/vision note with implemented relative in `text-cleanroom`.

### Twain/Feynman Model Collapse
- `IP_Notes_-_TwainFeynman_ModelCollapse_2026-01-01.md`
- **Status:** Placeholder-level note (very small).
- **Career value now:** Minimal until developed.

### Design by Inverse Angular Light
- `IP_Plus_Vision_-_Design_by_Inverse_Angular_Light_2026-06-30.md`
- **Status:** Vision-stage project.
- **Description:** Read the note before summarizing; title suggests optics/geometry but no stronger claim is made here.

### NLP-oriented symbolic encodings for visual structure
- `IP_Plus_Vision_-_NLP_oriented_Symbolic_Encodings_for_Visual_Structure_2026-05-23.md`
- **Status:** Vision-stage.
- **Potential signal:** Bridging computer vision and symbolic/NLP representations.

### Paper/Pencil neural networks / energy
- `IP_Plus_Vision_-_PaperPencil_NNs_Energy_2026-01-01.md`
- **Status:** Vision-stage.
- **Potential signal:** Neural-network interpretation/education and energy-based reasoning; read note for exact thesis.

### Symbolized Persistence Under Quantized Projection
- `IP_Plus_Vision_-_Symbolized_Persistence_Under_Quantized_Projection_2026-05-23.md`
- **Status:** Vision-stage.
- **Potential signal:** Representation, quantization, persistence/structure; exact claim requires note-level reading.

## IP classification framework

The repository also contains versioned IP-classification framework documents. These are **project-governance/provenance infrastructure**, not separate research projects, but they demonstrate explicit thinking about open research, employer boundaries, precedence, licensing, and safe collaboration.

---

# G. Repository families that should not be double-counted

## RMMFB / RMFB family

Treat these as one large research program with different roles:

- `manuscript-waste-reuse-finder` — early public prototype + 2024 paper/presentation
- `binding-unwinding` — dataset extraction/preparation
- `congenial-chainsaw-rmfb-html` — historical classification/documentation experiment
- `rib-wrist-in-bin-din` — later vision/model/paper planning
- `fhtw-paper-code-prep` — experiment infrastructure
- `fhtw-manuscript-models` — model-family support
- `rmfb-tech-draft` — technical writing space
- `rmfb-fragm-journal-draft` — Fragmentology-facing writing space

For a résumé, this should usually become **one flagship project with selected subcomponents**, not eight unrelated bullets.

## RWKV / LoRA family

- `rwkv-lora`
- `RWKV5-LM-LoRA`
- `info-rwkv-lora-learning-ref`

Treat as one experimental/learning lineage unless repository archaeology establishes separate publishable results.

## Higgs / physics visualization family

- `higgs_boson_visualized`
- `higgs_for_help`

Likely one broader physics-communication lineage until deeper inspection establishes otherwise.

## Job-analysis / portfolio-support family

- `ancestry-freq`
- `job-app-word-freq`
- `portfolio-amz-agi`
- `portfolio-resume`

Useful tools/artifacts, but not four independent scientific projects.

---

# H. Preliminary career-signal map

These are **not rankings of personal importance**. They are indications of what each project can most readily prove to a technical hiring manager.

## Strongest applied-science / research signals

1. **RMMFB/RMFB family** — long-horizon ownership, unusual dataset, CV, explainability, high-resolution document imagery, provenance, publication trajectory.
2. **NTEC** — falsifiable research question, sampling theory, preregistration/open science.
3. **Latent Forge** — recommender systems, matrix factorization, disciplined model iteration.
4. **Bilingual Boundary Lab** — controlled NLP baselines, multilingual data, visualization.
5. **Pocket Cocktail Party** — signal processing, ICA, mathematical model construction, experimental design.
6. **JabberVec-l2v** — representation learning and low-rank/embedding interpretation.

## Strongest ML-engineering / reproducibility signals

1. `fhtw-paper-code-prep`
2. `binding-unwinding`
3. `multimodal-jupy-logger`
4. `text-cleanroom`
5. `no-code-jupyter-nb`
6. RWKV/LoRA family, once reconstructed carefully

## Strongest data-centric signals

1. RMMFB dataset lineage
2. `binding-unwinding`
3. `text-cleanroom`
4. NTEC experimental-image preparation
5. multilingual OCR/HTR work such as `marco-polo-malayalam` after deeper inspection

## Strongest “memorable small project” signals

1. `mendeleev-spelling-bee`
2. `jabbervec-l2v`
3. `bilingual-boundary-lab`
4. `pocket-cocktail-party`

These are useful because a hiring manager can understand the question quickly and then ask deeper technical questions.

---

# I. Repositories present but not yet deeply classified

For completeness, the following owned repositories are retained in the inventory even though this pass did not justify a detailed technical summary:

- [`double-p-double-n`](https://github.com/bballdave025/double-p-double-n)
- [`english-gorf`](https://github.com/bballdave025/english-gorf)
- [`envelope-zip-reading`](https://github.com/bballdave025/envelope-zip-reading)
- [`solid-rotary-phone`](https://github.com/bballdave025/solid-rotary-phone)
- [`start-pirate`](https://github.com/bballdave025/start-pirate)
- [`start-pirate-now`](https://github.com/bballdave025/start-pirate-now)
- [`upgraded-waffle`](https://github.com/bballdave025/upgraded-waffle)
- [`vayzday`](https://github.com/bballdave025/vayzday)

The correct next action for any of these is **targeted README/root-file inspection**, not guessing from the name.

---

# J. What this inventory is for

This is deliberately the **long-form inventory**.

It is not yet the final résumé portfolio list.

A later short-form version can compress each project to something like:

```text
Project | status | 1-line problem | strongest evidence | skills | job-fit tags
```

The point of keeping this long form first is to avoid losing useful differentiators merely because they do not fit into a one-page résumé today. It provides the source from which we can later make:

- an Applied Scientist shortlist,
- an ML Engineer shortlist,
- a scientific-computing/HPC shortlist,
- a data-centric ML shortlist,
- a public portfolio page,
- résumé project bullets,
- and interview “tell me about a project” stories.
