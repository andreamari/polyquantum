# Variational quantum eigensolver based on high-order moments of the energy
<!-- Replace author(s) and affiliations(s) below  -->
Andrea Mari\
_University of Camerino_  


## Settings

The variational quantum eigensolver is a quantum algorithm in which the classical parameters $\vec \theta$ of a variational circuit $U(\vec \theta)$ are optimized by measuring the expectation value of the Hamiltonian $H$ and by minimizing the corresponding loss function:

$$
L(\vec \theta) = \langle 0\dots 0 | U(\vec \theta)^\dagger  H  U(\vec \theta) | 0 \dots 0\rangle  .
$$

- **If the circuit $U(\vec \theta)$ is highly expressive**, the minimum of $L$ gives the ground state energy of $E_0$ of $H$.

- **If the circuit $U(\vec \theta)$ has low expressivity** (e.g. if it has few parameters), the minimum of $L$ still provides a useful upper bound for $E_0$.  This is a consequence of the simple bound:

$$ E_0 \le  \langle \Psi| H  | \psi \rangle = \mu_1 \quad  \forall |\psi\rangle .$$

## Improved VQE

Now, consider a similar VQE where instead of just measuring the first moment of the energy, one also measures higher-order moments. **This can be quite expensive** but is always possible when $H$ is the sum of Pauli operators. Say, we measure the first 3 central moments:

$$ \mu_1 = \langle  H \rangle  \quad  \text{(Mean)}. $$
$$ \mu_2 = \langle (H - \mu_1)^2 \rangle   \quad  \text{(Variance)}.$$
$$ \mu_3 =   \langle (H - \mu_1)^3  \rangle   \quad  \text{(Unnormalized skewness)}.$$


What is the best loss function to minimize in this case (assuming we can always reach its global minimum)?

- **If the circuit $U(\vec \theta)$ is highly expressive** I could throw away the information about $\mu_2$ and $\mu_3$ since the standard loss function $L(\vec \theta) = \mu_1 (\theta)$ is enough to reach the ground state energy $E_0$.

- **If the circuit $U(\vec \theta)$ has low expressivity**, probably it is better to use a more complex loss function

$$ L(\vec \theta)= f(\mu_1(\vec \theta), \mu_2(\vec \theta), \mu_3(\vec \theta)), $$

where $f$ is a non-trivial function of the three moments. In particular, we may look for a function $f$ that gives a better estimate of the ground state energy compared to $\mu_1$:

$$E_0  \le  f(\mu_1, \mu_2, \mu_3) < \mu_1, \qquad \forall |\psi\rangle. $$

It is reasonable that this can be done. For example, if we happen to measure $\mu_3=0$, it means that the energy distribution is symmetric around the mean, so I would expect that in this case:

$$E_0  \le  \mu_1 - \sqrt{\mu_2}/2  < \mu_1, \qquad \forall |\psi\rangle \text{ with } \mu_3=0 .$$

Note: I guess that in order to have a non-trivial bound (better than $\mu_1$), one needs at least the first three moments. If we only measure $\mu_1$ and $\mu_2$, we cannot exclude pathological energy distributions with $E_0 \approx \mu_1$ but arbitrary $\mu_2$.

## Open questions

- What is the optimal $f$?
- Is this approach useful in practice?
- Is this idea already implicitly or explicitly in the literature?


## Related references

As far as I know, similar ideas are in Refs[^1][^2][^3]. 

- In Ref.[^1] the moments of H are measured in order to approximate (real and imaginary) time evolution operators by a Taylor truncation in classical post-processing. Since both types of virtual evolutions could be used to estimate the ground state energy of $H$, this shows that the energy moments contain very useful information. However, the method discussed above seems more direct and more focused on the task of ground state energy estimation. 
 
- In Ref.[^2] a similar Taylor truncation trick for evolution operators is obtained by a coherent linear combination of unitaries (not in post-processing). 

- In Ref.[^3]  it is shown that a loss function based on the variance or on a linear combination of mean energy and variance may be more efficient to find low-energy eigenstates states than minimizing variance or mean energy alone. However,  this corresponds to only measuring $\mu_1$ and $\mu_2$ and, as discussed above, this cannot give a better theoretical upper bound to $E_0$. If the task is estimating $E_0$ it can only give a practical improvement in the optimization process. The aim of this project is instead to make use of a better estimate of the ground state $E_0  \le  f(\mu_1, \mu_2, \mu_3) < \mu_1$, where the last $\<$ inequality is strict.

[^1]: P. K. Faehrmann, J. Eisert, M. Kieferova, R. Kueng, _Short-time simulation of quantum dynamics by Pauli measurements_ [arXiv:2412.08719](https://arxiv.org/abs/2412.08719).

[^2]: D. W. Berry, A. M. Childs, R. Cleve, R. Kothari, R. D. Somma, _Simulating Hamiltonian dynamics with a truncated Taylor series_ [arXiv:1412.4687](https://arxiv.org/pdf/1412.4687).

[^3]: D-B Zhang, Z-H Yuan, T. Yin, _Variational quantum eigensolvers by variance minimization_,  [arXiv:2006.15781](https://arxiv.org/abs/2006.15781).

## Link to original issue
- Link to the original issue andreamari/polyquantum#4.

## How to cite this research project as a whole
Short reference: _Polyquantum 4_.\
Full reference: _A. Mari, Variational quantum eigensolver based on high-order moments of the energy, Polyquantum 4, (2025)_.

## How to cite this document
Short reference: _Polyquantum 2.1_.\
Full reference: _A. Mari, Variational quantum eigensolver based on high-order moments of the energy, Polyquantum 4.1, (2025)_.

