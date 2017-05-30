---
layout: note
title: Select USAPhO 2015 Problem
date: 2017-05-29
---

From USAPhO 2016:

A uniform solid spherical ball starts from rest on a loop-the-loop track. It rolls without slipping along the track. However, it does not have enough speed to make it to the top of the loop. From what height $$h$$ would the ball need to start in order to land at point $$P$$ directly underneath the top of the loop? 

Express your answer in terms of $$R$$, the radius of the loop. Assume that the radius of the ball is very small compared to the radius of the loop, and that there are no energy losses due to friction.

<img src="/images/usapho2016_b0.png" height="300px"  style="display:block;margin:auto">

---

#### Solution

At what point does the ball lose contact with the loop? Since its velocity at that point must be adjacent to the loop, the ball loses contact with the loop above and to the right of $$P$$ in order to land at $$P$$. 

<img src="/images/usapho2016_b1.png" height="300px"  style="display:block;margin:auto">

As a result, its height above the ground is $$y = R + R \sin{\theta}$$ and horizontal position with respect to $$P$$ is $$x = R \cos{\theta}$$.

When the ball loses contact with the loop, it has some velocity $$v$$ and rotates with some angular velocity $$\omega$$. 

By conservation of energy, we have

$$ mgh = mg (R + R \sin{\theta}) + \frac{1}{2} m v^2 + \frac{1}{2} I \omega^2 $$

The moment of inertia of the ball is $$I = \frac{2}{5} m r^2$$, and because it does not slip, we have

$$
\begin{align*}
mgh &= mg (R + R \sin{\theta}) + \frac{1}{2} m v^2 + \frac{1}{2} \frac{2}{5} m r^2 \omega^2 \\
    &= mg (R + R \sin{\theta}) + \frac{1}{2} m v^2 + \frac{1}{5} m v^2 \\
    &= mg (R + R \sin{\theta}) + \frac{7}{10} m v^2
\end{align*}
$$

At this point, the loop exerts no normal force on the ball, so the only force acting on the ball is gravity. Since it travels along a circular loop, the centripetal force is given by the component of gravity directed towards the center, or

$$
\begin{align*}
m \frac{v^2}{R} &= m g \sin{\theta} \\
v^2 &= g R \sin{\theta}
\end{align*}
$$

Now the ball is a projectile that lands at $$P$$. Let $$t$$ be the time the ball is in projectile motion. If the ball's velocity $$v$$ is tangent to the loop, then its horizontal component is $$v \cos{\theta}$$ and its vertical component is $$v \sin{\theta}$$. Using kinematics,

$$
\begin{align*}
R \cos{\theta} &= (v \sin{\theta}) t \\
t &= \frac{R \cos{\theta}}{v \sin{\theta}}
\end{align*}
$$

and

$$
\begin{align*}
0 &= (R + R \sin{\theta}) + (v \cos{\theta}) t - \frac{1}{2} g t^2
\end{align*}
$$
