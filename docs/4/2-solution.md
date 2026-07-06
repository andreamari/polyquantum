# Solution: the optimal ground-state bound from the first three moments

<!-- Replace author(s) and affiliations(s) below  -->
Michele Minervini\
_Cornell University, Ithaca (NY), USA_.

This note records the answer to the optimization question posed in [Polyquantum 4](1-idea.md), following the discussion in the associated issue. It only writes down the formula and the argument for its optimality; the underlying construction is present in earlier literature (see the last section).

## Result

Let $|\psi\rangle$ be a normalized state, $H$ a Hamiltonian with ground-state energy $E_0$, and

$$ \mu_1 = \langle H \rangle, \qquad \mu_2 = \langle (H-\mu_1)^2 \rangle > 0, \qquad \mu_3 = \langle (H-\mu_1)^3 \rangle .$$

The optimal (smallest valid) upper bound on $E_0$ expressible as a function of the first three moments is

$$ f^\star(\mu_1,\mu_2,\mu_3) = \mu_1 + \frac{\mu_3}{2\mu_2} - \frac{1}{2}\sqrt{\frac{\mu_3^2}{\mu_2^2} + 4\mu_2} . $$

It satisfies $E_0 \le f^\star < \mu_1$ for every state with $\mu_2>0$, so it always strictly improves on the plain variational bound. For a symmetric energy distribution ($\mu_3=0$) it reduces to

$$ f^\star = \mu_1 - \sqrt{\mu_2} ,$$

which answers (and slightly tightens) the guess $\mu_1 - \sqrt{\mu_2}/2$ made in the original issue.

## Where the formula comes from

$f^\star$ is the smallest eigenvalue of $H$ projected onto the two-dimensional Krylov space $\mathcal K = \mathrm{span}\\{|\psi\rangle, H|\psi\rangle\\}$. In terms of the raw moments $m_j=\langle H^j\rangle$ this is the smallest root $\lambda$ of the $2\times 2$ generalized eigenvalue problem

$$ \det\left( \begin{pmatrix} m_1 & m_2 \\\\ m_2 & m_3 \end{pmatrix} - \lambda \begin{pmatrix} 1 & m_1 \\\\ m_1 & m_2 \end{pmatrix} \right) = 0 ,$$

where the two matrices are the projections of $H$ and of the identity (the overlap matrix) onto $\mathcal K$. Solving the quadratic and rewriting in central moments gives the closed form above.

## Optimality

As summarized by A. Mari in the issue discussion, optimality follows from two facts.

**(1) Validity: no admissible instance has $E_0 > f^\star$.** For any state $\chi$ in the full Hilbert space $\mathcal H \supseteq \mathcal K$ we have $\langle \chi | H | \chi \rangle \ge E_0$, so

$$ E_0 = \min_{\chi \in \mathcal H} \langle \chi | H | \chi \rangle \; \le \; \min_{\chi \in \mathcal K} \langle \chi | H | \chi \rangle = f^\star .$$

This is just the Rayleigh-Ritz variational principle restricted to $\mathcal K$, and it only uses the three measured moments.

**(2) Achievability: $f^\star$ is attained, so no smaller bound can be valid.** For any target $(\mu_1, \mu_2>0, \mu_3)$ there is a two-level instance whose ground energy equals $f^\star$. Explicitly, with

$$ u = \tfrac{1}{2}\Big(\sqrt{s^2+4\mu_2} - s\Big), \qquad v = \tfrac{1}{2}\Big(\sqrt{s^2+4\mu_2} + s\Big), \qquad s = \frac{\mu_3}{\mu_2}, $$

take $H = \mathrm{diag}(\mu_1-u,\; \mu_1+v)$ and $|\psi\rangle = \sqrt{p}\,|0\rangle + \sqrt{1-p}\,|1\rangle$ with $p = v/(u+v)$. One checks directly that this state has exactly the moments $(\mu_1,\mu_2,\mu_3)$, and its ground energy is $E_0 = \mu_1 - u = f^\star$. Another way to see it: for a two-level system $\mathcal K$ is the whole Hilbert space, so the Krylov diagonalization is exact.

Given (1) and (2), any function $g(\mu_1,\mu_2,\mu_3)$ that is a valid upper bound for **all** states and Hamiltonians must satisfy $g \ge E_0 = f^\star$ on the instances of point (2), for every moment triple. Hence $g \ge f^\star$ everywhere and $f^\star$ is the tightest possible bound.

A complementary, purely classical way to phrase the same thing: given only the first three moments, the highest that the lowest point of the energy distribution can sit is exactly $f^\star$, and the two-point distribution of point (2) is the extremal case. This is a known corner of the truncated moment problem / Gauss quadrature theory[^4].

## More moments

The same construction extends: from the moments $m_1,\dots,m_{2k-1}$ one builds the $k\times k$ version of the pencil above, and its smallest eigenvalue $f^\star_k$ (the smallest Ritz value of the order-$k$ Krylov space) is the optimal bound from that data, by the same two facts. The bounds improve monotonically, $E_0 \le \cdots \le f^\star_2 \le f^\star_1 = \mu_1$. This quantity is the one computed by the analytic-Lanczos bound of Hollenberg and Witte[^1] and, on quantum hardware, by the "quantum computed moments" method of Vallury et al.[^2]; the variance-only loss of Ref.[^3] corresponds to stopping at two moments, which (consistently with the note in the original issue) cannot improve on $\mu_1$ in the worst case. So the bound itself predates this note; what is recorded here is the explicit $k=2$ closed form and the optimality statement.

## References

[^1]: L. C. L. Hollenberg, N. S. Witte, _Analytic solution for the ground-state energy of the extensive many-body problem_, Phys. Rev. B 54, 16309 (1996), [arXiv:cond-mat/9602091](https://arxiv.org/abs/cond-mat/9602091).

[^2]: H. J. Vallury, M. A. Jones, C. D. Hill, L. C. L. Hollenberg, _Quantum computed moments correction to variational estimates_, [Quantum 4, 373 (2020)](https://quantum-journal.org/papers/q-2020-12-15-373/), [arXiv:2009.13140](https://arxiv.org/abs/2009.13140).

[^3]: D-B Zhang, Z-H Yuan, T. Yin, _Variational quantum eigensolvers by variance minimization_, [arXiv:2006.15781](https://arxiv.org/abs/2006.15781).

[^4]: G. H. Golub, G. Meurant, _Matrices, Moments and Quadrature with Applications_, Princeton University Press (2010).

## Link to original issue

- Link to the original issue andreamari/polyquantum#4.

## How to cite this document

Short reference: _Polyquantum 4.2_.\
Full reference: _M. Minervini, Solution: the optimal ground-state bound from the first three moments, Polyquantum 4.2, (2026)_.
