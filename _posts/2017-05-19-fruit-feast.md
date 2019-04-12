---
title: Fruit Feast
date: 2017-05-19
---

# {{ page.title }}

From USACO 2015 December Contest, Gold:

# Fruit Feast

> Bessie has broken into Farmer John's house again! 
> She has discovered a pile of lemons and a pile of oranges in the kitchen (effectively an unlimited number of each), and she is determined to eat as much as possible.
> Bessie has a maximum fullness of $$ T $$ $$ (1≤T≤5,000,000) $$. 
> Eating an orange increases her fullness by $$ A $$, and eating a lemon increases her fullness by $$ B $$ (with $$ 1≤A,B≤T $$). 
> Additionally, if she wants, Bessie can drink water at most one time, which will instantly decrease her fullness by half (and will round down).  
>
> Help Bessie determine the maximum fullness she can achieve!
>
> **INPUT FORMAT:**
> 
> The first (and only) line has three integers $$T$$, $$A$$, and $$B$$.
> 
> **OUTPUT FORMAT:**
> 
> A single integer, representing the maximum fullness Bessie can achieve.

## Solution

If Bessie can reach a fullness value of $$ t $$, then she can also reach fullness values of $$t+A$$ and $$t+B$$. 
Since Bessie starts at a fullness of $$0$$, she can immediately reach fullness values of $$A$$ and $$B$$, and then continue from there.

Since we get unlimited uses of oranges and lemons, this is an unbounded knapsack problem. 
We can solve knapsack problems using dynamic programming. 
However, we also need to consider whether Bessie drinks water, which will allow her to reach a fullness value of $$ \lfloor \frac{i}{2} \rfloor $$, but unable to drink water again. 

We define our subproblem $$F(t, w) $$ to be whether Bessie can achieve a fullness of $$ t $$, with $$ w = 0 $$ without drinking water and $$ w = 1 $$ having drunk water.
Then our recurrence relation is

$$
\begin{align*}
    F(t, 0) &= F(t - A, 0) \lor F(t - B, 0) \\
    F(t, 1) &= F(t - A, 1) \lor F(t - B, 1) \lor F(2 t, 0) \lor F(2 t + 1, 0)
\end{align*}
$$

But what order should we solve our subproblems in?
Notice that all subproblems of the form $$ F(t, 0) $$ depend only on subproblems with fullness values less than $$ t $$.
This means we can solve $$ F(t, 0) $$ subproblems by iterating over increasing values of $$ t $$.
What about $$ F(t, 1) $$?
Like in the case of $$ F(t, 0) $$, $$ F(t, 1) $$ depends on subproblems with fullness values less than $$t$$, but it also depends on the special cases when Bessie drinks water and halves her fullness.
Fortunately, these special cases fall under the $$ F(t, 0) $$ case, which means we can solve the $$ F(t, 1) $$ subproblems if we solve the $$ F(t, 0) $$ first.

Here is an iterative dynamic programming solution in Java:

```java
int fruitFeast(int T, int A, int B) {
    boolean[][] full = new boolean[T + 1][2];
    full[0][0] = true;

    // solve F(t, 0) subproblems first
    for (int t = 0; t <= T; t++) {
        // F(t, 0) = F(t - A, 0) or F(t - B, 0)
        if (t - A >= 0 && full[t - A][0])
            full[t][0] = true;
        if (t - B >= 0 && full[t - B][0])
            full[t][0] = true;
    }

    // solve F(t, 1) subproblems
    // we'll ignore bounds checks for simplicity
    for (int t = 0; t <= T; t++) {
        full[t][1] = full[t - A][1] || full[t - B][1]
                || full[2 * t][0] || full[2 * t + 1][0];
    }

    // return the largest value of t that Bessie can reach
    for (int t = T; t >= 0; t--)
        if (full[t][0] || full[t][1])
            return t;
    return 0;
}
```

Here is my original, full recursive dynamic programming solution in C++:

```cpp
#include <iostream>

using namespace std;

int T, A, B;
bool full[5000010];

void dp(int i, bool drank) {
    if (i < 0 || i > T || full[i])
        return;
    full[i] = true;
    dp(i+A, drank);
    dp(i+B, drank);
    if (!drank)
        dp(i / 2, true);
}

int main() {
    cin >> T >> A >> B;
    dp(0, false);
    for (int i = T; i >= 0; i--) {
        if (full[i]) {
            cout << i << endl;
            break;
        }
    }
}
```