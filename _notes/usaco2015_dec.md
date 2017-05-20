---
layout: note
title: Select USACO 2015 Problem
date: 2017-05-19
---

From USACO 2015 December Contest, Gold:

### Fruit Feast

Bessie has broken into Farmer John's house again! She has discovered a pile of lemons and a pile of oranges in the kitchen (effectively an unlimited number of each), and she is determined to eat as much as possible.
Bessie has a maximum fullness of \\( T \\) \\( (1≤T≤5,000,000) \\). Eating an orange increases her fullness by \\( A \\), and eating a lemon increases her fullness by \\( B \\) \\( (1≤A,B≤T) \\). Additionally, if she wants, Bessie can drink water at most one time, which will instantly decrease her fullness by half (and will round down).

Help Bessie determine the maximum fullness she can achieve!

**INPUT FORMAT:**

The first (and only) line has three integers \\(T\\), \\(A\\), and \\(B\\).

**OUTPUT FORMAT:**

A single integer, representing the maximum fullness Bessie can achieve.

#### Solution


Here is my solution without boilerplate:


{% highlight c++ %}
int T, A, B;
bool full[5000010];

void dp(int i, bool halved) {
    if (i < 0 || i > T || full[i])
        return;
    full[i] = true;
    dp(i+A, halved);
    dp(i+B, halved);
    if (!halved)
        dp(i/2, true);
}

int main() {
    cin >> T >> A >> B;
    dp(0, false);
    int ans = 0;
    for (int i = T; i >= 0; i--) {
        if (full[i]) {
            ans = i;
            break;
        }
    }
    cout << ans << endl;
}
{% endhighlight %}
