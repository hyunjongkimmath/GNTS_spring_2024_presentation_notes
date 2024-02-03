---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# A Zoo of $L$-functions

Speaker: [[kim_hyun_jong]]

Abstract: I will talk about some different kinds of $L$-functions (and zeta functions) and maybe some problems surrounding them


# 0. Riemann zeta function

Reference: Bump et al, "Introduction to the Langlands Program", Chapter 1

$\zeta(s) = \sum_{n=1}^\infty \frac{1}{n^s}$

Facts:
1. Converges absolutely for $\operatorname{Re}(s) > 1$
2. [[bump_et_al_ilp_page_1_2|We have]] Euler product $$\zeta(s) = \prod_p \frac{1}{1-p^{-s}}$$
3. We have functional equation: letting
$$\Lambda(s) = \pi^{-s/2} \Gamma(s/2) \zeta(s),$$
$\Lambda$ is meromorphic (and therefore $\zeta$ is meromorphic) except for simple poles at $s = 0, 1$ and satisfies 
$$\Lambda(1-s) = \Lambda(s)$$

# 1. Dirichlet $L$-functions

Reference: Bump et al, "Introduction to the Langlands Program", Chapter 1
- [[bump_et_al_ilp_3.1 Theorem]]

- Generalize $\zeta$

> [!Definition]
> Let $\chi: \mathbf{Z} \to \mathbf{C}$ be a Dirichlet character modulo $m$. The <b style="border-width:1px;border-style:solid;padding:3px" definition="">Dirichlet $L$-series</b> is defined by
>
> <span style="border-width:1px;border-style:solid;padding:3px" notation="">$$L(s,\chi) = \sum_{n=1}^\infty \frac{\chi(n)}{n^s} = \prod_p (1-\chi(p)p^{-s})^{-1} $$</span>
>
> for $\operatorname{Re} s > 1$

Note that this generalizes $\zeta$ because $L(s,1) = \zeta$.

[[bump_et_al_ilp_3.1 Theorem|Define]] $\Lambda(\chi,s)$ by

$$\Lambda(\chi, s) = \begin{cases} \pi^{-s / 2} \Gamma(s / 2) L(\chi, s) &\text{if } \chi(-1) = 1 \\ \pi^{-(s+1) / 2} \Gamma((s+1) / 2) L(\chi, s) &\text{if } \chi(-1) = -1 \end{cases}$$

[[bump_et_al_ilp_3.1 Theorem|We have]] the functional equation

$$\Lambda(\chi,s) = \varepsilon(\chi) q^{1/2-s} \Lambda(\overline{\chi}, 1-s)$$

($\varepsilon$ is definable with a "Gauss sum" and $\overline{\chi}: (\mathbf{Z}/m\mathbf{Z})^\times \to \mathbf{C}^\times$ is the Dirichlet character mod $m$ "inducing" $\chi$)

Therefore, $L(\chi,s)$ is extendable to a meromorphic function on the complex plane.

# 2. Dedekind zeta functions

Reference: Wikipedia

> [!Definition]
> Let $K$ be an algebraic number field. The <b style="border-width:1px;border-style:solid;padding:3px" definition="">Dedekind zeta function</b> is defined by
> $$\zeta_K(s) = \sum_{I \subseteq \mathcal{O}_K, \text{ nonzero}} \frac{1}{(N_{K/\mathbb{Q}}(I))^s} = \prod_{\mathfrak{p} \subseteq \mathcal{O}_K \text{ prime}} \frac{1}{1-N_{K/\mathbb{Q}}(\mathfrak{p})^{-s}}$$
> for $\operatorname{Re}(s) > 1$.

$N_{K/\mathbb{Q}}(\mathfrak{p})$ equals the size of the residue field of $\mathfrak{p}$.

For $K = \mathbb{Q}$, $\zeta_K(s) = \zeta(s)$.

We have a functional equation and hence an analytic continuation to a meromorphic function.

# 2' Partial Dedekind zeta function

Reference: Drew Sutherland's MIT 18.785 Notes, Lecture 21

> [!Definition]
> Let $K$ be an algebraic number field, and let $S$ be a set of primes of $K$. The <b style="border-width:1px;border-style:solid;padding:3px" definition="">partial Dedekind zeta function associated to $S$</b> is defined by
> $$\zeta_{K,S}(s) = \prod_{\mathfrak{p} \in S} \frac{1}{1-N_{K/\mathbb{Q}}(\mathfrak{p})^{-s}}$$
> for $\operatorname{Re}(s) > 1$.

If $S$ is the set of all primes of $K$, then $\zeta_{K,S} = \zeta_{K}$. 

If $S$ has all but finitely many primes, then $\zeta_{K,S}$ and $\zeta_{K}$ differ by the product of finitely many factors, so $\zeta_{K,S}$ extends to a meromorphic function



# 3. Hecke $L$-fucntion of a number field


# 4. $L$-function of an extension of number fields

Let $E/K$ be an abelian extension of number fields


# 5.0. Hecke $L$-function of a Galois character (of a number field)



# 5. Artin $L$-function of a global Galois representation (of a number field)

Reference: Gabor Wiese's notes "Galois Representations"

> [!Definition]
> Let $K$ be a number field


# Statement of Kronecker-Weber theorem

[[bump_et_al_ilp_5.2 Theorem]]

# 6. Zeta function of a curve over a finite field



# See Also
- https://en.wikipedia.org/wiki/Category:Zeta_and_L-functions - Lists many Wikipedia articles that have to do with Zeta and $L$-functions.

# Meta
## References

## Citations and Footnotes