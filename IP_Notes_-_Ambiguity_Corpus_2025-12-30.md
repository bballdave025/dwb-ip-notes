# IP_Notes_Ambiguity_Corpus_Initial_YYYY-MM-DD.md

## 0. Status & Intent
**Status:** Quick & Reckless (Q&R) capture  
**Purpose:** Establish independent conception, scope, and direction of the Ambiguity Corpus project prior to further development, publication, or potential collaboration.

This document is a *capture artifact*, not a finalized research proposal.

---

## 1. Project Name (Working)
**Ambiguity Corpus**  
(subtitle: Regex-Seeded Discovery of Ambiguous Language in Natural Contexts)

---

## 2. Core Intuition (One Paragraph)
The Ambiguity Corpus project aims to identify, collect, and characterize naturally occurring ambiguous language by leveraging *clarification behavior* rather than attempting to pre-define all ambiguity types. The key insight is that humans reliably signal ambiguity using recurring linguistic patterns (e.g., “do you mean X or Y?”, “as in…”, “pun intended”), which can be detected at scale using regex and lightweight NLP methods. These signals allow discovery of diverse ambiguity phenomena without constraining the corpus to a narrow taxonomy upfront.

---

## 3. Primary Ambiguity Categories (Provisional)
Initial working categories include:

- **Linguistic ambiguity** (syntactic, semantic)
- **Pragmatic ambiguity** (context, implicature)
- **Instructional ambiguity** (underspecified tasks)
- **Model vs. human uncertainty**
- **Annotator disagreement** (symptomatic / discovery-oriented)

These categories are intentionally provisional and may evolve.

---

## 4. Key Methodological Insight
Rather than detecting ambiguity directly, the project detects **responses to ambiguity**.

Examples:
- Clarification questions
- Explicit disambiguation (“as in…, not as in…”)
- Metalinguistic markers (“pun intended”)

Regex patterns can capture both:
1. the ambiguous utterance, and  
2. the clarifying reformulation that follows.

This enables paired data: *(ambiguous form → clarified form)*.

---

## 5. Data Sources (Planned / Potential)
- Existing large text corpora
- Audio transcripts
- Conversational datasets
- Human–AI interaction logs (where permitted)

Initial focus is on **open or publicly available sources**.

---

## 6. Features & Signals of Interest
Potential features explored or discussed:
- Regex trigger type
- POS structure of ambiguous spans
- Number of plausible interpretations (≠ limited to binary ambiguity)
- Information-theoretic measures (entropy, perplexity)
- Degree and type of annotator disagreement

---

## 7. Transformation / Rewrite Aspect (Exploratory)
Beyond detection, the corpus may support:
- Explicit **disambiguating rewrites**
- Structured mapping from ambiguity → clarification
- Pattern-based or model-based rewrite suggestions

This may involve NLP approaches beyond classical regex (future work).

---

## 8. Relationship to Employment / Use
This project originated through independent thinking and exploratory conversations about interview preparation and language ambiguity. It is intended primarily as **open research**, though its ideas may later inform applied systems if appropriately scoped and authorized.

---

## 9. Open Questions (Intentionally Unresolved)
- Optimal ambiguity metrics
- Taxonomy derivation (manual vs. learned)
- Best balance of regex vs. learned models
- Scope of automated rewriting

---

## 10. Notes
This document captures direction, not decisions.  
Details, citations, and formal structure will be added only if and when needed.
