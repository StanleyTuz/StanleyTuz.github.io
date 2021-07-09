---
layout: posts
title:  "Compactness and the Tychonoff Theorem"
date:   2021-07-09
categories: jekyll update
usemathjax: true
tags: compact topology space tychonoff
---
<p>
    The standard definition of topological compactness is in terms of open covers. There are several equivalent formulations, especially in the case of metric spaces. The Tychonoff theorem, which states that the arbitrary product of compact spaces is compact, can be easily proved using such an alternate formulation which involves intersections of closed subbases. To this end, we will discuss open and closed bases and subbases, the finite intersection property, how compactness can be defined, and the proof of the Tychonoff theorem.
</p>

### Closed Subbases
<p>
    Given a topological space $\left(X,\tau\right)$, a basis for this space is a collection of open sets $\mathcal{B}\subset \tau$ such that every open set can be written as a union of these basic sets. A closed basis is a collection of closed sets whose complements comprise an open basis.  
</p>
<p>
    An open subbasis for the topology is a collection of subsets of $X$ such that the class of all finite intersections of the subbasis elements is a basis for the topology. This subbasis generates the topology in the sense that the topology is the smallest one which contains the subbasis. A closed subbasis is a collection of subsets of $X$ whose complements comprise an open subbasis. As expected, finite unions of closed subbasis elements form a closed base, and this is pretty easily seen.
</p>
<p>
    Why bother with subbases? Subbasis elements need not be open or closed themselves: they are just any old subsets. They are useful in different contexts...
</p>


### The Finite Intersection Property
<div class="definition">
    A class of subsets of a set has the finite intersection property is every finite subclass has non-empty intersection.
</div>
<p>
    The finite intersection property (FIP) may be possessed by a collection of subsets.
</p>
<div class="theorem">
    Topological space $\left(X,\tau\right)$ is compact if and only if every class of closed sets $\left\{ C_i\right\}_{i\in I}$ with the FIP has non-empty total intersection: $$ \cap_{i\in I}C_i \neq \varnothing.$$
</div>
<p>
    In other words, the FIP takes care of the case where the collection of closed sets is finite (FIP works more generally for not just closed sets); this theorem says that compact spaces are those for which we can take a collection of closed sets with FIP and extend the conclusion to the non-finite intersection.
</p>


### Compactness in terms of FIP
<p>

</p>


### The Tychonoff Theorem
<p>

</p>


### Conclusion
<p>

</p>


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}
