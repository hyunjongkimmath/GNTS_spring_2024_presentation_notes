---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# 

---

- Written by: [Hyun Jong Kim](https://sites.google.com/wisc.edu/hyunjongkim?pli=1)
- Created: 2/2/2024
- Last updated: 2/4/2024

These are notes for my [[_index_GNTS_spring_2024|fall 2022 GNTS presentation notes]] on Tuesday, 2/6/2023.

I would greatly appreciate comments and corrections to these notes; please send such suggestions to me at `hyunjong<dot>kim<at>math<dot>wisc<dot>edu` or to my latest email address.

---

> [!Disclaimer]
> You might find it useful to use [Obsidian.md](https://obsidian.md/) if you are reading this as a Markdown file so that you can use the internal links in these notes. However, I may or may not make other notes that this note links to publicly available, so such links may be useless to you. Nevertheless, reading this as a Markdown file on Obsidian.md (alongside as a pdf file) could supplement your reading experience.

---

> [!Title]
> A Zoo of $L$-functions

> [!Abstract]
> I will talk about some different kinds of $L$-functions (and zeta functions) and maybe some problems surrounding them

---


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



# 3. Hecke $L$-function of a Hecke character of a number field
Reference: Bump, Chapter 1, Section 5

> [!Definition]
> Let $K$ be a number field and let $\chi: I_\mathfrak{m} \to \mathbf{C}^\times$[^2] be a Hecke character of weight $\xi_\infty$ for the modulus $\mathfrak{m}$ of $K$, where $\xi_\infty: P_\mathfrak{m} \to \mathbf{C}^\times$ is a (unitary) character[^1].
> The Hecke $L$-function of $\chi$ is
> $$L(\chi, s)=\sum_{\mathfrak{a}} \chi(\mathfrak{a})(N \mathfrak{a})^{-s}=\prod_{\mathfrak{p}}\left(1-\chi(\mathfrak{p})(N \mathfrak{p})^{-s}\right)^{-1}$$ 

[^1]: Of more technically speaking, induced from a unitary character $K^\times / \mathbf{Q}^\times \to \mathbf{C}^\times$ such that $U_\mathfrak{m} \subset \ker \xi_\infty$[^3]
[^2]: ![[bump_et_al_ilp_notation_I_m_group_of_fractional_ideals_coprime_to_a_modulus]]
[^3]: ![[bump_et_al_ilp_notation_U_m_group_of_units_of_P_m]]

For the trivial character $\chi = \chi_0$, the Hecke $L$-function is the Dedekind zeta function, i.e. $L(\chi_0,s) = \zeta_K(s)$.

Hecke characters [[bump_et_al_ilp_5.8 Theorem|have]] a functional equation and an analytic continuation as entire functions.

# 4. $L$-function of an extension of number fields

Reference: Bump et al, Chapter 1, Section 5
[[bump_et_al_ilp_page_12]]

Let $E/K$ be an abelian extension of number fields

> [!Definition]
> Let $E/K$ be an abelian extension of number fields with Galois group $G$. For $\rho \in \hat{G}$ (i.e. $\rho: G \to \mathbb{C}$) Define the $L$-function
> $$L(\rho,s) = \prod_{\mathfrak{p} \text{ prime of } K} (1-\rho(\sigma_\mathfrak{p})(N_\mathfrak{p})^{-s})^{-1}$$
> where $\rho(\sigma_\mathfrak{p})$ is the image of the Frobenius element by the Galois representation induced by $\rho$ in $\mathbf{C}^{I_\mathfrak{p}}$.

[[bump_et_al_ilp_5.9 Theorem]]

> [!Theorem] (Artin)
> Let $K$ be a number field, $E / K$ a finite abelian extension with Galois group $G$, let $\rho: G \rightarrow \mathrm{C}^{\times}$ be a Galois character and $L(\rho, s)$ the associated $L$-function.
> 
> Then there exists a unique primitive Hecke character $\chi$ of $K$, of modulus $\mathrm{m}$ such that
> $$ L(\rho, s)=L(\chi, s) . $$

When $K = \mathbb{Q}$, we have a theorem that yields the Kronecker-Weber theorem (which states that all abelian extensions of $K$ are subfields of cyclotomic fields).


# 5. Artin $L$-function of a global Galois representation (of a number field)

Reference: Gabor Wiese's notes "Galois Representations"

[[wiese_gr_1.4.1 Definition]]

> [!Definition]
> Let $K$ be a number field, and let $\rho: G_K \to \operatorname{GL}_n(\mathbb{C})$ be a Galois representation (i.e. an Artin representation). Define the $L$-function
> $$L(\rho,s) = \prod_{\mathfrak{p}} \frac{1}{\operatorname{char poly} (\operatorname{Frob}_\mathfrak{p})(\rho) (N(\mathfrak{p})^{-s})} $$

One can also more generally define a "partial $L$-function" for representations over topological fields, assuming that the characteristic polynomial of Frobenius are in $\overline{\mathbb{Q}}[X]$.

This is a generalization of 4, which only discussed Galois characters.

> [!Conjecture] 
> (Artin)
> If $\rho$ is a non-trivial Artin representation, then $L(\rho,s)$ has a holomorphic continuation to the whole complex plane.

^eede09

We know that $L(\rho,s)$ has a functional equation and hence a meromorphic continuation.

See also Silverman's "Advanced Topics in the Arithmetic of Elliptic curves", Chapter II, Section 10 for a discussion on the special case of elliptic curves



# 6. Zeta function of a nice variety over a finite field

Reference: Poonen's notes "Lectures on Rational points on Curves",  

> [!Definition]
> Given a "nice" variety over a finite field $\mathbb{F}_q$, define
> $$Z_X(T) = \prod_{\text{closed points } P \in X} (1-T^{\deg P})^{-1}$$
> $$\zeta_X(s) = Z_X(q^{-s})$$

By the Weil-conjectures, $Z_X(T)$, which is a priori in $\mathbb{Q}[[T]]$, is in fact in $\mathbb{Q}(T)$. Moreover, $Z_X$ has a functional equation.

More generally, we can define a zeta function for an arbitrary scheme of finite type over $\mathbb{Z}$.

For a nice genus $g$-curve $X$, we have

$$Z_X(T) = \frac{P_1(T)}{(1-T)(1-qT)}$$

for some integer polynomial $P_1(T)$ of the form $1 + a_1 T + a_2 T^2 + \cdots + a_gT^g + qa_{g-1} T^{g+1} + q^2 a_{g-2} T^{g+2} + \cdots + q^g T^{2g}$.


For an elliptic curve $E/\mathbb{F}_q$, we have $Z_E(E, T) = (1-a T + pT^2)$, where $a$ is the "trace of Frobenius" satisfying $a = q + 1 - \# E(\mathbb{F}_q)$.

# Hasse-Weil zeta function for nice varieties over number fields (5 mixed with 6ish for elliptic curves)

Reference: Silverman's "Advanced Topics in the Arithmetic of Elliptic curves", Chapter II, Section 10

Now given $K/\mathbb{Q}$ a number field and let $E/L$ be an elliptic curve. For each prime $\mathfrak{p}$ of $K$, define the <b style="border-width:1px;border-style:solid;padding:3px" definition="">local $L$-series of $E$ at $\mathfrak{p}$</b> by

$$ L_\mathfrak{p}(E/K, T) = \begin{cases} Z_{E/\mathbb{F}_\mathfrak{p}}(T) &\text{if } E \text{ has good reduction at } \mathfrak{p} \\ 1-T &\text{if } E \text{ has split multiplicative reduction at } \mathfrak{p} \\ 1+T &\text{if } E \text{ has nonsplit multiplicative reduction at } \mathfrak{p} \\  1 &\text{if } E \text{ has additive reduction at } \mathfrak{p} \end{cases}$$

where $\mathbb{F}_\mathfrak{p}$ is the residue field of $\mathfrak{p}$ and define the <b style="border-width:1px;border-style:solid;padding:3px" definition="">global $L$-series of $E$</b> by

$$L(E/K, s) = \prod_{\mathfrak{p}} L_\mathfrak{p}(E/K, \# \mathbb{F}_\mathfrak{p}^{-s})^{-1}$$

This is an example of Artin $L$-function of a global Galois representation. Also, these ideas can be generalized to algebraic varieties $V$ over number fields $K$.

Whether $L(E/K, s)$ has a functional equation[^12] is generally not known. However, by the modularity theorem, which [[#^c19c55|shows that]] $L(E/\mathbb{Q},s) = L(f,s)$ for some newform $f$, we can conclude that $L(E/\mathbb{Q},s)$ has a functional equation because $L(f,s)$ does. Deuring also showed that a CM elliptic curve $E/K$ has an $L$-function that is expressible either as the $L$-function of a Grössencharacter or the product of two such characters. A Grössencharacter has a functional equation, so $L(E/K,s)$ has a functional equation if $E$ has CM.

^c7b793

[^12]: Do not confuse the following questions:
1. whether the $L$-function of a nice variety over a number field has a functional equation
2. whether the zeta function of a nice variety over a finite field has a functional equation

So the following type of question is still quite open:

> [!Conjecture]
> $L(E/K,s)$ has a functional equation when $K$ is a general number field (and $E/K$ is not a CM elliptic curve)

Moreover, Artin's holomorphy conjecture, [[#^eede09|which is stated above]], states that $L(E/K,s)$ has a holomorphic continuation to the whole complex plane.




# 6'. $\mathbb{A}^1$-enriched logarithmic zeta function

Reference: Bilu, Ho, Srinivasan, Vogt, and Wickelgren's paper "Quadratic enrichment of the logarithmic derivative of the zeta function"

> Let $X$ be a smooth, proper variety over a field $k$. Let $\varphi: X \to X$ be an endomorphism. The <b style="border-width:1px;border-style:solid;padding:3px" definition="">$\mathbb{A}^1$-logarithmic zeta function of $(X, \varphi)$</b> is defined by
> $$\operatorname{dlog} \zeta_{X,\varphi}^{\mathbb{A}^1} := \sum \operatorname{Tr}(\varphi^m) t^{m-1} \in \operatorname{GW}(k)[[t]]$$

The motivation for this definition[^4] is to generalize the classical zeta function $\zeta_X(T)$ towards $\mathbb{A}^1$-enumerative geometry:  when $k = \mathbb{F}_q$ and $\varphi$ is the (geometric) Frobenius endomorphism on $X$, we have

[^4]: The logarithmic derivative of the zeta function is used instead of the zeta function itself because the question of rationality for the $\mathbb{A}^1$-logarithmic zeta function becomes difficult to ask because the Grothendieck-Witt ring in general has torsion elements.

$$\zeta_X(T) = \operatorname{exp}\left( \sum_{m \geq 1} \frac{|X(\mathbb{F}_{q^m})|}{m} T^m \right),$$

so 

$$\operatorname{dlog} \zeta_X(T) := \frac{d}{dT} \log \zeta_X(T) = \sum_{m \geq 1} |X(\mathbb{F}_{q^m})| T^{m-1}.$$

Moreover, when $\varphi$ is the Frobenius endomorphism, $\operatorname{Tr}(\varphi^m)$ is an "$\mathbb{A}^1$-enriched version of $|X(\mathbb{F}_{q^m})|$", where counting is done not with integers, but with elements of the Grothndieck-Witt ring $\operatorname{GW}(k)$ whose elements of generated by nondegenerate symmetric bilinear forms on finite dimension $k$-vector spaces[^5].

[^5]:  Moreover, taking the ranks of these vector spaces should in principle return any "classical" count, i.e. counts with familiar numbers.

One can define appropriately a notion of "$\operatorname{dlog}$-rationality" for the power series $\operatorname{dlog} \zeta_{X,\varphi}^{\mathbb{A}^1}$. It turns out that there is a class of schemes (smooth projective schemes over $k$ with "cellular structure") for which $\operatorname{dlog} \zeta_{X,\varphi}^{\mathbb{A}^1}$ is dlog-rational. There are also schemes, such as some elliptic curves, for which $\operatorname{dlog} \zeta_{X,\varphi}^{\mathbb{A}^1}$ is not dlog-rational.

The functional equation has been verified for $\operatorname{dlog}_{\mathbb{P}^n}^{\mathbb{A}^1}(T)$ with the Frobenius endomorphism.

# 7. $L$-function of a modular form 

Reference: Diamond, Shurman, Chapter 5 Section 9

> [!Definition]
> Given a weight $k$-modular form $f$ for $\Gamma_1(N)$, i.e. $f \in \mathcal{M}_k(\Gamma_1(N))$, write its fourier expansion by
> $$f(\tau) = \sum_{n=0}^\infty a_n q^n$$
> where $q = e^{2\pi i \tau}$.
> Its <b style="border-width:1px;border-style:solid;padding:3px" definition="">$L$-function</b> is defined by the Dirichlet series
> $$L(s,f) = \sum_{n=1}^\infty a_n n^{-s}.$$

Whenever $f \in \mathcal{S}_k(\Gamma_1(N))^{\pm}$, there is a functional equation for $L(s,f)$ and hence $L(s,f)$ has an analytic continuation to the complex plane.

The following fact addresses whether $L(s,f)$ has an Euler product expansion
> [!Theorem]
> The following are equivalent for $f \in \mathcal{M}_k(\Gamma_1(N))$:
> - $f$ is a normalized eigenform, i.e. it is a eigenvector for all Hecke operators $T_n$ and $\langle n \rangle$ such that $a_1 = 1$.
> - $L(s,f)$ has an Euler product expansion
> $$ L(s, f)=\prod_{p}\left(1-a_{p} p^{-s}+\chi(p) p^{k-1-2 s}\right)^{-1} $$

Also, given $f \in \mathcal{M}_k(N,\chi)$[^6] for a Dirichlet character $\chi$ modulo $N$, $f$ is a normalized eigenform if and only if we have the recursive relations:

[^6]: ![[diamond_shurman_notation_M_k_N_chi]]; $d_\gamma$ is denotes the lower right entry of $\gamma \in \Gamma_0(N)$.

1. $a_{1}(f)=1$,
2. $a_{p^{r}}(f)=a_{p}(f) a_{p^{r-1}}(f)-\chi(p) p^{k-1} a_{p^{r-2}}(f)$ for all $p$ prime and $r \geq 2$,
3. $a_{m n}(f)=a_{m}(f) a_{n}(f)$ when $(m, n)=1$.

For elliptic curves over $E/\mathbb{Q}$, we have the very same recursive relations for the traces $a_{p^r}$ of Frobenius for $E/\mathbb{F}_{p^r}$ when $p$ is a prime of good reduction.

In fact, one can say more:

> [!Theorem]
> (Modularity theorem, "version $L$")
> Let $E/\mathbb{Q}$ be an elliptic curve with conductor $N_E$. Then for some newform[^7] $f \in \mathcal{S}_2(\Gamma_0(N_E))$,
> $L(s,f) = L(s,E)$[^9]

^c19c55

[^7]: A newform is a normalized eigenform in $\mathcal{S}_k(\Gamma_1(N))^{\text{new}}$[^8]
[^8]: ![[diamond_shurman_notation_S_k_Gamma_1_N_new_space_of_newforms]]
[^9]: Here $L(s,E)$ is the global $L$-series $L(E/\mathbb{Q}, s)$ as defined in [[#5 mixed with 6ish for elliptic curves]]



[[#^c7b793|As mentioned above]], this modularity theorem allows us to conclude that $L(s,E)$ has a functional equation and thus has an analytic continuation.


# 7'. $L$-function of a newform by getting an Artin $L$-function from an abelian variety constructed from the newform


Given a newform $f \in \mathcal{S}_2(\Gamma_1(M_f))$ at a level $M_f$, one can construct an abelian variety

$$A_f = J_1(M_f) / I_f J_1(M_f)$$

Here, 
- $J_1(M_f)$ is the Jacobian of $X_1(M_f)$,
- there is an action of the (level $M_f$) "Hecke algebra" $\mathbb{T}_\mathbb{Z}$[^10] on $J_1(M_f)$ ^696c00
- $I_f$ denotes the kernel of the homomorphism $\mathbb{T}_\mathbb{Z} \to \mathbb{C}$  given by sending $T \in \mathbb{T}_\mathbb{Z}$ to the eigenvalue $\lambda_f(T)$ of $T$ on $f$, i.e. 

$$T_f = \lambda_f(T) f$$

and 

$$I_f = \{T \in \mathbb{T}_\mathbb{Z}: \lambda_f(T) = 0\}.$$

[^10]: ![[diamond_shurman_notation_T_Z_hecke_algebra]]

> [!Fact] 
> (See Diamond, Shurman Lemma 9.5.3)
> Let $\chi$ be a Dirichlet character modulo $N$. Let $f \in \mathcal{S}_2(N,\chi)$ be a normalized eigenform. Then $V_\ell(A_f) := T_\ell(A_f) \otimes_{\mathbb{Z}_\ell} \mathbb{Q}_\ell$ is a free module of rank $2$ over $\mathbb{K}_f \otimes_\mathbb{Q} \mathbb{Q}_\ell$ where $\mathbb{K}_f$ is the number field generated over $\mathbb{Q}$ by the Fourier coefficients $a_n$ of $f$[^11].

[^11]: There turns out to be an isomorphism $\mathbb{T}_\mathbb{Z}/I_f \xrightarrow{\sim} \mathcal{O}_f  = \mathbb{Z}[\{a_n: n \in \mathbb{Z}^+\}]$. Moreover, as [[#^696c00|noted above]], $\mathbb{T}_\mathbb{Z} / I_f$ acts on $A_f$, and hence $\mathcal{O}_f$ acts on $T_\ell(A_f)$ as well.

Now take a look at its $\mathbb{Q}_\ell$-Galois representation of $G_\mathbb{Q}$ acting on $V_\ell(A_f) \cong (K_f \otimes_\mathbb{Q} \mathbb{Q}_\ell)^2$. Note that $K_f \otimes_\mathbb{Q} \mathbb{Q}_\ell$ decomposes in the form $\prod_{\lambda \mid \ell} \mathbb{K}_{f,\lambda}$ where the product is over primes $\lambda$ of $\mathbb{K}_f$ lying over $\ell$, so by projective, for each $\lambda$ we get a $2$-dimensional representation

$$ \rho_{f, \lambda}: G_{\mathbb{Q}} \longrightarrow \mathrm{GL}_{2}\left(\mathbb{K}_{f, \lambda}\right) $$

such a representation is called a <b style="border-width:1px;border-style:solid;padding:3px" definition="">modular representation</b> and it has its own [[#5. Artin $L$-function of a global Galois representation (of a number field)|Artin $L$-function]]



# Many forms of the modularity theorem

Above, we say the following modularity theorem:

![[#^c19c55]]

There are also many other formulations of the modularity theorem, all taken from Diamond and Shurman:

Ther following is a formulation that says that the $\ell$-adic Galois representation of an elliptic curve over $\mathbb{Q}$ equals a representation of some newform:

> [!Theorem]
> (Modularity theorem, "version $R$")
> Let $E$ be an elliptic curve over $\mathbb{\mathbb{Q}}$.  Then $\rho_{E, \ell}$ is a modular representation for some $\ell$, i.e. there is some newform $f \in \mathcal{S}_2(\Gamma_0(M_f))$ such that $\mathbb{K}_{f,\lambda} = \mathbb{Q}_\ell$ for some maximal ideal $\lambda$ of $\mathcal{O}_{\mathbb{K}_f}$ lying over $\ell$ such that $\rho_{f,\lambda}$ is equivalent to $\rho_{E,\ell}$.

Here is a stronger formulation of the above:

> [!Theorem]
> (Modularity theorem, "strong version $R$")
> Let $E$ be an elliptic curve over $\mathbb{Q}$ with conductor $N$. Then for some newform $f \in \mathcal{S}_{2}\left(\Gamma_{0}(N)\right)$ with number field $\mathbb{K}_{f}=\mathbb{Q}$, $\rho_{f, \lambda} \sim \rho_{E, \ell}$ for all $\ell$



Here is a statement concerning how the traces of Frobenii/Hasse invariants of an elliptic curve over $\mathbb{Q}$ are equal to the Fourier coefficients of some newform:

> [!Theorem]
> (Modularity Theorem, Version $a_{p}$). Let $E$ be an elliptic curve over $\mathbb{Q}$ with conductor $N_{E}$. Then for some newform $f \in \mathcal{S}_{2}\left(\Gamma_{0}\left(N_{E}\right)\right)$, $$ a_{p}(f)=a_{p}(E) \quad \text { for all primes } p $$


Here are some modularity theorem statements for elliptic curves over $\mathbb{Q}$ about how elliptic curves are covered by modular curves.

> [!Theorem]
> (Modularity theorem, "version $X_\mathbb{Q}$")
> Let $E$ be an [[diamond_shurman_Definition 7.1.2|elliptic curve]] over $\mathbb{Q}$. Then for some positive integer $N$ there exists a surjective morphism over $\mathbb{Q}$ of curves over $\mathbb{Q}$ from the modular curve $X_{0}(N)_{\text {alg }}$ to the elliptic curve $E$, $$ X_{0}(N)_{\mathrm{alg}} \longrightarrow E $$
> 
> (Modularity Theorem, "version $\left.A_{\mathbb{Q}}\right.$") Let $E$ be an elliptic curve over $\mathbb{Q}$. Then for some positive integer $N$ and some newform $f \in \mathcal{S}_{2}\left(\Gamma_{0}(N)\right)$ there exists a surjective morphism over $\mathbb{Q}$ of varieties over $\mathbb{Q}$ $$ A_{f, \mathrm{alg}}^{\prime} \longrightarrow E $$
>
> (Modularity Theorem, Version $J_{\mathbb{Q}}$ ). Let $E$ be an elliptic curve over $\mathbb{Q}$. Then for some positive integer $N$ there exists a surjective morphism over $\mathbb{Q}$ of varieties over $\mathbb{Q}$ $$ \mathrm{J}_{0}(N)_{\mathrm{alg}} \longrightarrow E $$
> 

And here are some modularity statements for complex elliptic curves with $j$-invariants over $\mathbb{Q}$:


> [!Theorem]
> (Modularity Theorem, Version $X_\mathbb{C}$)
> Let $E$ be a complex elliptic curve with $j(E) \in \mathbb{Q}$.  Then for some positive integer $N$ there exists a surjective holomorphic homomorphism of compact Riemann surfaces from the modular curve $X_0(N)$ to the elliptic curve $E$, $$ X_{0}(N) \longrightarrow E $$
> 
> (Modularity Theorem, Version $A_\mathbb{C}$)
> Let $E$ be a complex elliptic curve with $j(E) \in \mathbb{Q}$.
> Then for some positive integer $N$ and some newform $f \in \mathcal{S}_{2}\left(\Gamma_{0}(N)\right)$ there exists a surjective holomorphic homomorphism of complex tori $$ A_{f}^{\prime} \longrightarrow E $$ 
>
> (Modularity Theorem, Version $J_\mathbb{C}$) Let $E$ be a complex elliptic curve with $j(E) \in \mathbb{Q}$. Let $J_0(N)$ denotes the Jacobian of $X_0(N)$. Then for some positive integer $N$ there exists a surjective holomorphic homomorphism of complex tori $$ J_{0}(N) \longrightarrow E $$
>
> 



# See Also
- https://en.wikipedia.org/wiki/Category:Zeta_and_L-functions - Lists many Wikipedia articles that have to do with Zeta and $L$-functions.

# Meta
## References

## Citations and Footnotes