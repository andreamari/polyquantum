# A simple paraodox about quantum termodynamics
Andrea Mari\
_University of Camerino_  

The following is a simple paradox about quantum thermodynamics. I don't know its solution and so any comment is welcome. 

## The thought experiment

- Consider a 1D box of length L. The box is divided by a removable wall (a separator) into two 2 boxes of length $L_A$ and $L_B$, with $L_A+L_B=L$, as shown in the next diagram:

$$ |      \qquad   \qquad      \longleftarrow L_A    \longrightarrow     \qquad   \qquad     |       \qquad   \qquad      \longleftarrow L_B    \longrightarrow     \qquad   \qquad      |$$


- A quantum particle is placed in the left box and cooled to its ground state.  The initial configuration is shown in the next diagram:

$$ | (\text{wave function with energy } E_A = \frac{\hbar^2 \pi^2}{2 m L_A}    )|        \qquad   \qquad   \qquad    \longleftarrow L_B    \longrightarrow     \qquad   \qquad       |$$

- The separator is vertically removed, so no external work is involved. Assume also that the removal process is approximately instantaneous (compared to the timescale of the particle dynamics). Immediately after the removal of the separator the wave function is unchanged, so it is fully localized in the left part of the box and is zero in the right part of the box. This is no longer an eigenstate of the enlarged box. The new configuration is:

$$ | (\text{same wave function but uncrertain energy)}        \qquad   \qquad   \qquad   \qquad   \qquad   \qquad      |$$

- The energy of the particle is measured. The state collapses into one of the eigenstates of the system, i.e.,  a wave function with support on the full box and energy  $E_j=\frac{j^2 \hbar^2 \pi^2}{2 m (L_A + L_B)} $, with j=1, 2, 3, \dots . The new configuration is:

$$ | \qquad   \qquad   \text{(wave function with energy } E_j = \frac{j^2 \hbar^2 \pi^2}{2 m (L_A + L_B)}   )  \qquad   \qquad   |$$

So, after the full experiment, the particle has a deterministic energy $E_j \neq E_A$. The overall energy shift $\Delta E= E_j - E_A$ can be positive or negative. 

**The paradox:**

During the full experiment no energy is ever exchanged with the external environment. If so, where does the energy shift $\Delta E$ acquired by the particle come from?

**Comments:**
- It is easy to check that the average of  $\Delta E$ evaluated over many experiments is zero (as expected). However, for a single experiment, the paradox remains.
- Removing the separator may actually involve some nonzero (non-deterministic) work, i.e. a nonzero energy exchange with the environment. But, if so, how can we physically explain such work? Is that a pressure from below due to the finite width of the separator? Is that a Casimir-like effect?
- If some non-deterministic work is involved when removing the separator, the amount of work must depend on $L_B$ and thus on the position of the right wall. How is it possible that locally removing the separator requires a work that depends on the position of a distant object? Would that be consistent with the no-signaling principle?

## Link to original issue
- Link to the original issue andreamari/polyquantum#5.

## How to cite this research project as a whole
Short reference: _Polyquantum 5_.\
Full reference: _A. Mari, A simple paraodox about quantum termodynamics, Polyquantum 5, (2026)_.

## How to cite this document
Short reference: _Polyquantum 5.1_.\
Full reference: _A. Mari, A simple paraodox about quantum termodynamics, Polyquantum 5.1, (2026)_.
