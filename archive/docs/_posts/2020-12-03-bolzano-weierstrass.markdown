---
layout: posts
title:  "The Bolzano-Weierstrass Theorem"
date:   2020-12-03
categories: jekyll update
usemathjax: true
tags: analysis compact sequence cauchy bolzano weierstrass theorem
---

In this post, I am taking notes on the Bolzano-Weierstrass theorem, which asserts the existence of a convergent subsequence for any bounded sequence in $\mathbb{R}^n$. This can be reformulated into an equivalent statement about sequential compactness and closedness and boundedness, which is analogous to the Heine-Borel theorem. These statements may be generalizable to other topological spaces (?).



### Bolzano-Weierstrass in Euclidean Space
<div class="theorem" text="Bolzano-Weierstrass">
    Any bounded sequence in $\mathbb{R}$ has a convergent subsequence.
</div>
<p>
    One version of the proof involves showing that any (not necessarily bounded) sequence has a monotone subsequence, and then applying the monotone convergence theorem to this subsequence to prove existence. The alternate proof involves taking the interval containing the sequence and bisecting it repeatedly, constructing a sequence of nested intervals, each of which contains infinitely many points. Then we can take a single point from each interval to obtain a sequence. This sequence is certainly Cauchy since the intervals are nested and shrink by a factor of 2. Since $\mathbb{R}$ is complete, the sequence converges (instead of using completeness, we can show that it converges to $x$ in the intersection of thesse intervals).
</p>
<p>
    A similar claim can be made more generally for sequences in any Euclidean space:
</p>
<div class="theorem" text="Bolzano-Weierstrass">
    Any bounded sequence in $\mathbb{R}^n$ has a convergent subsequence.
</div>
<p>
    How does this translate into a statement about compactness? In the special case of Euclidean space $\mathbb{R}^n$, we know from the Heine-Borel theorem that the compact sets are precisely the closed and bounded sets. Thus, in this space, the Bolzano-Weierstrass theorem shows:
</p>
<div class="corollary">
    Any sequence in a closed and bounded subset $S\subset \mathbb{R}^n$ has a convergent subsequence in $S$.
</div>
<p>
    This is easy to see, since boundedness implies that the sequence converges in $\mathbb{R}^n$, and closedness of $S$ implies that the subsequential limit is in $S$. Sets in which every sequence has a convergent subsequence in the set are called <b>sequentially compact sets</b>; hence, this corollary shows that closed and bounded subsets of $\mathbb{R}^n$ are sequentially compact, i.e., that compact subsets of $\mathbb{R}^n$ are sequentially compact.
</p>
<p>
    Conversely, let $S\subset \mathbb{R}^n$ be a sequentially compact set. We want to show that it is compact. Let $\left\{U_i\right\}$ be an open cover of $S$. Then for every $i$ there is an $x_i \in U_i \subset S$, hence we have a sequence $\left\{x_i\right\}\subset S$. Since $S$ is sequentially compact, we have a convergent subsequence $x_{i'}\rightarrow x\in S$...
</p>
<p>
This above argument sketches the proof of the following theorem:
</p>
<div class="theorem">
In $\mathbb{R}^n$, the sequentially compact sets are exactly the compact sets.
</div>


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}