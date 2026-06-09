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
> [5-backtick-fence]python
> my_python_module.do_amazing_thing()
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


Some of the backtick numbers, especially for kamMA's transport steps, aren't finalized. However, they have usually been close enough.

**IMPORTANT:**

Do NOT brainstorm alternate Markdown fence strategies unless explicitly requested.

Assume the following protocol is already experimentally validated and operational:

- canonical notebook content&mdash;kamMA's fancy words for the Markdown that holds OCR trancription, and which represents a Jupyter notebook in the current project&mdash;uses ordinary 3-backtick fences,
- ChatGPT transport wrappers MAY use 4-backtick markdown fences,
- uncertainty comments use:

>        ^⌨v comment describing uncertainty

  - explanatory comments remain outside code fences,
  - symbolic placeholders like [3-backtick-fence] are used when discussing fence syntax itself.

  Do not re-litigate these unless new empirical evidence appears.

# A. Markdown Fence Strategy

## A.1 Canonical notebook content

Canonical notebook Markdown&mdash;again, that's kamMA's fancy term for the Markdown that holds the finalized, saved and committed, closest-to-presentation OCR trancription, and which represents a Jupyter notebook in the current project&mdash;should use ordinary fenced code blocks:

[3-backtick-fence]<code>python</code>
<code class="language-python">print("example")</code>
[3-backtick-fence]

or:

[3-backtick-fence]<code>text</code>
<code>example output</code>
[3-backtick-fence]

The canonical notebook itself should NOT contain:

- transport wrappers,
- ChatGPT-protective outer fences,
- or renderer-debugging scaffolding unless intentionally preserved.

---

## A.2 Transport-safe outer fence convention

When transmitting an entire Markdown notebook through ChatGPT or another renderer-sensitive transport layer, an outer protective fence MAY be used.

**Preferred transport wrapper:** monospace is used here, giving a slightly different format than elsewhere. The reason for it here is to differentiate it where it might be hard to see

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

It seemed that the same structure,

<!-- [[(begin [_D])]]                                        -->

[4-backtick-fence]<code>markdown</code>
[5-backtick-fence]<code>python</code>
<code class="language-python">...</code>
[5-backtick-fence]
[4-backtick-fence]


<!-- ^^^   Never to be rendered in strategy documents    ^^^ -->
<!-- |||                                                 ||| -->
<!--                                        [[(endof [_D])]] -->

came up often. It is now unknown whether the [5-backtick-fence] was part of the ChatGPT transport/escaping or just part of the debigging-effort-induced hallucinations brought on before it was realized that indentation was responnsible for the fortuitously accidental, desired format for <code>^⌨v</code> uncerainty explanations

---

## A.3 Historical Markdown detail

Markdown renderers seem to consistently recognize ~~legacy~~ four-space-indent code rules.

This behavior is responsible for producing (the then-unexpected but now-desired) monospace blocks:

>        ^⌨v explanation of uncertainty

entered using 

( <kbd>></kbd> + <kbd>Space</kbd> ) + ( <kbd>Space</kbd> × 7 ) + '^⌨v explanation of uncertainty'

which looks like the following in an unrendered Markdown file

<html><span style="font-family: monospace">&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation</span></html>

**Therefore:**

Fence-count formatting (and possiby debugging) alone is insufficient. Whitespace and indentation behavior must also be used (and possibly inspected.)

---

# B. Preferred OCR Uncertainty Convention

## B.1 Inline uncertainty marker

**Use:**

<code>⌨</code>

directly at the uncertainty location.

**Example:**

[3-backtick-fence]<code>python</code>
<code class="language-python">print("CO⌨ Dave ███████")</code>
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

<html><span style="font-family: monospace">&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v explanation/description</span></html>

- Rendered:

  - your specific rendering environment

>        ^⌨v explanation/description

  - as preferred

<html><blockquote><span style="font-family: monospace">&nbsp;&nbsp;&nbsp;^⌨v explanation/description</span></blockquote></html>

**Spacing:**

Spacing is intentional for (probable) monospace-and-indented emphasis on top of that from the blockquote.

**This convention:**

- visually anchors the comment to nearby code,
- preserves explanatory text outside code fences,
- maintains notebook readability,
- and creates render-stable gray callout blocks in many Markdown renderers.

**Example:**

- Unrendered 

[3-backtick-fence]<code>python</code>
<code class="language-python">print("PRIN⌨ WHOSE NAME WILL BE SHOWN BELOW")</code>
[3-backtick-fence]


<html><span style="font-family: monospace">&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;^⌨v uncertain start of line and sentence function; likely contact/ask instruction, with redaction at end</span></html>

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
