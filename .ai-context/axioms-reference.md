# Maloney's Geometry — Axiom Reference

## Primitive Notions
- **Points**: Set $\mathbf{P}$
- **Betweenness**: Relation $\mathcal{B}(A,B,C)$ — "$B$ lies between $A$ and $C$"
- **Congruence**: Relation $\cong$ — segment equivalence

## Axioms of Betweenness
1. **Symmetry**: $\mathcal{B}(A,B,C) \implies \mathcal{B}(C,B,A)$
2. **Order**: $\mathcal{B}(A,B,X) \implies \neg\mathcal{B}(B,A,X) \land \neg\mathcal{B}(A,X,B)$
3. **Identity**: $\mathcal{B}(A,B,A) \implies A = B$
4. **Density**: $A \neq C \implies \exists B: \mathcal{B}(A,B,C)$
5. **Extensibility**: $A \neq B \implies \exists C: \mathcal{B}(A,B,C)$
6. **Transitivity**: $\mathcal{B}(A,B,C) \land \mathcal{B}(B,C,D) \land B \neq C \implies \mathcal{B}(A,B,D)$

## Axioms of Congruence
1. **Reversal**: $AB \cong BA$
2. **Transitivity**: $AB \cong CD \land AB \cong EF \implies CD \cong EF$
3. **Identity**: $AB \cong CC \implies A = B$ (excludes zero-distance universe)

## Axioms on Interaction
- **Segment Construction** (Ax 11): $\forall Q, X, A, B: Q \neq X \implies \exists Y: \mathcal{B}(Q,X,Y) \land XY \cong AB$
- **Plane Separation** (Ax 15): Line $\ell$ partitions plane into two half-planes $H_{\ell,A}, H_{\ell,B}$
- **Midpoint Existence/Uniqueness** (Ax 12–13): Every segment has exactly one midpoint

## Key Theorem Names (for reference)
- **Thm 10**: Reflexivity of Congruence
- **Thm 11**: Symmetry of Congruence
- **Thm 12**: Full-Transitivity of Congruence
- **Thm 29**: Same-Side Transitivity
- **Thm 30**: Partition Theorem (half-planes)

## NO Distance Metric
Do not introduce $d(A,B)$, degrees, radians, or real numbers. All proofs use $\mathcal{B}$, $\cong$, $S$, $H$ only.
