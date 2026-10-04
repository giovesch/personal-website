---
title: "Simulating Ferromagnetic Phase Transitions with the 2D Ising Model"
description: "How computational physics and Monte Carlo Metropolis-Hastings algorithms reveal spontaneous symmetry breaking and the Onsager critical temperature."
pubDate: 2026-09-18
tags: ["Physics", "Simulation", "Python", "Algorithms"]
featured: true
readingTime: "5 min read"
---

At the University of Padova, one of the most mesmerizing intersections between statistical mechanics and computation is the **2D Ising Model**. Originally formulated as a simplified mathematical model of ferromagnetism, it captures how microscopic magnetic dipole moments interact with their nearest neighbors.

Despite its deceiving simplicity, the model exhibits a rich phase transition: at high temperatures, thermal fluctuations dominate and the spins point in random directions; below a critical temperature $T_c \approx 2.269 J/k_B$, the system spontaneously magnetizes.

## The Hamiltonian

The energy of a lattice configuration $\sigma = \{\sigma_i\}$ where each spin $\sigma_i \in \{+1, -1\}$ is governed by:

$$H(\sigma) = -J \sum_{\langle i, j \rangle} \sigma_i \sigma_j - h \sum_i \sigma_i$$

Where $J$ is the coupling constant ($J > 0$ for ferromagnets) and $\langle i, j \rangle$ denotes summation over nearest-neighbor pairs.

## Implementing the Metropolis-Hastings Step

To simulate the system on a discrete $L \times L$ grid, we use the Metropolis-Hastings Markov Chain Monte Carlo (MCMC) algorithm:

```python
import numpy as np

def metropolis_step(lattice: np.ndarray, beta: float, J: float = 1.0) -> None:
    """Performs one Monte Carlo sweep over an L x L spin lattice."""
    L = lattice.shape[0]
    for _ in range(L * L):
        i, j = np.random.randint(0, L, size=2)
        s = lattice[i, j]
        # Periodic boundary conditions
        neighbors = (
            lattice[(i + 1) % L, j] +
            lattice[(i - 1) % L, j] +
            lattice[i, (j + 1) % L] +
            lattice[i, (j - 1) % L]
        )
        dE = 2 * J * s * neighbors
        
        # Metropolis acceptance criterion
        if dE <= 0 or np.random.rand() < np.exp(-beta * dE):
            lattice[i, j] = -s
```

## Critical Phenomena and Clustering

Near $T_c$, the correlation length diverges, giving rise to scale-invariant fractal spin clusters. This is where simple local-update Metropolis algorithms experience *critical slowing down*. 

To overcome this in our computational labs, we implement cluster algorithms like **Wolff** or **Swendsen-Wang**, which flip whole connected islands of correlated spins at once. Computational physics teaches us that understanding physical symmetry is often the fastest route to algorithmic optimization.
