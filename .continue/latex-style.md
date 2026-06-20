---
name: LaTeX Standards
---

# Core Document Architecture & Tokenization
- Any mathematical variables or constants MUST be enclosed in dollar signs (e.g., `$A$`, `$B$`).
- Grammatical periods MUST NOT appear in inline math blocks. Example: `$A$, $B$, and $C$` is acceptable, while `$x=3.$` is not. However, mathematical commas must still remain within inline math blocks (e.g., `$A, B \in \mathbf{P}$`).
- There SHOULD be spaces around binary operators and relations inside inline blocks. Example: `$A = B$`.
- Always use amsmath's `\dots`. Put these outside of inline math when separating prose items.
- Always use `\coloneqq` over `\coloneq` for definitional equivalence assignments.
- Always include a space after `\{` and before `\}` in set-builder notation (e.g., `\{ x \mid x > 5 \}`).

# Display Math Environments
- For single-line display math, use of `\[ ... \]` is required. Line breaks after `\[` and before `\]` are optional but highly recommended.
- When a series of equations are too long to fit on a single line, one MUST NOT have adjacent `\[ ... \]` expressions. In most cases, the `align*` environment SHOULD be used instead.
- When using `align*`, `\begin{align*}` and `\end{align*}` MUST be on their own lines. There MUST be a line break after each `\\` invocation. There MAY be additional line breaks for legibility, and there MUST be additional line breaks if they are necessary to keep the source line length within readability limits.

# Structural Spacing & Vertical Whitespace
- **Logical Constraints:** You MUST use a structural `\quad` to isolate logical constraints or quantifiers (e.g., `\forall` operators) from core display equations.
- **Side-by-Side Formulas:** Separate dual, independent mathematical statements placed on a single display line using exactly `\qquad`.
- **Trailing Punctuation:** Apply a thin space `\,` immediately prior to any trailing sentence punctuation (periods or commas) inside display math blocks.
- **Text Connectives:** Do not use raw trailing spaces inside `\text{}` to separate equations. Keep spacing structural outside the macro (e.g., use `\[ A=B \quad \text{and} \quad C=D \]`).
- **High-Level Layout Isolation:** Structural block declarations (`\chapter`, `\section`, `\begin{environment}`) MUST be isolated by exactly one empty line above and below in the source code to maximize terminal and editor scannability.
- **Paragraph Integrity:** There MUST NOT be an empty line separating text prose from an immediate display math environment `\[ ... \]` or an internal environment body, as this forces an unwanted `\par` layout indentation shift. Do not place an empty line between a section header and its starting text block.

# Delimiter & Parentheses Scaling
- You MUST NOT use automatic scaling delimiters (`\left` and `\right`) inside inline math `$ ... $` body paragraphs.
- You MUST NOT use automatic `\left` and `\right` scaling around variables containing overhead accents (e.g., `\overline{AB}` or `\overleftrightarrow{XY}`). Use manual sizing commands like `\big(` and `\big)` if minor clearance is required.
- You MUST use `\left` and `\right` (or explicit manual steps like `\Bigg`) for multi-level display fractions (`\frac` or `\dfrac`) to ensure brackets scale to fully enclose the numerator and denominator.

# Label Namespaces & Cross-Referencing
- All cross-reference anchors MUST use strict lowercase, colon-separated semantic prefixes: `ax:` (axiom), `thm:` (theorem), `lem:` (lemma), `def:` (definition), `chap:` (chapter), `sec:` (section), `fig:` (figure/tikz).
- Label content strings MUST use lowercase kebab-case layout format (e.g., `\label{ax:identity-betweenness}`).
- Reference invocations inside text prose MUST link using a non-breaking space tie rather than a standard space (e.g., use `Axiom~\ref{ax:order}` instead of `Axiom \ref{ax:order}`) to prevent structural numbers from hanging across line margins.

# Source Code Formatting & Cleanliness
- The inner contents of any `\begin{...} ... \end{...}` environment SHOULD be indented by exactly 2 spaces (one logical tab step configured via your `settings.json`) per nesting layer.
- There MUST NOT be any trailing whitespace; no line in the source file may end with a trailing whitespace character.
- Paragraph breaks MUST be typeset using two or more line breaks (i.e., one empty line between paragraphs), and MUST NOT be typeset using `\\` or other line-breaking tactics inside body prose.
- **Zero-Boilerplate Policy:** Actively filter and delete stray web URLs, draft notes, or compilation scrap markers during file modifications. Never output structural placeholders or unfinished layout markers (like `% TODO`).

# TikZ & Diagram Design Rules
- **Preamble Dependency:** Diagrams MUST assume global style macros are initialized: `geometry/line`, `geometry/aux`, and `geometry/point`.
- **Explicit Coordinates:** All geometric nodes and vertices in a `tikzpicture` environment MUST be initialized via explicit coordinate commands (e.g., `\coordinate (A) at (0,0);`) before being used in paths. Absolute coordinate tuples MUST NOT be hardcoded inline inside a drawing path sequence.
- **Label Separation:** Coordinate definitions, visual dot markers, and alphanumeric text labels MUST be handled as independent, distinct line commands in the code block.
- **Relative Vector Positioning:** Interdependent geometric arrays SHOULD be built using structural calculations via the `calc` library (e.g., midpoints `$(A)!0.5!(B)$` or projections `$(A)!(P)!(B)$`) rather than absolute manual numbers.
- **Background Layering:** Solid polygon fills, shading masks, or angle arc indicators MUST be enclosed inside a `pgfonlayer{background}` environment block to guarantee that structural line paths and vector strokes remain completely unobstructed in the foreground.
- **Angle Formats:** Angle arcs MUST use the native `angles` library syntax matching the counterclockwise triplet signature format `{angle = A--B--C}`.
