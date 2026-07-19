# Writing Style for Maloney's Geometry

## Theorem Structure
1. **Name and formal statement** (in math notation)
2. **Proof**:
   - State what you assume
   - Reference axioms/theorems by number: "By Axiom 5..."
   - Use logical notation: $\implies$, $\land$, $\lor$, $\neg$, $\forall$, $\exists$
   - End with ∎

## Proof Density
Match the rigor of primatives.tex (Chapter 1) and linear-notions.tex (Chapter 2). Every step must be justified, no hand-waving.

Example good proof: Theorem 13 (Left-Reversal of Congruence) in primatives.tex

## Before Each Definition/Axiom
Write 1-2 sentences of motivation. Explain:
- Why this is needed
- What degenerate model it excludes (if applicable)

Example: Axiom 10 (Identity of Congruence) excludes the "zero-distance universe" where all points are equidistant.

## First-Person Voice
Use "we": "We now define...", "It is useful to note...", "We proceed by contradiction..."

## Degenerate Cases
Name and discuss explicitly, don't suppress them. Example: straight angles, null angles.

## No Abbreviations in Formal Statements
Write $\mathcal{B}(A,B,C)$, not $[ABC]$ in axiom statements (reserve $[ABC]$ for informal prose).
