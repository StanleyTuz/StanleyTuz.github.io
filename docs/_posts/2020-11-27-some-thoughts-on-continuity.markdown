---
layout: posts
title:  "Some Basic Thoughts on Continuity and Differentiability"
date:   2020-11-26 10:49 PM
categories: jekyll update
usemathjax: true
tags: calculus analysis continuity differentiability
---

<h2>Thoughts on continuity, differentiability.</h2>
Continuity gives local info. So does derivative. How do they differ? 

{% comment %}{% cite Sp65 Ru64 --file refs %}{% endcomment %}


<div class="theorem" text="Stan's Theorem">This is my fancy theorem.</div>
<div class="proof">This is the proof of my fancy theorem.</div>








- Trying to understand the inverse function theorem. It says that being differentiable with non-zero derivative means that we can locally take an inverse, and also that the inverse will be differentiable. The proof is quite involved,so I wanted to step back and think about rudiments first.

- The epsilon-delta definition of limit says that we can make our function arbitrarily close to the limiting value by restricting the domain to be sufficiently small. In the case of continuous functions, the limit of the function *is* the value of the function. Basically, continuous functions behave as we would expect as we move toward a point of continuity.
- A key idea is that continuity is a local property, since it is defined at a point, and is based on behavior of the function near --- i.e., in a neighborhood about --- that point. Continuity (and limits in general) tell us that a function can be made arbitrarily close to a particular value.
- An example of this is if we have $f$ continuous at some point $a$ with $f\left(a\right)>0$. In this case, since continuity allows us to restrict function values to be arbitrarily close to $f\left(a\right)$ by keeping the domain sufficiently tight about $a$, and since $f\left(a\right)>0$, we can ensure that $f\left(x\right)>0$ for any $x$ close enough to $a$. Prove this as a lemma!
- Thus, continuity of a function at a point is giving us some information about how a function behaves nearby that point. Compare continuity and limit: if not continuous, but limit exists, then it is a removable discontinuity, and we get the same information, except that the function is arbitrarily close to the *limit* and not to the actual function value.
- Notice that this holds for any continuous function. For example, if we have a continuously differentiable function $f$ --- so that the derivative $f'$ exists and is itself continuous --- then we know that the derivative function satisfies this same propert: if $f'(a)>0$, then it is positive on some small region about $a$.

- The derivative of a function is a similar creature in that both the derivative and the definition of continuity involve limits, but the quantity of which we are taking the limit has an important difference. Continuity describes what the function itself approaches as we near a point, while the derivative describes what the "difference quotient" approaches as we approach the point. AKA the slope of the tangent line to the graph of the function.
- In all situations, differentiability at a point implies continuity at that point; the converse does not hold, and the canonical counterexample is the function $f\left(x\right) = \left|x\right|$.

- Think about mean-value theorem?

This is not a theorem 



- What does it mean if $$f$$ is differentiable at $$a$$, and $f'\left(a\right)>0$? From the definition, it means that as we approach $a$, the slope of the tangent line to the graph of the function approaches the quantity $f'\left(a\right)$, which is positive. My intuition tells me that this means that the function is "instantaneously increasing" at $a$, but when I go to prove it, I run into some difficulty: is it enough to say that $f'\left(a\right)>0$ means that $f$ increasing on some local neighborhood of $$a$$ (spoiler: it is not).

-[Do my "proof" and show that the most we can conclude in this case is that $f\left(x\right)>0$ for $x>a$, etc. This does not mean that it is increasing!]

- Show my counterexample of $f\left(x\right) = x$ where $x in \mathbb{Q}$ and $f\left(x\right)=\sin\left(x\right)$ otherwise, which is only differentiable at $x=0$ and has derivative $1$, yet is clearly neither increasing nor decreasing on any neighborhood of $0$. How does this make sense in light of my previous "proof?"

- Use the notion of continuous differentiability to save the day. From the above lemma, if we now take $f$ to be continuously differentiable, then $f'(a)>0$ means $f'(x)>0$ for some neighborhood of $a$. Now given any $x<y$ in this neighborhood, we have by the mean value theorem $f\left(y\right)-f\left(x\right = f'\left(z\right) \left(y-x\right) > 0 $ so that $f$ is increasing on this interval.


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}