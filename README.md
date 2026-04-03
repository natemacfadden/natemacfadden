# Nate MacFadden

Ph.D. candidate at Cornell specializing in computational geometry and high-performance computation.

## ML Research

- **[The DNA of Calabi-Yau Hypersurfaces](https://arxiv.org/abs/2405.08871)** — Applied genetic algorithms to combinatorial optimization over triangulations of 4D reflexive polytopes, on search spaces up to ~500M candidates. In a benchmark test, the GA significantly outperformed MCMC and simulated annealing. Applies to all 4D reflexive polytopes in the Kreuzer-Skarke database. This work demonstrates that encoding triangulations via their 2-face restrictions — the core insight of the [NTFE algorithm](https://arxiv.org/abs/2309.10855) — yields a structure amenable to ML optimization.

## Software & Algorithms

- **[NTFE algorithm](https://arxiv.org/abs/2309.10855)** — Simple algorithm for triangulating reflexive polytopes with exponentially better scaling than previous methods; bounds on NTFE counts established in [this work](https://arxiv.org/abs/2602.16909). Implemented in [CYTools](https://github.com/LiamMcAllisterGroup/cytools).
- **[CYTools](https://github.com/LiamMcAllisterGroup/cytools)** — BDFL of the standard toolkit for studying Batyrevian CY compactifications in string theory. Contributions include:
  1. a generalization to vex triangulations via `regfans`, and
  2. a significantly faster intersection number kernel (see `fanroots` for an application of this).
- **[latticepts](https://github.com/natemacfadden/latticepts)** — High-performance C/Cython implementation of Kannan's lattice point enumeration algorithm for general polyhedra. Outperforms Normaliz by ~8x in raw speed and continues enumerating 75M+ lattice points where Normaliz and OR-Tools CP-SAT both time out.
- **[regfans](https://github.com/natemacfadden/regfans)** — Python package for regular triangulations of integral vector configurations, associated with [Calabi-Yau Threefolds from Vex Triangulations](https://arxiv.org/abs/2512.14817).
- **[fanroots](https://github.com/natemacfadden/fanroots)** - Optimization library for finding roots of vector-valued functions defined over the secondary fan of point/vector configurations.
- **[pfvs](https://github.com/natemacfadden/pfvs)** *(coming soon... when the rest of the paper is ready)* — C/Cython algorithm (with some Python prep) for generating (coni-)PFVs orders of magnitude faster than previous methods, with significantly better scaling.

## For fun

I put some more recreational projects in **[ntt](https://github.com/natemacfadden/ntt)**. This includes a random, fine, pushing triangulation algorithm written in C and a cute game for visualizing flips of vector configurations and the [vex triangulations](https://arxiv.org/abs/2512.14817) that these flips lead to.
