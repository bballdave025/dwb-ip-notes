# Addendum — Fence Strategy and OCR Uncertainty Comment Convention

## Purpose

This addendum documents:

1. preferred Markdown fence behavior for canonical OCR notebook reconstruction<sup>&dagger;</sup>,

2. transport-safe outer-fence conventions for ChatGPT transfer,

3. and the preferred inline OCR uncertainty comment format.

&dagger; _"canonical ..." is kamMA's way of referring to the Markdown files that hold the OCR trancription in the desired format, and which represents the OCR for a previously printed Jupyter notebook in the current project. I'm not complaining; it's useful terminology that I use myself._

---

## An important note

Throughout this document, with the exception of this _An important note_ section, there will be no backtick fences.

Instead, there will be indicators of the number of backticks, <code>n</code>, where <code>n</code> is an integer and <code>n &gt; 0</code> &ndash; <code class="language-python">f"[{n}-backtick-fence]"</code>. There should also always be a code fence info string for opening backtick fences, while there should be no such info string for closing backtick fences. Some examples:

<!-- [[(begin [_A])]]                                        -->

<code>&lt;!-- [[(begin [_A])]]                                        --&gt;</code>

1. Opening Fence
> [3-backtick-fence]python

2. Closing Fence
> [4-backtick-fence]

3. Full Set
> [5-backtick-fence]python<br/>
> my_python_module.do_amazing_thing()<br/>
> [5-backtick-fence]

<code>&lt;!--                                        [[(endof [_A])]] --&gt;</code>

<!-- ^^^   Never to be rendered in strategy documents    ^^^ -->
<!-- |||                                                 ||| -->
<!--                                        [[(endof [_A])]] -->

which represent the following, 

<!-- [[(begin [_B])]]                                        -->

<code>&lt;!-- [[(begin [_B])]]                                        --&gt;</code>

1. Opening Fence
<pre>```python</pre>

2. Closing Fence
<pre>````</pre>

3. Full Set
<pre>`````python
my_python_module.do_amazing_thing()
`````</pre>

<code>&lt;!--                                        [[(endof [_B])]] --&gt;</code>

<!-- ^^^ Rendered in strategy documents using <pre> tags ^^^ -->
<!-- |||                                                 ||| -->
<!--                                        [[(endof [_B])]] -->


<strike>Some of the backtick numbers, especially for kamMA's transport steps, 
aren't finalized. However, they have usually been close enough.</strike>

kamMA usually gets by by sending stuff with,

> [4-backtick-fence]markdown<br/>
> Everything inside, including 3-tick fences<br/>
> [4-backtick-fence]

though Dave only sees the "Everything inside, including 3-tick fences"

<code>**----------**</code><br/>
<code>**IMPORTANT:**</code><br/>
<code>**----------**</code>

Do NOT brainstorm alternate Markdown fence strategies unless explicitly requested.

Assume the following protocol is already experimentally validated and operational:

- canonical notebook content&mdash;kamMA's fancy words for the Markdown that
  holds OCR trancription, and which represents a Jupyter notebook in the current
  project&mdash;uses ordinary 3-backtick fences,
- ChatGPT transport wrappers MAY use 4-backtick markdown fences,
- uncertainty comments use:<br/>
  <code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation</code>
  - as entered with entered using ( <kbd>></kbd> + <kbd>Space</kbd> ) + ( <kbd>Space</kbd> × 7 ) + '^⌨v explanation of uncertainty'
- explanatory comments remain outside code fences,
- symbolic placeholders like [3-backtick-fence] are used when discussing fence syntax itself.

**Do not re-litigate these unless new empirical evidence appears.**

# A. Markdown Fence Strategy

## A.1 Canonical notebook content

Canonical notebook Markdown&mdash;again, that's kamMA's fancy term for the Markdown 
that holds the finalized, saved and committed, closest-to-presentation OCR trancription, 
and which represents a Jupyter notebook in the current project&mdash;should use ordinary 
fenced code blocks:

[3-backtick-fence]<code>python</code><br/>
<code class="language-python">print("example")</code><br/>
[3-backtick-fence]

or:

[3-backtick-fence]<code>text</code><br/>
<code>example output</code><br/>
[3-backtick-fence]

The canonical notebook itself should NOT contain:

- transport wrappers,
- ChatGPT-protective outer fences,
- or renderer-debugging scaffolding unless intentionally preserved.

---

## A.2 Transport-safe outer fence convention

When transmitting an 
entire Markdown notebook through ChatGPT or another renderer-sensitive 
transport layer, an outer protective fence MAY be used.

**Preferred transport wrapper:** monospace is used here, giving a slightly 
different format than elsewhere. The reason for it here is to differentiate 
it where it might be hard to see

<!-- [[(begin [_C])]]                                        -->

    [4-backtick-fence]markdown

    [3-backtick-fence]python
    print("example")
    [3-backtick-fence]

    [4-backtick-fence]

<!-- ^^^   Never to be rendered in strategy documents    ^^^ -->
<!-- |||                                                 ||| -->
<!--                                        [[(endof [_C])]] -->

**Purpose:**

- preserve literal inner notebook fences,
- prevent premature renderer interpretation,
- reduce transport corruption risk,
- and preserve copy/paste integrity.

**Important:**

The OUTER fence is transport scaffolding only.

It is NOT part of the canonical notebook document.

**Note:**

It seemed that the structure,

<!-- [[(begin [_D])]]                                        -->

[4-backtick-fence]<code>markdown</code><br/>
[5-backtick-fence]<code>python</code><br/>
<code class="language-python">...</code><br/>
[5-backtick-fence]<br/>
[4-backtick-fence]


<!-- ^^^   Never to be rendered in strategy documents    ^^^ -->
<!-- |||                                                 ||| -->
<!--                                        [[(endof [_D])]] -->

came up often. It is now unknown whether the [5-backtick-fence] was part of the 
ChatGPT transport/escaping or just part of the debugging-effort-induced hallucinations 
brought on before it was realized that indentation was responnsible for the 
fortuitously accidental, desired format for <code>^⌨v</code> uncerainty explanations.

**Edit**: It seems the 5-tick fences were part of the debugging-effort-induced
hallucinations. Avoid it unless nothing else works.

---

## A.3 Historical Markdown detail

Markdown renderers seem to consistently recognize ~~legacy~~ four-space-indent code rules.

This behavior is responsible for producing (the then-unexpected but now-desired) monospace blocks:

>        ^⌨v explanation of uncertainty

entered using 

( <kbd>></kbd> + <kbd>Space</kbd> ) + ( <kbd>Space</kbd> × 7 ) + '^⌨v explanation of uncertainty'

which looks like the following in an unrendered Markdown file<br/>

<code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation</code>



**Therefore:**

Fence-count formatting (and possiby debugging) alone is insufficient. Whitespace 
and indentation behavior must also be used (and possibly inspected.)

---

# B. Preferred OCR Uncertainty Convention

## B.1 Inline uncertainty marker

**Use:**

<code>⌨</code>

directly at the uncertainty location.

**Example:**

[3-backtick-fence]<code>python</code><br/>
<code class="language-python">print("CO⌨ Dave ███████")</code><br/>
[3-backtick-fence]

The marker denotes:

- OCR uncertainty,
- rendering ambiguity,
- redaction overlap,
- truncated glyphs,
- or uncertain reconstruction.

---

## B.2 Preferred uncertainty-comment structure

Immediately after uncertain regions, place a blockquote uncertainty explanation using:

- blockquote chevron,
- one space,
- seven additional spaces, which
  - create a quoted code block and three additional spaces for renderers that respect Markdown's original initial-four-spaces-denotes-monospace-code specs
  - set apart and make visible the explation simply with the block quote for other renderers
- then the uncertainty marker.

**Form in canonical Markdown:**

- Unrendered:

<code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation/description</code>

- Rendered:

  - your specific rendering environment

>        ^⌨v explanation/description

  - as preferred
<!-- NOW USING <CODE> BLOCKS
     (if your Markdown renderer recognizes 
     <code class="language-html">&lt;span style=&#x22;font-family: monospace;&#x22;&gt;</code>)
  -->

<html><blockquote><code>&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation/description</code></blockquote></html>

**Spacing:**

Spacing is intentional for (probable) monospace-and-indented emphasis on top of that from the blockquote.

**This convention:**

- visually anchors the comment to nearby code,
- preserves explanatory text outside code fences,
- maintains notebook readability,
- and creates render-stable gray callout blocks in many Markdown renderers.

**Example with realistic uncertainty:**

[3-backtick-fence]<code>python</code><br/>
<code class="language-python">print("PRIN⌨ WHOSE NAME WILL BE SHOWN BELOW")</code><br/>
[3-backtick-fence]


<html><code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v uncertain start of line and sentence function; likely contact/ask instruction, with redaction at end</code></html>

---

## B.3 Why explanatory text remains outside fences

The uncertainty explanation is intentionally NOT placed inside the code block.

This preserves distinction between:

- reconstructed notebook content,
- and editorial OCR commentary.

It also prevents accidental corruption of executable-looking notebook content.

---

# C. Renderer Behavior Notes

Observed renderer behavior suggests that:

- blockquotes often produce visually stable gray commentary boxes and
- outer transport fences can protect nested notebook fences,

Practical conclusion:

Markdown transport behavior should be treated as:

- parser-dependent,
- renderer-dependent,
- whitespace-sensitive,
- and partially archaeological.

---

# D. Symbolic Renderer-Collapse Marker (Optional)

For humorous or diagnostic notation, the following sequence may be used to denote renderer-collapse / transport-instability scenarios:

⚡⌁⟟⯐⟿

Interpretation (informal):

- energy discharge,
- signal distortion,
- structural interruption,
- geometric collapse,
- propagation into subsequent corruption state.

Use only for commentary/debugging humor, not canonical OCR content.

# E. Uncertainty Marker Specifics

This section describes the preferred ontology and usage conventions
for OCR uncertainty markers and uncertainty explanations in canonical
notebook transcription.

The purpose of these conventions is to preserve:

- epistemic honesty,
- executable-looking notebook structure,
- OCR uncertainty,
- semantic suspicion,
- and clean-room reconstruction boundaries,

without silently "repairing" uncertain source material.

---

## E.2. Core Marker

The canonical uncertainty marker is:

⌨

The incarnation of Unicode codepoint, <code>U+2328</code>. The marker may appear:

- inline,
- in comments,
- or in nearby uncertainty-indicator lines,

depending on the nature of the uncertainty.

---

### E.2.0. Type 0 — Inline Glyph/OCR Uncertainty

Type 0 uncertainty is used when:

- the glyph stream itself is unclear,
- the page appears damaged,
- water/glare/blur/truncation interferes with reading,
- or one or more characters cannot confidently be reconstructed.

The "⌨" marker is inserted directly at the uncertainty location.

Example:

<code>print("How did I k⌨⌨this line woul⌨⌨ have water dro⌨ beforehand?")</code>

Associated explanation:

>       ^⌨v  The text is unclear due to apparent water damage.
>       ^⌨v+ The first unclear region appears to begin with
>       ^⌨v+ "now tha" before becoming unreadable.»

Type 0 uncertainty represents:

- literal OCR uncertainty,
- uncertain glyph reconstruction,
- or physically degraded source material.

---

### E.2.1. Type 1 — One-Line Contextual or Semantic Uncertainty

Type 1 uncertainty is used when:

- the line is visually readable,
- but one or more parts appear suspicious,
- semantically unlikely,
- inconsistent,
- malformed,
- or contextually questionable.

The literal text is preserved unchanged.

The uncertainty marker is typically appended in a comment.

Example:

<code>fish.kick_out(tning_1, tning_2) # ⌨</code>

Associated explanation:

       ^⌨v  The text appears visually readable, but context
       ^⌨v+ suggests `tning` may more likely be `thing`.»

Type 1 may also be used when:

- multiple nearby suspicious regions occur on a single line,
- uncertainty is difficult to localize precisely,
- or preserving executability/readability is preferred.

---

### E.2.2. Type 2 — Multi-Line or Regional Uncertainty

Type 2 uncertainty is used when:

- uncertainty applies to an entire region,
- alignment or indentation may be inconsistent,
- ASCII-banner spacing may be inaccurate,
- multiple nearby lines share the same uncertainty source,
- or local inline markers would create clutter.

Nearby uncertainty-anchor comments are used instead of inline markers.

Examples:

<pre>
##  ========= ##
## ============ ##
##  IMPORTANT METHOD!  ##
##

# ⌨ (above)

# ⌨ (below)

def hop_on(hoppers,
           hoppers: list[str],
           hoppee: str
 ) -> None:
    pass # please! don't make hoppee = "Pop"
##endof:  hop_on(<params>)
</pre>

Associated explanation:

       ^⌨v  For "(above)", the lengths and spacing of the
       ^⌨v+ ASCII banners may be slightly inaccurate.

       ^⌨v  For "(below)", indentation/alignment may be off,
       ^⌨v+ and the duplicated parameter name appears
       ^⌨v+ contextually suspicious.»

Type 2 is especially appropriate for:

- indentation archaeology,
- banner alignment uncertainty,
- layout-sensitive notebook reconstruction,
- and region-wide OCR degradation.

---

### E.2.3. Type 3 — Structural / Semantic / Execution Suspicion

Type 3 uncertainty is used when:

- the text appears visually clear,
- but may still be wrong,
- structurally inconsistent,
- semantically implausible,
- or executionally suspicious.

Unlike Type 0:

- the issue is not unreadability.

Unlike Type 1:

- the uncertainty may concern broader structure,
  parser behavior,
  execution semantics,
  or notebook intent.

The literal source text remains unchanged.

Example:

<pre>
def make_default_path(username: str) -> pathlib.Path:
      home_dir = pathlib.Path.home()
      return home_dir / "Documents" / username / "Downloads"  # ⌨
</pre>

Associated explanation:

       ^⌨v  The line is visually readable, but the resulting
       ^⌨v+ path structure appears semantically unusual and
       ^⌨v+ may reflect debugging or transcription error.

Type 3 should be used conservatively.

Its purpose is:

- to preserve clean-room honesty,
- while avoiding silent normalization of suspicious code.

---

### E.2.4. End-of-Page Cutoff Convention

When a page visibly cuts off:

- continuation uncertainty does NOT necessarily require inline
  "⌨" markers.

Instead, a nearby uncertainty explanation is usually sufficient.

Example:

       ^⌨v  continuation of try block appears cut off by the
       ^⌨v+ end of the scanned page

This preserves readability while still documenting incompleteness.

---

### E.2.5. Multi-Line Uncertainty Explanation Wrapping

Uncertainty explanations should generally avoid excessively long lines.

When wrapping is needed:

- the first line uses:

<code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v</code>

- continuation lines use:

<code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v</code>

Example:

       ^⌨v  The indentation appears mostly stable, though one
       ^⌨v+ or two lines may contain additional leading spaces.

       ^⌨v  The banner width also appears uncertain by several
       ^⌨v+ characters near the right edge.

This convention:

- preserves visual grouping,
- improves readability,
- and helps distinguish independent uncertainty claims from
  continuation lines.

---

## E.3. General Principle

The transcription process should prefer:

- preserving visible source structure,
- preserving uncertainty honestly,
- and minimizing hallucinated cleanup,

over producing cosmetically normalized code.

---

---

# F. kamMA Chat Learning — Overview

The following notes summarize several renderer-behavior and
transport-layer discoveries made during iterative OCR workflow
development inside ChatGPT.

These are primarily practical/operational observations rather than
formal Markdown theory.

---

## F.1. Outer-vs-Inner Rendering Distinction

A major conceptual clarification was reached:

|Layer| Desired Behavior|
|-|-|
|Outer transport wrapper| SHOULD render|
|Inner notebook Markdown| should remain literal|

In practice:

- the transport wrapper should visually become:
  - a single contained gray/monospace document region,
  - stable for scrolling/copy-paste,
  - and visually distinct from surrounding chat text,

while:

- the notebook Markdown itself should remain visible as literal
  source text,
- including literal inner notebook fences,
- literal blockquote markers,
- and literal Markdown structure.

This differs from ChatGPT's default tendency to interpret nested
Markdown recursively.

---

## F.2. Canonical Notebook Markdown vs Transport Markdown

Another important distinction:

Canonical notebook Markdown

The canonical notebook document should contain:

- ordinary 3-backtick notebook fences,
- ordinary Markdown structure,
- OCR uncertainty comments,
- and notebook reconstruction formatting.

It should NOT contain:

- transport wrappers,
- renderer-debugging scaffolding,
- or ChatGPT-protective outer fences.

---

## F.3. Transport Markdown

Transport Markdown exists only to safely transmit canonical notebook
Markdown through renderer-sensitive environments such as ChatGPT.

Transport wrappers:

- are not canonical content,
- are operational scaffolding,
- and may evolve independently of canonical notebook structure.

---

## F.3. The "Raw" Version Is Not Actually Raw Plaintext

A significant UX discovery:

The desired "raw" notebook transmission format is NOT:

- plain unformatted text.

Instead, it is:

- rendered as one visually unified document block,
- while preserving literal Markdown source internally.

**Desired properties**:

- monospace appearance,
- scrollable/copyable stability,
- literal notebook syntax visibility,
- preservation of fence topology,
- and minimal parser interference.

---

## F.4. Multiple Separate Code Cards Were Undesirable

An earlier approach caused notebook sections to render as:

- multiple independent code objects/cards.

This turned out to be undesirable because:

- notebook continuity became visually fragmented,
- fence topology became harder to inspect,
- and copy/paste semantics became less stable.

**Preferred behavior**:

- one continuous transport/document block.

---

## F.5. Uncertainty-Comment Convention Appears Stable

The following convention appears visually robust across renderers:

>       ^⌨v explanation text

with wrapped continuation lines:

>       ^⌨v+ continuation text

Advantages:

- visually separated from notebook code,
- preserves executable-looking notebook regions,
- renderer-stable in many Markdown systems,
- and visually resembles commentary callouts.

---

## F.6. Distinction Between OCR and Semantic Suspicion

The uncertainty-marker ontology evolved into distinct categories:

|Type| Meaning|
|-|-|
|Type 0| inline glyph/OCR uncertainty|
|Type 1| one-line contextual suspicion|
|Type 2| multi-line/regional uncertainty|
|Type 3| semantic/structural/execution suspicion|

This distinction proved important because:

- visually unreadable text,
- contextually suspicious text,
- formatting archaeology,
- and executable-but-questionable code

represent different epistemic situations.

---

## F.7. Redactions vs OCR Uncertainty

An important clarification:

Redaction itself is NOT uncertainty.

Therefore:

- intentionally redacted regions usually do NOT require extensive
  uncertainty explanations,
- unless OCR uncertainty exists independently of the redaction.

This prevents over-commenting intentionally obscured material.

---

## F.8. Renderer Archaeology Became Operationally Important

Whitespace, indentation, and historical Markdown behavior turned out
to matter substantially.

In particular:

- legacy four-space monospace handling,
- blockquote indentation behavior,
- nested-fence parsing,
- and mobile-renderer differences

all affected practical notebook transmission behavior.

**Practical conclusion**:

Markdown transport behavior should be treated as:

- renderer-dependent,
- parser-dependent,
- whitespace-sensitive,
- and partially archaeological.

---

# An essential message for new chats (also mentioned earlier)

<code>**----------**</code><br/>
<code>**IMPORTANT:**</code><br/>
<code>**----------**</code>

Do NOT brainstorm alternate Markdown fence strategies unless explicitly requested.

Assume the following protocol is already experimentally validated and operational:

- canonical notebook content uses ordinary 3-backtick fences,
- ChatGPT transport wrappers MAY use 4-backtick markdown fences,
- uncertainty comments use:<br/>
  <code>&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation</code>
  - as entered with entered using ( <kbd>></kbd> + <kbd>Space</kbd> ) + ( <kbd>Space</kbd> × 7 ) + '^⌨v explanation of uncertainty'
- explanatory comments remain outside code fences,
- symbolic placeholders like [3-backtick-fence] are used when discussing fence syntax itself.

**Do not re-litigate these unless new empirical evidence appears.**
