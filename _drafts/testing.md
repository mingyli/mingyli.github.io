---
title: Testing
description: Just for testing
---

# Table of Contents

- TOC
{:toc}

# Header 1

This is a test page designed to be used during development, to make sure that
the custom CSS covers all the kinds of Kramdown supports. For example,
this text **should be bold** and this text *should be italic*. Meanwhile, this
represents `inline code` and this represents a [hyperlink](#header-2).
This is a footnote.[^1] This is a footnote.[^footnote]

This is a test page designed to be used during development, to make sure that
the custom CSS covers all the kinds of Kramdown supports. For example,
<span class="marginnote">
    This is a margin note.
    This text **should be bold** and this text *should be italic*.
    Meanwhile, this
    represents `inline code` and this represents a [hyperlink](#).
</span>
this text **should be bold** and this text *should be italic*. Meanwhile, this
represents `inline code` and this represents a [hyperlink](#).

> This is a test page designed to be used during development, to make sure that
> the custom CSS covers all the kinds of Kramdown supports. For example,
> this text **should be bold** and this text *should be italic*. Meanwhile, this
> represents `inline code` and this represents a [hyperlink](#).


This is a margin note.
This text **should be bold** and this text *should be italic*.
Meanwhile, this
represents `inline code` and this represents a [hyperlink](#).
{: .marginnote}

## Header 2

This is a term
: this is a definition
: this is another definition

- a list
- with
- no nesting

End of first list

- nested list
    - nested
- another point
    - nested again

And then *in-line-margin-note*{:.marginnote} another list: 

- this time with paragraphs and nesting

  this is another paragraph

- some random point

  another point

1.  Point 1
2.  Point 2

What about mixing the two?

1. Point 1
    - first bullet
    - second bullet

2. Point 2
    - third bullet
    - fourth bullet

This is a margin note.
This text **should be bold** and this text *should be italic*.
Meanwhile, this
represents `inline code` and this represents a [hyperlink](#).
{: .marginnote}

1. Hm
    - is
    - this
        - nested
            - or 
        - not

This is $$ \LaTeX $$.
This is math: $$ \sum_{i=1}^n X_i = X $$.
This is math:

$$ \binom{n}{k} = \binom{n-1}{k} + \binom{n-1}{k-1} $$

### Header 3

```ruby
class A
  def foo; end
end

# comment
# this line should be 80 characters long. this line should be 80 characters long

Opus::Ops::DB::Model::NetworkTransaction::SettlementState.readytosubmit(arg0, arg1, arg2, arg3)
```

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

Paragraph in between.


    No paragraph between this and the next


```
┌───┐
│ × │
└───┘
```


Here we see a horizontal rule:

- - -

This is a margin note.
This text **should be bold** and this text *should be italic*.
Meanwhile, this
represents `inline code` and this represents a [hyperlink](#).
{: .marginnote}


How do emoji render? 🤔 👌 🚀

SFO -> LAX

# Footnotes

[^1]: Footnote definition

[^footnote]: Another definition
