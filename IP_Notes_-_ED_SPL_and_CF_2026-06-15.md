# IP Notes — Entity Density, Predicate Load, and Compression Feasibility

**Project:** Entity Density and Compression Feasibility Analysis  
**Working title:** Entity Density Compression Diagnostics  
**Author:** David Black / DWB  
**Status:** Early idea / portfolio candidate  
**Date:** 2026-06-14  
**Primary classification:** Personal research / personal tooling  
**Secondary classification:** Portfolio-oriented analysis tooling  

---

## 1. Purpose

This project explores whether short-form writing constraints can be
diagnosed using simple linguistic and statistical features such as:

- entity-word density
- number of named entities
- subject/predicate density
- predicate load
- noun-phrase density
- clause count
- information density
- genre-specific compression limits

The motivating observation is that some writing tasks may be infeasible
under a strict word limit if the required facts, entities, subjects,
predicates, and rhetorical constraints already consume too much of the
available word budget.

A practical example is a marketing-summary task constrained to 100 words.
A preliminary back-of-the-envelope estimate suggested that the text might
need roughly 40% entity words to preserve all required entities. This is
likely high relative to ordinary prose expectations and may make natural
marketing prose difficult or impossible under that word limit.

---

## 2. Core hypothesis

Some summarization or rewriting tasks fail not because the model lacks
fluency, but because the task constraints are structurally
overdetermined.

A target word count can become infeasible when the required content already
uses too much of the available word budget.

Possible measurable contributors:

```text
required entities
+ required predicates
+ required relations
+ required rhetorical framing
+ required marketing language
+ grammatical glue
+ naturalness constraints
> available word budget
```

When this happens, a model may have to choose among:

- dropping required content
- compressing content into unnatural prose
- merging entities ambiguously
- removing necessary predicates
- producing list-like text instead of fluent prose
- violating the word limit

---

## 3. Initial motivating workflow

The initial manual analysis involved:

1. Taking a marketing email.
2. Asking whether it could be shortened to 100 words.
3. Extracting entities manually.
4. Asking an AI assistant to extract entities independently.
5. Comparing the human and model entity lists.
6. Estimating how much of the 100-word budget would be consumed by
   entities.
7. Asking for the shortest natural marketing-prose summary after removing
   the strict word limit.
8. Observing that the shortest natural version was still about 1.5 times
   the target word count.

This suggests that the original target may have been infeasible as written.

---

## 4. Portfolio version

A non-proprietary portfolio version should use public or user-supplied text,
not workplace data.

Possible input sources:

- marketing web pages
- public marketing emails
- technical documentation
- academic abstracts
- journal articles from different fields
- news articles
- blog posts
- public-domain books
- historical texts
- YouTube transcripts
- README files
- API documentation
- grant abstracts
- public legal or policy summaries

The tool could accept:

```text
a list of URLs
or
a directory of text files
or
a CSV containing document IDs and text
```

and produce approximate measurements, comparisons, and visualizations.

---

## 5. Candidate measurements

### 5.1 Basic document statistics

- total words
- total sentences
- total tokens
- average sentence length
- median sentence length
- type-token ratio
- punctuation density
- paragraph count

### 5.2 Entity statistics

- named-entity count
- entity-token count
- entity-word ratio
- entity types
- unique-entity count
- repeated-entity count
- entity density per sentence
- entities per 100 words

Possible entity types:

- person
- organization
- location
- product
- date or time
- money
- percentage
- event
- work of art
- law or policy
- technical term, if custom extraction is added

### 5.3 Subject/predicate approximations

Approximate subject/predicate extraction could include:

- dependency-parse subjects
- main verbs
- subject-verb-object triples
- finite-verb count
- predicate count per sentence
- clauses per sentence
- verbs per 100 words
- subject mentions per 100 words

A first pass does not need perfect linguistic theory. It can use practical
approximations and report uncertainty.

### 5.4 Compression-feasibility features

For a target word count `W`, estimate:

```text
entity_word_ratio = entity_word_count / W

predicate_word_ratio = predicate_word_count / W

required_content_ratio = required_content_words / W
```

Potential exploratory warning thresholds:

```text
entity_word_ratio > 0.25

entity_word_ratio > 0.35

required_content_ratio > 0.50

sentence_count_needed > plausible_sentence_count
```

These thresholds should be empirical and exploratory, not presented as
settled theory.

---

## 6. Simple modeling ideas

### 6.1 Descriptive analysis

Start with descriptive statistics by genre:

```text
marketing prose
technical documentation
academic abstracts
news
blogs
public-domain fiction
public-domain nonfiction
video transcripts
```

For each genre, calculate:

- entity-word-ratio distribution
- predicate-density distribution
- average compression ratio
- sentence-length distribution
- natural-summary-length estimates

### 6.2 Visualization ideas

Possible plots:

- entity density by genre
- predicate density by genre
- word budget consumed by entities
- word budget consumed by subjects and predicates
- entity density versus shortest natural summary length
- histogram of entities per 100 words
- box plot of entity density across genres
- compression-feasibility heatmap
- required-content ratio versus achieved-summary ratio
- target length versus estimated minimum natural length

### 6.3 Simple feasibility classifier

A first model could classify tasks as:

```text
likely feasible
borderline
likely infeasible
```

based on features such as:

- source length
- target length
- required entity count
- entity-word ratio
- predicate density
- requested style
- genre
- number of required claims
- number of required relations
- desired sentence count
- required tone or rhetorical framing

This could begin as:

- a rule-based classifier
- logistic regression
- a small decision tree
- a calibrated linear model

The first version should remain interpretable. More elaborate models can
come later if the dataset justifies them.

### 6.4 Regression targets

Possible regression targets include:

- minimum natural summary length
- achieved compression ratio
- fraction of required entities retained
- fraction of required predicates retained
- human naturalness score
- rubric-compliance score
- difference between requested and achievable word counts

### 6.5 Theoretical but ML-grounded extension

A later model could estimate a task-specific lower bound:

```text
estimated minimum natural word count
```

using features derived from:

- entity structure
- relation structure
- syntax
- discourse requirements
- genre
- tone
- required claims
- expected redundancy
- acceptable ambiguity

This would not initially be a formal mathematical theorem. It would be an
empirical estimate informed by linguistic features and learned from data.

---

## 7. Open-source tooling candidates

Potential tools include:

- spaCy for tokenization, POS tagging, dependency parsing, and NER
- Stanza for linguistically oriented parsing
- NLTK for simple tokenization and classical NLP baselines
- scikit-learn for interpretable statistical models
- pandas for tabular analysis
- NumPy and SciPy for numerical work
- matplotlib for plots
- Beautiful Soup for basic HTML parsing
- trafilatura for extracting main article text from web pages
- readability-style extraction for isolating primary page content

A practical first implementation should avoid too much scraping complexity.

A sensible sequence is:

```text
local text files
-> CSV datasets
-> saved HTML or article text
-> URL ingestion
-> transcript acquisition
```

---

## 8. Candidate extraction pipeline

A first-pass document pipeline could be:

```text
raw input
-> document cleanup
-> sentence segmentation
-> tokenization
-> POS tagging
-> named-entity recognition
-> dependency parsing
-> feature aggregation
-> genre-level analysis
-> visualization
-> feasibility estimate
```

Potential per-document output columns:

```text
document_id
source_type
genre
word_count
sentence_count
entity_count
unique_entity_count
entity_word_count
entity_word_ratio
subject_count
predicate_count
finite_verb_count
clause_count
average_sentence_length
target_word_count
compression_ratio_requested
estimated_minimum_word_count
feasibility_label
```

---

## 9. Subject and predicate extraction ideas

Perfect subject/predicate extraction is not required for the first version.

A useful approximation could count dependency labels such as:

```text
nsubj
nsubjpass
csubj
csubjpass
```

Predicate candidates could begin with:

- ROOT verbs
- finite verbs
- verbal heads connected to subjects
- coordinated verbs
- subordinate-clause verbs

A practical subject-predicate record might contain:

```text
sentence_id
subject_text
subject_head
predicate_lemma
predicate_text
object_text
entity_links
dependency_confidence
```

Possible complications to document:

- implied subjects
- passive voice
- coordinated clauses
- nominal predicates
- copular constructions
- infinitival clauses
- appositives
- pronoun resolution
- cross-sentence references
- marketing fragments without full clauses

The first release should make its approximations visible rather than imply
perfect linguistic parsing.

---

## 10. Entity extraction ideas

A first entity layer could combine:

1. standard named-entity recognition
2. noun-phrase extraction
3. repeated capitalized phrase detection
4. domain-term extraction
5. optional user-supplied required-entity lists

This distinction matters because important semantic items are not always
recognized as conventional named entities.

For example, a rubric may require mention of:

- a product feature
- an abstract benefit
- a technical component
- a policy requirement
- a customer segment
- a quantitative claim

These may be semantically required without being labeled as named entities
by a general NER model.

Possible categories:

```text
named entities
required concepts
required claims
required numerical values
required relations
required qualifiers
```

---

## 11. Naturalness and grammatical-glue analysis

The words not directly assigned to entities or predicates still matter.

Possible categories of grammatical or rhetorical glue include:

- determiners
- prepositions
- conjunctions
- auxiliary verbs
- pronouns
- transitions
- discourse markers
- qualifiers
- articles
- punctuation-bearing connective phrases

A useful empirical quantity could be:

```text
glue_ratio
    = glue_word_count / total_word_count
```

or:

```text
semantic_payload_ratio
    = required_content_words / total_word_count
```

A text may become unnatural when the semantic-payload ratio becomes too
high for its genre.

This could help explain why a technically possible compressed list is not
equivalent to natural marketing prose.

---

## 12. Genre comparison

The project should compare multiple genres because acceptable information
density varies substantially.

Candidate genre groups:

- marketing emails
- landing pages
- technical documentation
- API documentation
- academic abstracts
- journal articles
- news reporting
- opinion writing
- informal blogs
- public-domain fiction
- public-domain nonfiction
- historical scientific writing
- video transcripts
- podcast transcripts

Potential questions:

- Which genres have the highest entity density?
- Which genres have the highest predicate density?
- Which genres tolerate compressed noun-heavy prose?
- Which genres require more rhetorical glue?
- How does natural compression differ by genre?
- Does marketing prose require more non-entity language than technical
  prose?
- At what density do texts begin to resemble lists rather than prose?

---

## 13. RLHF and rubric-analysis relevance

This project is relevant to RLHF and rubric design because some rubric
requirements may be impossible to satisfy simultaneously under a strict
word limit.

A rubric might ask for:

- all key entities
- all important claims
- natural marketing prose
- a specific tone
- a strict maximum word count
- no ambiguity
- no omissions
- particular persuasive language
- required subject matter
- preservation of all named relationships

If the required semantic content exceeds the available word budget, model
outputs may be penalized for failures caused by rubric infeasibility rather
than model weakness.

This suggests useful diagnostic categories such as:

```text
constraint infeasibility
rubric overdetermination
semantic-payload overload
compression infeasibility
```

Potential diagnostic question:

```text
Does the task require more entity, relation, predicate, and rhetorical
content than the target length can support in natural prose?
```

---

## 14. LLM-as-a-judge implications

An LLM judge may penalize different outputs for different compromises:

- one output exceeds the word limit
- another omits an entity
- another drops a predicate
- another sounds unnatural
- another merges two claims ambiguously

If no output can satisfy every requirement, preference data may become
internally inconsistent.

Possible consequences include:

- noisy reward signals
- contradictory preference labels
- wrong reward-model updates
- apparent model instability
- systematic preference for one arbitrary failure mode
- judge disagreement caused by infeasible rubrics

A feasibility pre-check could therefore be useful before human or automated
evaluation.

---

## 15. Relationship to RLHF and GRPO

The project may eventually connect to:

- RLHF task design
- reward-model training
- rubric validation
- LLM-as-a-judge reliability
- group-relative policy optimization
- preference-data quality
- failure-mode classification

The first portfolio version does not need to implement RLHF or GRPO.

Its contribution can be narrower:

```text
Measure whether the evaluation prompt itself appears feasible under its
length and content constraints.
```

That is already useful as a diagnostic layer.

---

## 16. Minimal GitHub portfolio version

A small portfolio project could use:

```text
entity_density/
  README.md
  requirements.txt
  src/
    entity_density/
      __init__.py
      ingest.py
      clean.py
      entities.py
      syntax.py
      features.py
      feasibility.py
      visualize.py
  examples/
    sample_texts/
    sample_url_list.txt
    demo_notebook.ipynb
  outputs/
    example_tables/
    example_charts/
```

First milestone:

- local text-file ingestion
- entity extraction with spaCy
- simple POS and dependency features
- pandas summary table
- three to five plots
- one feasibility-score prototype
- one notebook explaining the method
- explicit caveats about approximate extraction

---

## 17. Possible staged implementation

### Stage 1 — Local corpus analysis

- ingest local `.txt`, `.md`, or `.csv` content
- calculate basic document statistics
- run POS tagging
- run NER
- run dependency parsing
- export per-document features

### Stage 2 — Genre comparisons

- assemble a small public corpus
- label documents by genre
- compare feature distributions
- create visualizations
- document limitations

### Stage 3 — Compression experiments

- generate summaries at multiple target lengths
- measure retained entities
- measure retained predicates
- measure naturalness approximately
- compare requested and achieved compression

### Stage 4 — Feasibility prediction

- define empirical labels
- build simple interpretable models
- compare rule-based and learned baselines
- inspect feature importance
- identify failure cases

### Stage 5 — Rubric diagnostics

- represent required rubric items
- estimate minimum semantic payload
- flag likely overdetermined tasks
- produce a short diagnostic report

---

## 18. Evaluation ideas

Potential evaluation measures include:

- entity precision and recall
- required-entity retention
- predicate retention
- relation retention
- word-count compliance
- semantic similarity
- grammaticality
- naturalness
- genre conformity
- judge agreement
- feasibility-classification accuracy

Potential baselines:

- simple word-count ratio
- entity count alone
- entity-word ratio alone
- subject-plus-predicate count
- TF-IDF feature model
- logistic regression
- shallow decision tree
- small gradient-boosted model

The project should begin with interpretable baselines before more complex
models.

---

## 19. Non-goals for the first version

Do not begin with:

- perfect linguistic theory
- perfect subject/predicate extraction
- universal feasibility claims
- workplace data
- proprietary examples
- a large scraping system
- an opaque deep model
- LLM-generated labels as the only ground truth
- a proof that any exact word count is impossible

The first version should be a lean-to empirical diagnostic tool.

---

## 20. Possible research questions

- How much entity density is typical by genre?
- How much entity density can natural marketing prose tolerate?
- How does entity density relate to minimum natural summary length?
- Can rough entity and predicate counts predict whether a word limit is
  infeasible?
- Do rubric failures cluster around tasks with high required-content
  density?
- Are LLM judges sensitive to impossible compression constraints?
- Can simple pre-checks identify overdetermined summarization tasks?
- How much grammatical glue is required for natural prose by genre?
- Does entity retention decline sharply beyond a particular compression
  ratio?
- Do models preserve entities at the expense of relations or predicates?
- Can disagreement among judges be predicted by estimated task
  infeasibility?

---

## 21. Intellectual-property and provenance boundaries

The portfolio project should be developed from:

- independently written code
- public datasets
- public documents
- public-domain texts
- user-created synthetic examples
- general linguistic and statistical methods

It should intentionally exclude:

- workplace marketing content
- confidential rubrics
- internal task instructions
- proprietary model outputs
- internal evaluation data
- employer-specific systems or workflow details

The motivating professional experience may identify the usefulness of a
general diagnostic pattern, but the implementation, datasets, terminology,
and examples should remain independent and organization-agnostic.

---

## 22. Personal note

The motivating instinct was pre-formal but numerically plausible: a
100-word target can be unrealistic if preserving the required entities
already consumes too much of the word budget.

A later comparison found that the shortest natural marketing-prose version,
after removal of the strict word limit, was approximately 1.5 times the
original target length.

The project is valuable because it connects:

- practical RLHF task analysis
- linguistic feature extraction
- simple empirical modeling
- visualization
- rubric feasibility
- compression analysis
- portfolio-friendly NLP and data analysis

The first goal is not to prove a universal theory.

The first goal is to build a small, interpretable tool that helps detect
when a writing task is probably asking for too much semantic content in too
few words.

*End of document*
