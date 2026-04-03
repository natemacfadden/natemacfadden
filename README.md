# Nate MacFadden

<img src="bonsai.jpg" align="right" width="160"/>
<p align="right"><sub>See my first bonsai 'Paco'<br/>(named after one of my favorite<br/>mathematicians). I've grown quite<br/>fond of these trees — I now have<br/>4.5, including a Japanese maple,<br/>redwood, and spruce.</sub></p>

Ph.D. candidate at Cornell. I work on computational geometry (such as regular triangulations) and string compactifications, with a soft spot for problems where the right algorithm changes what's computationally possible.

**Languages:** C, C++, Python, Cython

<br clear="right"/>

## ML Work

- **[The DNA of Calabi-Yau Hypersurfaces](https://arxiv.org/abs/2405.08871)** — Applied genetic algorithms to the problem of generating Calabi-Yau hypersurfaces via regular triangulations of 4D reflexive polytopes, demonstrating that [the NTFE encoding (2-face restrictions)](https://arxiv.org/abs/2309.10855) yields a structure amenable to multiple optimization methods across search spaces up to ~500M candidates. The custom GA, in particular, outperformed MCMC and simulated annealing, all using the same encoding.

## Software & Algorithms

- **[NTFE algorithm](https://arxiv.org/abs/2309.10855)** — Simple algorithm for generating regular triangulations of reflexive polytopes with distinct 2-face restrictions — necessary for constructing distinct Calabi-Yau hypersurfaces — with exponentially better scaling than previous methods; bounds on NTFE counts established in [this work](https://arxiv.org/abs/2602.16909). Implemented in [CYTools](https://github.com/LiamMcAllisterGroup/cytools).
- **[CYTools](https://github.com/LiamMcAllisterGroup/cytools)** — Lead developer and maintainer of the standard toolkit for studying Batyrevian CY compactifications in string theory. Major contributions include:
  1. a generalization to vex triangulations via `regfans`, and
  2. a significantly faster intersection number kernel (see `fanroots` for an application of this).
- **[latticepts](https://github.com/natemacfadden/latticepts)** — High-performance C/Cython implementation of Kannan's lattice point enumeration algorithm for general polyhedra. Outperforms Normaliz by ~8x in raw speed and continues enumerating 75M+ lattice points where Normaliz and OR-Tools CP-SAT both time out.
- **[regfans](https://github.com/natemacfadden/regfans)** — Python package for regular triangulations of integral vector configurations, associated with [Calabi-Yau Threefolds from Vex Triangulations](https://arxiv.org/abs/2512.14817).
- **[fanroots](https://github.com/natemacfadden/fanroots)** — Optimization library for finding roots of vector-valued functions defined over the secondary fan of point/vector configurations, designed for tasks such as those in [Candidate de Sitter Vacua](https://arxiv.org/abs/2406.13751).
- **[pfvs](https://github.com/natemacfadden/pfvs)** *(coming soon... when the rest of the paper is ready)* — C/Cython algorithm (with some Python prep) for generating (coni-)PFVs orders of magnitude faster than previous methods, with significantly better scaling.
- **[FastAerosol](https://geant4.web.cern.ch/docs/advanced_examples_doc/example_fastaerosol)** — C++ advanced example contributed to GEANT4 for stochastic simulation of aerosol geometries via voxelized droplet placement, with attention to time and memory efficiency. Associated with [this paper](https://www.sciencedirect.com/science/article/pii/S0010465522001023).

## For fun

I put some more recreational projects in **[ntt](https://github.com/natemacfadden/ntt)**. This includes a random, fine, pushing triangulation algorithm written in C and a cute game for visualizing flips of vector configurations and the [vex triangulations](https://arxiv.org/abs/2512.14817) that these flips lead to.
