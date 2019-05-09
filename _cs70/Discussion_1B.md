---
title: Discussion 1B
topic: Stable Marriage
---

# Induction Problem

A party has $$n \geq 2$$ people. A *celebrity* is a person who knows nobody, but everyone knows the celebrity. If you ask questions of the form ***Does*** $$A$$ ***know*** $$B$$ ***?*** prove that you can figure out who the celebrity is (or that there is no celebrity) using $$3 n - 4$$ questions.

# Stable Marriage

There are $$n$$ men and $$n$$ women. Each man has his own preference list of the women, and likewise for the women. The goal is to pair up the men and women according to their preferences.

## Definitions
- **pairing** - a set of $$n$$ pairs of men and women
- **rogue couple** - given a pairing, a man and a woman form a rogue couple if they would rather be with each other than their current partners
- **stable** - a pairing is stable if there are no rogue couples
- **optimal** - the optimal woman for a man is the best woman the man could be paired with over all stable pairings

## Stable Marriage Algorithm

The men go down their lists, proposing to women. When a woman receives multiple proposals, she keeps her favorite man on her string and rejects the other men, who continue down their lists. The algorithm ends when every woman receives one proposal.

**Improvement Lemma** - if a woman has a man on her string, then for every day after she will either have the same man or a better man on her string

**Theorem** - the algorithm always terminates with a male-optimal stable pairing

# Worksheet
## 1. Stable Marriage

The algorithm takes four days (it terminates on the fifth) and the final pairing is $$(A,2),(B,1),(C,3)$$.

## 2. Propose-and-Reject Proofs

**a**
The Improvement Lemma says if a woman receives a proposal, then on each day after she will either have the same man on her string or get proposals from better men.

**b**
Suppose for the sake of contradiction that she receives no proposal on day $$i$$ but receives a proposal on a previous day $$j$$. Then using part **a**, since she receives a proposal on day $$j$$ she receives proposals for all subsequent days, including day $$i$$. This contradicts the assumption that she receives no proposal on day $$i$$.

**c**
Let the number of days the algorithm takes be $$k$$. Since the algorithm ends, every woman has a proposal on day $$k$$. Since the algorithm does not end on day $$k-1$$, there is some woman who does not have a proposal on day $$k-1$$. Then using part **b**, she did not receive proposals on all days before $$k-1$$, so she only receives one proposal (on day $$k$$).

## 3. Be a Judge

**a**
False. If this were true that would mean every man gets rejected $$n-1$$ times and every woman gives $$n-1$$ rejections. This contradicts what we proved before: that there is some woman who is proposed to exactly once.

If $$n=2$$, can this be true?

**b**
True. Suppose they aren’t paired, so that in the final pairing we see the pairs $$(M, W')$$ and $$(M', W)$$. In this final pairing, $$M$$ and $$W$$ form a rogue couple since they each prefer the other over their current partners. Therefore this isn’t a stable pairing.

**c**
False. Consider the counterexample with $$n=2$$ with men $$1$$ and $$2$$ and women $$A$$ and $$B$$. Both men have the preference list $$B > A$$ and both women have the preference list $$2 > 1$$. The algorithm terminates with the pairing $$(A, 1), (B, 2)$$.

**d**
True. If for every pair $$(M_i, W_i)$$ they each have the other as their least favorite partner, then any other choice of $$M_j$$ and $$W_k$$ is a rogue couple.

# Induction Problem Solution
## Base case

For $$n=2$$, we ask the two questions ***Does*** $$A$$ ***know*** $$B$$***?*** and ***Does*** $$B$$ ***know*** $$A$$***?***

## Inductive hypothesis

Assume that at a party with $$n$$ people we can figure out who the celebrity is using $$3 n - 4$$ questions.

## Inductive step

Our goal is to show that at a party with $$n+1$$ people we need to use $$3(n+1)-4$$ questions.
First we ask ***Does*** $$A$$ ***know*** $$B$$***?*** If $$A$$ knows $$B$$, then $$A$$ is not a celebrity; otherwise, if $$A$$ does not know $$B$$, then $$B$$ is not celebrity. In both cases, we are left with $$n$$ people who are potentially celebrities. So, we can use our inductive hypothesis and ask $$3 n - 4$$ questions to learn one of the following:

1. There’s no celebrity among the $$n$$ people, and since the person we excluded is not a celebrity, we know there is no celebrity among the $$n+1$$ people. We use one additional question, meaning we ask a total of $$3 n -3$$ questions.
2. There’s a celebrity among the $$n$$ people, but we need to check whether this person is still a celebrity among the $$n+1$$ people. This requires us to ask two questions: whether the potential celebrity and the $$n+1$$th person know each other. We use three additional questions, meaning we ask a total of $$3 n - 1$$ questions.

