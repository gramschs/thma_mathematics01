# Writing Style Guide: Engineering Mathematics Lecture Notes

This document captures the writing style and structural conventions for
lecture notes in mathematics for engineering students. It is intended as a
reference for any new chapter or section.

---

## Course Context

- Audience: undergraduate engineering students, first year.
- Method: inverted classroom. Students read the notes and watch embedded
  videos at home. In-class sessions are used for discussion and exercises.
- Prior knowledge: most material builds on school mathematics. The notes
  consolidate and deepen rather than introduce from scratch.
- Forward goal: all content prepares students explicitly for later topics,
  particularly differential and integral calculus.

---

## File Format

- MyST Markdown for Jupyter Book version 2.
- One section per file.
- Every file opens with a YAML front matter block:
  ```
  ---
  authors:
    - name:
  ---
  ```
- The section title is an H1 heading (`#`).
- Subsections use H2 headings (`##`).
- The learning goals block always appears immediately after the H1 title,
  before any body text.

---

## Language

- **American English** throughout.
- No dashes of any kind, neither `--` nor `---`. Rephrase sentences to avoid
  them. Use a comma or a full stop instead.
- Bold is used only at the moment a key term is introduced for the first time.
  Do not use bold for general emphasis in running text.
- Italics are used for rhetorical questions and for light emphasis where
  genuinely needed.

---

## Voice

- **Learning goals:** use "You" (second person). Each goal begins with an
  action verb: "You know", "You can", "You are familiar with".
- **All other text:** use "we" throughout. The student is a fellow
  investigator, not a passive recipient.
- Tone is warm and direct, closer to a spoken lecture than a textbook.
- Use rhetorical questions to guide attention and create narrative tension.
  Write them in italics: *How does the voltage change over time?*

---

## Learning Goals Block

```
```{admonition} Learning goals
:class: attention
* [ ] You know ...
* [ ] You can ...
```
```

- Appears immediately after the H1 title, before any body text.
- Each goal is concise and checkable: a student should be able to determine
  unambiguously whether they have achieved it.
- Key terms are in **bold**.

---

## Narrative Structure

Every section follows this arc without exception:

1. **Opening paragraph:** connects to the previous section and introduces a
   concrete physical scenario that motivates the new concept. Never open with
   a definition or a formula.
2. **Learning goals block.**
3. **Content subsections:** each develops one concept, moving from physical
   observation to informal description to formal definition box.
4. **Summary and outlook paragraph:** summarizes what was covered and ends
   with a forward-pointing sentence that hints at the next section without
   giving it away.

---

## Subsection Headings

- Phrase headings as questions or short statements that a student would
  naturally ask or say.
- Good examples: "What is a function?", "Does the track rise or fall?",
  "When is a function invertible?"
- Avoid abstract noun-phrase headings such as "Definition" or "Properties".

---

## Running Examples

- Every chapter should have one **central running example** that is
  introduced in the first section and extended or revisited in subsequent
  sections.
- The example must be physically concrete and relevant to the engineering
  discipline.
- When a new configuration of the example is introduced, always: describe
  it physically first, set up coordinates or parameters, then write the
  function or equation.
- Verify consistency at boundaries or special points numerically.

---

## Formal Definition Boxes

Use `{admonition}` with `:class: note`. Title pattern: **"What is ... ?"**

```
```{admonition} What is ... a function?
:class: note
A **function** is ...
```
```

- Definition boxes appear **after** the concept has been developed informally
  in the running text. They consolidate; they do not introduce.
- Immediately after every definition box, apply the definition to the running
  example with concrete numbers.

---

## Formulas and Notation

- Every displayed formula is followed by a sentence explaining each symbol
  in the context of the running example.
- Choose example numbers that are physically plausible and arithmetically
  manageable. Avoid trivially clean numbers and avoid numbers so messy they
  distract.
- Use display math for all key formulas. Use inline math for brief
  expressions in running text.
- Physical units appear directly in formulas using `~\text{unit}`.
- Interval notation uses square and round brackets: $[0, 24]$, $(8, 12]$.
  Do not use semicolons inside intervals.

---

## Cross-Section Connections

- Every section must contain at least one explicit **callback** to a concept
  from an earlier section.
- Every section must contain at least one explicit **forward reference** to a
  concept that will appear later, either in the same chapter or in a future
  chapter.
- Forward references should be specific enough to create genuine narrative
  tension but vague enough not to give the answer away.
- The summary and outlook paragraph is the natural place for forward
  references, but they can also appear within subsections where they arise
  naturally.

---

## Lists and Tables

- Numbered lists are used only for genuine sequential procedures (step 1,
  step 2, ...). The sketching procedure for a parabola is a valid use;
  a collection of properties is not.
- Tables are used only for genuinely tabular data: standard values of
  trigonometric functions, comparison of two methods side by side. Do not
  use tables as a substitute for prose.
- Bullet lists within the body text should be used sparingly and only when
  the items are truly parallel and enumerable.

---

## Video Dropdowns

```
```{dropdown} Video "Title" by Channel
<iframe ...></iframe>
```
```

- Place videos at the point of relevance within the text, immediately after
  the subsection where the concept was introduced.
- Do not collect videos at the end of a section.
- Label each dropdown with the video title and channel name.
- Videos are supplementary depth, not a replacement for reading.

---

## Engineering Connections

- Every section must contain at least one explicit connection to an
  engineering application.
- Engineering examples motivate the mathematics; they do not merely
  illustrate it after the fact.
- Prefer examples that are standard in the student's discipline and that
  they will encounter again in other modules.
- When a formula is given, interpret its parameters in physical terms
  immediately.

---

## Worked Examples

- Use the same running example throughout a section rather than introducing
  a new example for each concept.
- After deriving a result, verify it by substitution or by checking a
  boundary condition. Write the verification step explicitly.
- Choose parameter values so that intermediate results are interpretable,
  not just numerically correct.

---

## Closing a Chapter

- The final section of a chapter should explicitly name all the function
  families or concepts introduced in the chapter.
- The last sentence of the final summary should close the chapter as a unit
  and frame it as the foundation for the next chapter.
- Avoid ending on a loose thread; every question raised in the chapter
  should be answered by the end of it, or explicitly handed off to a named
  future section.

---

## TikZ Figures

This section defines all conventions for standalone TikZ figures. Every
figure is compiled as a `standalone` document, exported to SVG, and
embedded in the MyST Markdown source via a `{figure}` directive.

### Preamble template

Every TikZ file uses the following preamble without exception:

```latex
\documentclass[11pt]{standalone}
\usepackage{amssymb}
\usepackage{amsmath}
\usepackage[no-math]{fontspec}
\usepackage{unicode-math}
\usepackage{libertinus}
\usepackage{pgf,xcolor}
\usepackage{tikz}
\usetikzlibrary{arrows.meta, backgrounds}
\usepackage{pgfplots}
\pgfplotsset{compat=newest}
```

`pgfplots` is included in every file even when the figure uses only pure
TikZ, so that the preamble remains identical across all files and the
compilation environment is predictable.

### Font

The font is **Libertinus** throughout: Libertinus Serif for text labels and
Libertinus Math for mathematical symbols. This matches the body font of the
Jupyter Book and ensures that labels inside figures are visually
indistinguishable from inline math in the surrounding text.

Do not use TeX Gyre Heros, Computer Modern, or any other font family.

### Color palette

All figures use the following named colors. Define all seven in every file,
even if only a subset is used. This keeps the palette declaration identical
across all files and makes global adjustments straightforward.

```latex
\definecolor{my_darkgray}{HTML}{484949}
\definecolor{my_lightgray}{HTML}{F3F4F4}
\definecolor{my_darkblue}{HTML}{005A94}
\definecolor{my_lightblue}{HTML}{CCDEE9}
\definecolor{my_yellow}{HTML}{FFEC7F}
\definecolor{my_red}{HTML}{E60000}
\definecolor{my_orange}{HTML}{E87846}
```

Never introduce ad-hoc color names such as `lightblue`, `highlight`,
`myblue`, `itwm_blue`, or `bgcolor`. All colors in every figure must come
from this palette and use exactly these names.

Color usage follows these rules:

**Two-color figures (the default case).** Use `my_darkblue` for the primary
element (outline, main curve, dominant region) and `my_lightblue` for the
secondary element (fill, background region, or second curve). This pairing
provides clean contrast and is the standard for Venn diagrams, shaded
regions, and single-function graphs.

**Three-color function graphs.** Use `my_darkblue` for the first curve,
`my_red` for the second, and `my_orange` for the third. Do not use
`my_yellow` for curve lines: it lacks sufficient contrast against the light
gray background and becomes invisible at small sizes. Reserve `my_yellow`
for highlighted fill regions where it is surrounded by a visible border.

**Text and annotation.** Use `my_darkgray` for secondary labels and
annotations where full black would be too heavy. Use `my_darkblue` for
labels that identify mathematical objects (set names, axis labels on
diagrams). Default TikZ black is acceptable for element labels inside
diagrams.

### Background panel

Every figure carries an explicit background panel. This ensures correct
rendering in both light and dark browser themes, because the figure never
inherits the document background color. The background color is
`my_lightgray`, so no separate `bgcolor` definition is needed.

Apply the background at the opening of every `tikzpicture` environment:

```latex
\begin{tikzpicture}[
    show background rectangle,
    background rectangle/.style={fill=my_lightgray, rounded corners=8pt},
    inner frame sep=0.8cm
]
```

Use `inner frame sep=0.3cm` only for wide, shallow figures such as number
lines where the default padding would produce excessive whitespace. Use
`0.8cm` in all other cases.

To adapt the entire figure set to a dark theme, redefine `my_lightgray`
globally. No other changes to individual files are required, provided the
color rules above have been followed consistently.

### Axis style for function graphs (pgfplots)

All function graphs use the following axis options:

```latex
\begin{axis}[
    axis lines = center,
    xlabel = {$x$},
    ylabel = {$y$},
    grid = both,
    axis equal,
    axis line style={thick},
]
```

Omit `axis equal` only when the natural aspect ratio of the function would
make the graph unreadable at equal scaling, for example for functions with
very different x and y ranges. Document the omission with a comment.

All plotted curves use:

```latex
\addplot[draw=itwm_blue, samples=300, ultra thick, domain=a:b]{ ... };
```

For functions with poles or other singularities, split the domain into
separate `\addplot` calls, one for each continuous branch. Do not rely on
`restrict y to domain` alone to suppress the discontinuity artifact: always
split at the singularity explicitly, and add `restrict y to domain` only as
a safety net.

### Legends

When a figure shows more than one curve, include a legend. Use the following
style options on the axis:

```latex
legend pos=north west,
legend style={font=\small},
legend cell align=left,
```

Add legend entries with `\addlegendentry{...}` immediately after each
`\addplot` call. Do not use the `legend entries={...}` key on the axis, as
it separates entry declarations from the plot commands they describe and
makes the file harder to maintain.

### Venn diagrams and set diagrams

For diagrams involving filled regions such as Venn diagrams, use
`my_lightblue` for highlighted regions and `white` for regions that are
explicitly empty. Label the universal set and all named sets in
`my_darkblue` with `font=\bfseries`. Place element labels with `font=\small`.

When illustrating a complement $A^C = W \setminus A$, use the following
three-step fill sequence:

1. Fill the universal set region with `my_lightblue` (this paints the
   complement).
2. Fill the inner set $A$ with `white` (this erases the highlight inside
   $A$).
3. Draw the outlines of both shapes with `my_darkblue` at `line width=1.5pt`.

Do not fill the inner set with `my_lightgray` first and then overwrite with
`white`. Since `my_lightgray` is not pure white, using it as an intermediate
fill would create a visible color difference between the inside of $A$ and
the panel background whenever `my_lightgray` is changed for theme switching.

### Figure captions

Every figure referenced in the MyST Markdown source carries a caption of
the form:

```
Graph of [what the figure shows].
(Source: own figure; licence [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Keep the descriptive part to one sentence. Do not repeat information that
is already stated in the surrounding text.

### File naming

Name figure files descriptively and in lowercase with underscores. Append
the language code `_EN` or `_DE` only when two language versions of the
same figure exist. Do not include chapter or section numbers in the filename:
figure files are referenced by path from the MyST source and the directory
structure provides the organizational context.
