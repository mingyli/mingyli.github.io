---
layout: note
title: Charge Sharing
date: 2017-05-29
---

In all circuits involving charge sharing, keep the following in mind:

1. Kirchhoff's voltage law.
2. Conservation of charge in closed systems (such as isolated  sections of wire)
3. The charges on the plates of a capacitor are equal in magnitude and opposite in sign.

Charge will arrange itself in order to satisfy these conditions.
A common misconception students have is that charge is distributed evenly among capacitors. We will show that this is not necessarily the case.

<img src="/images/charge_sharing0.png" height="200px"  style="display:block;margin:auto">

In the above diagram, capacitor 1 begins with a positive charge $$+q$$ on its top plate and negative charge $$-q$$ on its bottom plate. Capacitor 2 has no charge. 

When the switch is closed, the charge in the circuit rearranges in order to satisfy the charge sharing conditions. Observe that the section of wire in the top half of the circuit is completely isolated; this means that the total charge in the top half must remain $$+q$$.

Let $$q_1$$ and $$q_2$$ be the charges on capacitor 1 and capacitor 2 respectively after the switch is closed. We label each top plate as positive and each bottom plate as negative (the labeling scheme won't matter in the end as long as we are consistent). By conservation of charge, we know that $$q_1 + q_2 = q$$.

<img src="/images/charge_sharing1.png" height="200px"  style="display:block;margin:auto">

By KVL, we know that voltages across the capacitors must be equal. Let the voltage be $$V$$. 

$$
\begin{align*}
    V &= \frac{q_1}{C_1} = \frac{q_2}{C_2} \\
        &= \frac{q_1 + q_2}{C_1 + C_2} \\
        &= \frac{q}{C_1 + C_2}
\end{align*}
$$

Here we use a neat algebraic trick: $$\frac{a}{b} = \frac{c}{d} = \frac{a+c}{b+d}$$. 

Now that we have $$V$$, we can now solve for $$q_1$$ and $$q_2$$.

$$
\begin{align*}
    q_1 &= C_1 V \\
        &= C_1 \frac{q}{C_1 + C_2} \\
    q_2 &= C_2 V \\
        &= C_2 \frac{q}{C_1 + C_2}
\end{align*}
$$

Notice that $$q_1$$ and $$q_2$$ are not necessarily the same. In fact, $$q_1 = q_2$$ only if $$C_1 = C_2$$ (assuming $$q \neq 0$$).

Isn't that wild?
