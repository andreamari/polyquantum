# Unifying quantum circuit lower bounds via resource measures
Oxana Shaya\
_Leibniz University Hannover_  

Recent works derive quantum circuit lower bounds from resource measures such as for the resource theory of entanglement, coherence, magic, or imaginarity.[^1][^2][^3] This raises the question whether these bounds can be formulated in a unified manner for any resource theory with a canonical resource measure. 

## A common mechanism: resource speed limits

The known bounds share a common mechanism, a *local resource speed limit*: a circuit built from local gates can generate a resource only at a controlled rate, and integrating this rate along the circuit yields a complexity lower bound. For entanglement, such rate bounds go back to the study of entanglement rates under local Hamiltonian dynamics.[^5]

For a resource measure $R$ on $n$ qubits, define the *resource velocity*

$$
v_R(k) := \sup_{\rho,H} \left| \frac{d}{dt} R\left(e^{-itH} \rho\, e^{itH}\right) \right|_{t=0},
$$

where the supremum runs over all states $\rho$ and Hamiltonians $H$ supported on at most $k$ qubits with $\|H\|_\infty \le 1$, and the *resource-changing power* of a unitary $U$,

$$
P_R(U) := \sup_{\rho} \left| R(U \rho U^\dagger) - R(\rho) \right|.
$$

A Trotter-based telescoping argument then bounds the circuit cost as

$$
\mathrm{Cost}(U) \ge \frac{P_R(U)}{v_R(2)},
$$

with $k = 2$ the hardware-native case of one- and two-qubit gates. The problem thus separates into two tasks: upper-bounding the two-local resource velocity, and lower-bounding the resource power of the target unitary. At present, the velocity bounds are proven case by case for each resource.

## Open questions

Can such lower bounds be unified within a single framework for all resource theories, using a canonical resource measure?
In the case of magic, the lower bound is expressed in terms of the quantum Fourier entropy, which is shifted by $n$ compared to the stabilizer entropy. 
What resource measure allows for better structural understanding? Maybe the $g$-purity[^4] or the relative entropy of resource $R_{\mathcal{F}}(\rho) = \inf_{\sigma \in \mathcal{F}} D(\rho \| \sigma)$? In the velocity formalism the question becomes structural: which properties of a resource theory — for instance of its set of free states $\mathcal{F}$ — guarantee dimension-stable bounds on the resource velocity $v_R(2)$? A further point of comparison is the Wasserstein complexity of quantum circuits, which provides a parallel metric lower-bound framework.[^6]

[^1]: K. Bu, R. J. Garcia, A. Jaffe, D. E. Koh, and L. Li, *Complexity of quantum circuits via sensitivity, magic, and coherence*, *Commun. Math. Phys.* **405**, 161 (2024), arXiv:2204.12051.
[^2]: J. Eisert, *Entangling power and quantum circuit complexity*, *Phys. Rev. Lett.* **127**, 020501 (2021), arXiv:2104.03332.
[^3]: L. Ye, Z. Wu, and N. Zhou, *Coherence and imaginarity as resources in quantum circuit complexity*, *Adv. Quantum Technol.* (2026), arXiv:2604.05660.
[^4]: A. E. Deneris, P. Braccia, P. Bermejo, N. L. Diaz, A. A. Mele, and M. Cerezo, *Analyzing the free states of one quantum resource theory as resource states of another*, arXiv:2507.11793.
[^5]: M. Mariën, K. M. R. Audenaert, K. Van Acoleyen, and F. Verstraete, *Entanglement rates and the stability of the area law for the entanglement entropy*, *Commun. Math. Phys.* **346**, 35 (2016).
[^6]: L. Li, K. Bu, D. E. Koh, A. Jaffe, and S. Lloyd, *Wasserstein complexity of quantum circuits*, *J. Phys. A: Math. Theor.* **58**, 265302 (2025).

## Link to original issue
- Link to the original issue andreamari/polyquantum#6.

## How to cite this research project as a whole
Short reference: _Polyquantum 6_.\
Full reference: _O. Shaya, Unifying quantum circuit lower bounds via resource measures, Polyquantum 6, (2026)_.

## How to cite this document
Short reference: _Polyquantum 6.1_.\
Full reference: _O. Shaya, Unifying quantum circuit lower bounds via resource measures, Polyquantum 6.1, (2026)_.
