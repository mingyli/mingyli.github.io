---
title: Discussion 0B
topic: Proof Techniques
---
# Discussion 0B

# Proof techniques
## Direct

To prove $$P \Rightarrow Q$$, begin with $$P$$ and derive more facts until you reach $$Q$$.
Often, direct proofs apply to questions of the form $$P_0 \land P_1 \land \cdots \land P_n \Rightarrow Q$$ because the various $$P_i$$s together can lead to intermediate logical steps.

## Contraposition

Since an implication $$P \Rightarrow Q$$ and its contrapositive $$\lnot Q \Rightarrow \lnot P$$ are equivalent, you can prove the contrapositive instead. 
Proof by contraposition can be useful for questions of the form $$P \Rightarrow Q_0 \lor Q_1 \lor \cdots \lor Q_n$$ for the same reason as above because this is equivalent to $$\lnot Q_0 \land \lnot Q_1 \land \cdots \land \lnot Q_n \Rightarrow \lnot P$$.

## Contradiction

To prove $$P$$, assume $$P$$ is false and that results in something known to be false $$(\lnot P \Rightarrow \text{false})$$.
Proof by contradiction is a type of proof by contraposition because $$\text{true} \Rightarrow P$$ is equivalent to $$\lnot P \Rightarrow \text{false}$$.

## Cases

Suppose there are cases $$C_0, C_1, \cdots, C_n$$ of which at least one must be true. You can prove $$P$$ by showing $$P \land C_i$$ is true for each of the $$C_i$$ when $$C_i$$ is true.  This is because $$P \equiv P \land (C_0 \lor \cdots \lor C_n) \equiv (P \land C_0) \lor \cdots (P \land C_n)$$.
Proof by cases is helpful when knowing $$C_i$$ gives you information to complete the proof that $$P$$ alone does not.

