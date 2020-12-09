---
layout: posts
title:  "The Inverse Function Theorem"
date:   2020-11-30
categories: jekyll update
usemathjax: true
tags: calculus analysis inverse theorem
---

In this post, I am taking notes on the theory of multivariate, vector-valued differentiation as developed by Spivak in *Calculus on Manifolds* (1965). In particular, I walk slowly through Spivak's proof of the inverse function theorem.

### Give Intuition from One Dimension
Recall from our discussion on continuity that if $f'\left(a\right)>0$ and $f'$ is continous on some neighborhood of $a$ (that is, $f$ is continuously differentiable there) then we have $f'\left(x\right)>0$ for all $x$ in a neighborhood $V$ of $a$. This means that $f$ is strictly increasing on $V$, and so it is injective there. That, in turn, means that its inverse, $f^{-1}$, exists and is well-defined on $f\left(V\right)$. (Note: we can either take (*a*) $f'\left(a\right)>0$ and $f \in C^1$, or (*b*) we can take $f'\left(x\right)>0$ on some neighborhood of $a$ directly; then apply the mean-value theorem here to obtain the fact that $f$ is strictly increasing.)

If we picture this situation graphically, on $V$, $f$ has positive slope. We can try to look at $f^{-1}$ by flipping the graph $\left(x,f\left(x\right)\right)$ over the line $y=x$, or by looking at the $y$-axis. Recall that $f'\left(a\right)>0$ means that the slope of the tangent line to the graph of $f$, at $a$, is positive; in other words, we linearly approximate $f$ at $a$ by a line with positive slope. If we consider the graph of the inverse function, the same linear approximation holds at $f\left(a\right)$, but the slope is inverted. The statement of the inverse function theorem for univariate functions makes this precise:

<div class="theorem">
Let $f:\mathbb{R}\rightarrow\mathbb{R}$ be continuously differentiable on a neighborhood of $a$, and assume $f'\left(a\right)\neq 0$. Then $f^{-1}$ is differentiable on a neighborhood $W$ of $f\left(a\right)$ with $$ \left(f^{-1}\right)'\left(y\right) = 1/f'\left(f^{-1}\left(y\right)\right) $$ for $y \in W$.
</div>
<div class="proof">
Assume $f'\left(a\right)>0$. By the above discussion, we know that $f$ is strictly increasing and thus injective on some neighborhood $V$ of $a$. Let $W=f\left(V\right)$, a neighborhood of $f\left(a\right)$. To determine the derivative of $f^{-1}$ at arbitrary $y\in W$, we look at the difference quotient limit
\begin{equation}
\left(f^{-1}\right)'\left(y\right) = \lim_{y'\rightarrow y}\frac{f^{-1}\left(y'\right) - f^{-1}\left(y\right)}{y'-y}
\end{equation}
By injectivity, we have $x',x \in V$ with $f\left(x'\right)=y'$ and $f\left(x\right)=y$, with $x' \neq x$. Since $f$ is continuous, we have the $y'\rightarrow y$ if and only if $x'\rightarrow x$. Then substituting these values, we obtain
\begin{equation}
\frac{f^{-1}\left(y'\right) - f^{-1}\left(y\right)}{y'-y} = \frac{f^{-1}\left(f\left(x'\right)\right) - f^{-1}\left(f\left(x\right)\right)}{f\left(x'\right)-f\left(x\right)} = \frac{x'-x}{f\left(x'\right)-f\left(x\right)} 
\end{equation}
By properties of limits, then, the right-hand side tends to $1/f'\left(x\right)$ as $x'\rightarrow x$, or, equivalently, as $y'\rightarrow y$. Thus we have
\begin{equation}
\left(f^{-1}\right)'\left(y\right) = \lim_{y'\rightarrow y} \frac{f^{-1}\left(y'\right) - f^{-1}\left(y\right)}{y'-y} = \frac{1}{f'\left(f^{-1}\left(y\right)\right)}
\end{equation}
</div>
(see Rudin's *PMA*, Chapter 5 Exercise 2 which asks for this proof.)

This makes a lot of sense. If the function has nonzero derivative at $a$, then near $a$ it is non-constant and strictly increasing (resp. decreasing), so we can invert it. The result is that the inverse itself is differentiable, and that the derivative is related nicely to the derivative of $f$ at $a$. The statement involves not only the points $a$ and $f\left(a\right)$, but all points $x$ and $f\left(x\right)$ on neighborhoods of $a$ and $f\left(a\right)$. These neighborhoods are provided by our assumption of continuous differentiability of $f$.

Note that we may still have $f$ invertible about $a$, but with $f'\left(a\right)=0$. The standard example is $f\left(x\right)=x^3$ at $a=0$. In this case, the inverse function is not differentiable at $b = f\left(0\right)=0$; this would give the derivative of the inverse at $f\left(0\right)$ as $1/0$!

### Set up the general problem
In general, we want to address the invertibility and differentiability of functions $f:\mathbb{R}^n\rightarrow \mathbb{R}^m$. The theorem as stated by Spivak (1965) is 
<div class="theorem">
Let $f:\mathbb{R}^n\rightarrow\mathbb{R}^m$ be continuously differentiable in a neighborhood of $a$, with $\det f'\left(a\right) \neq 0$. Then there are open sets $V$ about $a$ and $W$ about $f\left(a\right)$ so that $f:V\rightarrow W$ has continuous inverse $f^{-1}:W\rightarrow V$ which is differentiable on $W$ and, for $y\in W$, satisfies $$ \left(f^{-1}\right)'\left(y\right) = \left[ f'\left(f^{-1}\left(y\right)\right)\right]^{-1}. $$
</div>
This is clearly the multivariate, vector-valued analogue to the standard theorem above. Here, the determinant of $f'\left(a\right)$ plays the role of the "slope" of the function at $a$, as expected. Continuous differentiability of $f$ is still assumed, and the local neighborhoods $V$ and $W$ are still produced. The result relating the derivatives of $f$ and of $f^{-1}$ is notationally identical to the univariate case; the difference is that the derivative $f'$ being inverted is, as a linear mapping from $\mathbb{R}^n$ to $\mathbb{R}^m$, a matrix --- the Jacobian matrix of $f$ at $f^{-1}\left(y\right)$, written \begin{equation} f'\left(f^{-1}\left(y\right)\right) = Df\left(f^{-1}\left(y\right)\right)\end{equation}




<div class="proof">
    <h4>Step 1: Reduce the Jacobian to the identity.</h4>
    <p>
    We will interchangeably write $\lambda = Df\left(a\right)$, where we assume $\det Df\left(a\right) \neq 0$. Thus, the inverse $\lambda^{-1}$ exists and we have $\lambda^{-1} \circ f: \mathbb{R}^n\rightarrow\mathbb{R}^n$. Then
    \begin{align}
    D\left(\lambda^{-1} \circ f\right)\left(a\right) & = D\left(\lambda^{-1}\right)\left(f\left(a\right)\right) \circ Df\left(a\right) \\
    & = \lambda^{-1} \circ Df\left(a\right) \\
    & = a
    \end{align}
    so that $D\left(\lambda^{-1} \circ f\right)=I$ is the identity map on $\mathbb{R}^n$. Spivak enigmatically states: "If the theorem is true for $\lambda^{-1}\circ f$, it is clearly true for $f$."
    </p><p>
    To prove this, assume that the theorem is true for $g = \lambda^{-1} \circ f$; that is, assume that there exist the open sets $V$ and $W$ about $a$ and $g\left(a\right)$, respectively, so that $g$ is invertible on $V$ and $g^{-1}$ differentiable at every $y\in W$, with $$ \left(g^{-1}\right)'\left(y\right) = \left[g'\left(g^{-1}\left(y\right)\right) \right]^{-1}$$ By the definition of inverse, we have, on $V$, $$ I = g^{-1} \circ g = g^{-1} \circ \lambda^{-1} \circ f = \left(g^{-1} \circ \lambda^{-1}\right) \circ f $$ which tells us that $f^{-1} = g^{-1} \circ \lambda^{-1}$ is the inverse function for $f$ on $\lambda\left(W\right)$. Further, this inverse is clearly continuous as a composition of a linear function with a differentiable one.
    </p><p>
    Lastly, we must show that the derivative relationship is satisfied by this $f^{-1}$. This amounts to an application of the chain rule. Let $z\in \lambda\left(W\right)$; then,
    \begin{align}
        \left(f^{-1}\right)'\left(z\right) & = D\left(g^{-1} \circ \lambda^{-1} \right)\left(z\right) \\
        & = D\left(g^{-1}\right)\left(\lambda^{-1}\left(z\right)\right) \circ D\left(\lambda^{-1}\right)\left(z\right) \\ 
        & = \left[ g'\left( g^{-1}\left(\lambda^{-1}\left(z\right)\right)\right) \right]^{-1} \circ \lambda^{-1} \\
        & = \left[ g'\left( g^{-1}\circ \lambda^{-1}\left(z\right)\right) \right]^{-1} \circ \lambda^{-1} \\
        & = \left[ g'\left( f^{-1}\left(z\right)\right) \right]^{-1} \circ \lambda^{-1} \\
        & = \left[ \lambda \circ g'\left( f^{-1}\left(z\right)\right) \right]^{-1}\\
        & = \left[ f'\left( f^{-1}\left(z\right)\right) \right]^{-1}\\
    \end{align} 
    where in the last line we used the fact that since $g = \lambda^{-1} \circ f$, $\lambda \circ g = f$ and by the chain rule we have $$ f' = \lambda \circ g'.$$
    </p>
    <p> 
    Thus we have showed that the theorem holds for $f$ if it also holds for $Df\left(a\right)\circ f$, since we have the identity derivative, $D\left(Df\left(a\right)\circ f\right) = I$. Because of this observation, the rest of the proof is restricted to functions $f$ which have identity derivative: in the general case, we may take $f\mapsto Df\left(a\right)\circ f$, which has the identity Jacobian, apply the results, and be guaranteed that they hold for the function $f$.
    </p>
    <p>
    The next steps seek the desired neighborhoods $V$ and $W$ on which $f$ is invertible and has differentiable inverse.
    </p>


    <h4>Step 2: Find a suitable neighborhood in the domain.</h4>
    <p>
    This step is the analogue of monotonicity. Assume $f\left(h+a\right) = f\left(a\right)$ for some $h\in\mathbb{R}^n$. Then $$ \lim_{h\rightarrow 0} \frac{\left| f\left(a+h\right) - f\left(a\right) - \lambda\left(h\right) \right|}{\left|h\right|} = \lim_{h\rightarrow 0} \frac{\left|h\right|}{\left|h\right|} = 1 \neq 0 $$ and so differentiation at $a$ does not hold where $f\left(a+h\right)=f\left(a\right)$. Hence, there is some neighborhood $U$ about $a$ with $f\left(x\right) \neq f\left(a\right)$ for all $x\in U\setminus \left\{a\right\}$. Spivak takes $U$ to be a closed rectangle. (How? We know there must be an open neighborhood of $a$. Take a closed rectangle inside of that open neighborhood. This is possible because of the metric structure on $\mathbb{R}^n$.)
    </p>

    <p>
    Further, since $f$ is continuously differentiable, and $\det Df\left(a\right) \neq 0$, there is a neighborhood of $a$ with $\det Df\left(x\right) \neq 0$ on it. Take $U$ to be a closed rectangle also within this neighborhood. Even further, since the partial derivatives are continuous at $a$ (why?), we can take $U$ small enough so that $$ \left| D_jf^i\left(x\right) - D_jf^i \left(a\right)\right| < 1/2n^2, $$ the reason for which will become clear.
    </p>
    <p>
    Consider $g\left(x\right) = f\left(x\right) - x$, and let $x_1, x_2 \in U$. Apply Spivak's Lemma 2-10 to show that $$ \left|g\left(x_1\right) - g\left(x_2\right) \right| = \left|\left(f\left(x_1\right) - x_1\right) - \left(f\left(x_2\right) + x_2 \right)\right| \leq \frac{1}{2}\left|x_1 -x_2\right| $$ Apply the reverse triangle inequality to obtain a bound: $$ \left|x_1 - x_2 \right| \leq 2\left|f\left(x_1\right)-f\left(x_2\right)\right|. $$ What this tells us is that for any two distinct points $x_1,x_2 \in U$, we have $f\left(x_1\right) \neq f\left(x_2\right)$, so that $f$ is injective on $U$, and thus invertible. Note that all of this has been similar to the proof of the similar result in the one-dimensional case.
    </p>
    <p>
    One last note is that $U$ is not open, and is not quite the set $V$ that we are looking for. In the next section, we will identify our $W$ and construct our $V$ from the interior of $U$.
    </p>

    <h4>Step 3: Find a suitable region in the codomain.</h4>
    <p>
    The set $U$ is a closed rectangle, and its boundary $\partial U$ is a closed and bounded subset of $\mathbb{R}^n$, and is thus compact. Since $f$ is continuous on $U$, the image $f\left(\partial U\right)$ is also compact, and we know that $f\left(x\right) \neq f\left(a\right)$ for any $x$ on $\partial U$. The image values $f\left(x\right)$ and $f\left(a\right)$ are vectors in $\mathbb{R}^m$, and so we must speak of their differences in vector magnitude: there is a number $d>0$ so that $\left|f\left(x\right) - f\left(a\right)\right| \geq d$ for all $x\in \partial U$. We want to ensure that our region does not intersect $f\left(\partial U\right)$; we can take $$ W = \left\{ y\, : \, \left|y-f\left(a\right)\right| < \frac{d}{2}\right\} $$ Clearly $\left|y-f\left(a\right)\right| < \left|y-f\left(x\right)\right|$ for all $y\in W$.
    </p>
    <p>
    Why is this neighborhood $W$ special? We will show that for every $y\in W$ there is a unique $x\in \text{int}\,U$ with $f\left(x\right)=y$, i.e., that $f$ is a bijection from $\text{int}\,U$ to $W$.
    </p>
    <p>
        How to show this? Consider for fixed $y\in W$ the function $g:U\rightarrow \mathbb{R}$ given by $$ g\left(x\right) = \left|y - f\left(x\right)\right|^2. $$ It is certainly continuous and defined on a compact set, so it attains a minimum on $U$. Assume that this minimum is attained at $x \in \partial U$. Then $g\left(a\right) < g\left(x\right)$, which is a contradiction of the definition of minimum. Hence, the minimum must be attained at $x \in \text{int}\,U$. Since the minimum occurs on the interior, the partial derivatives must all be zero there: $$ 0 = D_jg\left(x\right) = \sum_{i=1}^n 2\left(y^i - f^i\left(x\right)\right) \cdot D_jf^i\left(x\right) \; \text{for} \; j=1,\ldots,n $$ This is a system of linear equations of the columns of $Df$, and since we know $\det \, Df \neq 0$ on $U$, we must have $y^i - f^i\left(x\right) = 0$, which completes our production of $x$ with $f\left(x\right)=y$. Uniqueness follows from the bound we found in Step 2.
    </p>
    <p>
        In this step, we have constructed a neighborhood $W$ of $f\left(a\right)$ such that for any $y \in W$, there is a unique $x\in \text{int}\, U$ with $f\left(x\right)=y$. This is not a bijection from $U$ to $W$, since we can't be certain that $f\left(U\right)=W$. Rather, we will need to restrict $U$ to just those values which map into $W$. We also need this restricted set to be open. This is done easily: Take $$ V = \left( \text{int}\, U\right)\cap f^{-1}\left(W\right).$$ Then certainly $f$ is a bijection from $V$ to $W$.
    </p>
    
    <h4>Step 4: Show that the derivative relation holds.</h4>
    <p>
        We have found the open neighborhoods of $a$ and $f\left(a\right)$, $V$ and $W$, respectively, upon which $f$ acts as a bijection. It remains to be seen that $f^{-1}$ is indeed differentiable on $W$ and satisfies the derivative condition we know from the univariate case.
    </p>
    <p>
        Let $y$ be an arbitrary point in $W$. Then $y=f\left(x\right)$ for some $x\in V$. We want to take the derivative of $f^{-1}$ at $y$. Accordingly, we will construct the difference quotient, letting $y'\in W$ be another point in $W$, $x'\in V$ mapping to $y'$, and we will take the limit as $y' \rightarrow y$. 
    </p>
    <p>
        Recall that the definition of differentiability of $f$ at $x'$ is equivalent to the existence of the equation $$ f\left(x'\right) = f\left(x\right) + Df\left(x\right)\cdot\left(x'-x\right) + \phi \left(x'-x\right) $$ where $$ \lim_{x'\rightarrow x} \frac{\left| \phi\left(x'-x\right)\right|}{\left|x'-x\right|} =0.$$ We want to show that the same equation holds for the inverse $f^{-1}$. Keeping in mind that $y=f\left(x\right)$, $y'=f\left(x'\right)$, and that $Df\left(x\right)$ is invertible, we can multiply by $Df\left(a\right)^{-1}$ to get
        \begin{align}
            x' & = x + Df\left(a\right)^{-1}\cdot \left(f\left(x'\right)-f\left(x\right)\right) - Df\left(a\right)^{-1}\cdot \phi\left(x'-x\right) \\ 
        \end{align}
        We can use $f^{-1}$ to replace all instances of the variables in $V$ with those in $W$:
        \begin{align}
            f^{-1}\left(y'\right) & = f^{-1}\left(y\right) + Df\left(a\right)^{-1} \cdot \left(y'-y\right) - Df\left(a\right)^{-1}\cdot\phi\left(f^{-1}\left(y'\right)-f^{-1}\left(y\right)\right) \\ 
        \end{align}
        Thus, $f^{-1}$ will be differentiable at $y\in W$ with derivative $Df\left(a\right)^{-1}$ if and only if the last term satisfies $$ \lim_{y'\rightarrow y}\frac{\left| Df\left(a\right)^{-1}\cdot \phi\left(f^{-1}\left(y'\right)-f^{-1}\left(y\right)\right)\right|}{\left|y'-y\right|} = 0$$ Since $Df\left(a\right)$ is a linear function (i.e., a matrix), we know that $$ \left|Df\left(a\right)\cdot h\right| \leq M \left|h\right|$$ where $M$ is a constant involving the entries in the matrix of $Df\left(a\right)$. Thus, we need to show that $$ \lim_{y'\rightarrow y}\frac{\left| \phi\left(f^{-1}\left(y'\right)-f^{-1}\left(y\right)\right)\right|}{\left|y'-y\right|} = 0$$ We do the classic trick of multiplying and dividing by the same (nonzero) quantity: $$ \frac{\left| \phi\left(f^{-1}\left(y'\right)-f^{-1}\left(y\right)\right)\right|}{\left|f^{-1}\left(y'\right)-f^{-1}\left(y\right)\right|} \cdot \frac{\left| f^{-1}\left(y'\right) - f^{-1}\left(y\right) \right|}{\left|y'-y\right|}$$ Take the limit of this as $y'\rightarrow y$. Notice that this means $f^{-1}\left(y'\right)\rightarrow f^{-1}\left(y\right)$ since $f^{-1}$ is continuous (at $y$). The second term does not blow up since our previous bound $$ \left|x_1 - x_2\right| \leq 2\left| f\left(x_1\right) -f\left(x_2\right) \right| $$ for $x_1, x_2 \in U$ can be rewritten in terms of the inverse $f^{-1}$ as $$ \left|f^{-1}\left(y_1\right) - f^{-1}\left(y_2\right)\right| \leq 2\left|y_1 - y_2\right| $$ Thus, the second factor is bounded by 2 in the limit $y'\rightarrow y$. The first term goes to $0$ since $\phi$ was defined to have precisely this property.
    </p>
    <p>
        In conclusion, we have demonstrated the existence of open neighborhoods $V$ and $W$ of $a$ and $f\left(a\right)$, respectively, upon which $f$ acts as a bijection. We have also shown that the inverse of $f$, $f^{-1}$, is differentiable on $W$ with inverse $$ D\left(f^{-1}\right)\left(y\right) = Df\left(f^{-1}\left(x\right)\right)^{-1}. $$
    </p>


<div>





{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}