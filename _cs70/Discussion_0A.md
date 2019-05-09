---
title: Discussion 0A
topic: Logic
dropbox: https://paper.dropbox.com/doc/Discussion-0A--Aa8hFieI~ksvZIEcA5OMpT2eAQ-c9L5zYpxZTH9H4BeEfckQ
---

- OH: Th 3 to 4pm in Soda 651
- Discussion: TuTh 5 to 6pm in Dwinelle 105
- Logistics: Piazza and [sp19@eecs70.org](mailto:sp19@eecs70.org)

# Review

## Propositional Logic
- **proposition**: statement that evaluates to true or false
  - **conjunction**: $$P \land Q$$, $$P \text{ and } Q$$
  - **disjunction**: $$P \lor Q$$, $$P \text{ or } Q$$
  - **negation**: $$\lnot P$$, $$\text{not } P$$
  - **implication**: $$P \Rightarrow Q$$, $$\lnot P \lor Q$$
    - or $$\text{hypothesis} \Rightarrow \text{conclusion}$$
    - when $$P$$ is false, the implication is true regardless of $$Q$$. this is called a vacuous statement
- given an implication $$P \Rightarrow Q$$
  - **contrapositive**: $$\lnot Q \Rightarrow \lnot P$$
    - has the same truth value: $$(P \Rightarrow Q) \equiv (\lnot P \lor Q) \equiv (Q \lor \lnot P) \equiv (\lnot Q \Rightarrow \lnot P)$$
  - **converse**: $$Q \Rightarrow P$$
    - not necessarily the same truth value
  - $$P \equiv Q$$ means both $$P \Rightarrow Q$$ and $$Q \Rightarrow P$$

## Quantifiers
- **universal quantifier**: $$\forall$$, for all
  - $$\forall x P(x)$$ is whether $$P(x)$$ evaluates to true for all values of $$x$$
- **existential quantifier**: $$\exists$$, there exists
  - $$\exists x P(x)$$ is whether $$P(x)$$ evaluates to true for some value of $$x$$

## Negation
- \\( \lnot (P \land Q) \equiv (\lnot P \lor \lnot Q) \\)
- \\( \lnot (P \lor Q) \equiv (\lnot P \land \lnot Q) \\)
- \\( \lnot (\forall x P(x)) \equiv \exists x \lnot P(x) \\)
- \\( \lnot (\exists x P(x)) \equiv \forall x \lnot P(x) \\)

