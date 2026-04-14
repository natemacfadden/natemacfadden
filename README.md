# Nate MacFadden

<img src="bonsai.jpg" align="right" width="160"/>
<p align="right"><sub>See my first bonsai 'Paco'<br/>(named after one of my favorite<br/>mathematicians). I've grown quite<br/>fond of these trees — I now have<br/>4-5, including a Japanese maple,<br/>redwood, and spruce.</sub></p>

Ph.D. candidate at Cornell. I work on computational geometry (regular triangulations ❤️) and string compactifications. I like efficient solutions to computational problems.

**Languages:** C, C++, Python

<br clear="right"/>

## ML Work

- **[The DNA of Calabi-Yau Hypersurfaces](https://arxiv.org/abs/2405.08871)** — Used [the NTFE encoding (2-face restrictions)](https://arxiv.org/abs/2309.10855) to efficiently search over Calabi-Yau manifolds arising from Batyrev's construction, optimizing user-defined objective functions. Tested a range of optimization methods (genetic algorithms, best first search, simulated annealing, and MCMC) with various objective functions on search spaces up to ~500M candidates.

## Software & Algorithms

- **[NTFE algorithm](https://arxiv.org/abs/2309.10855)** — Simple algorithm for generating regular triangulations of reflexive polytopes with distinct 2-face restrictions, exponentially quicker than previous methods. Such triangulations lead to potentially-inequivalent Calabi-Yau manifolds via Batyrev's construction. Bounds on NTFE counts established in [this work](https://arxiv.org/abs/2602.16909). This algorithm is implemented in [CYTools](https://github.com/LiamMcAllisterGroup/cytools).
- **[CYTools](https://github.com/LiamMcAllisterGroup/cytools)** — Lead developer and maintainer of the standard toolkit for studying Batyrevian CY compactifications in string theory. Major contributions include:
  1. a generalization to vex triangulations via `regfans`, and
  2. a significantly faster intersection number kernel (see `fanroots` for an application of this).
- **[latticepts](https://github.com/natemacfadden/latticepts)** — High-performance C/Cython implementation of Kannan's lattice point enumeration algorithm, substantially faster than Normaliz and OR-Tools CP-SAT with better scaling. As one performance example: `latticepts` generates ~107M lattice points in the strict interior of an example 7D cone (arXiv:2406.13751) in ~23s.
- **[regfans](https://github.com/natemacfadden/regfans)** — Python package for regular triangulations of integral vector configurations, associated with [Calabi-Yau Threefolds from Vex Triangulations](https://arxiv.org/abs/2512.14817).
- **[fanroots](https://github.com/natemacfadden/fanroots)** — Optimization library for finding roots of vector-valued functions defined over the secondary fan of point/vector configurations, designed for optimization tasks such as those occurring in [Candidate de Sitter Vacua](https://arxiv.org/abs/2406.13751).
- **[pfvs](https://github.com/natemacfadden/pfvs)** *(coming soon... when the rest of the paper is ready)* — C/Cython algorithm (with some Python prep) for generating (coni-)PFVs orders of magnitude faster than previous methods, with significantly better scaling.
- **[FastAerosol](https://geant4.web.cern.ch/docs/advanced_examples_doc/example_fastaerosol)** — C++ 'advanced example' contributed to GEANT4 for stochastic simulation of particle transport through aerosol geometries via voxelized droplet generation, with attention to time and memory efficiency. Associated with [this paper](https://www.sciencedirect.com/science/article/pii/S0010465522001023).

## For fun

I put some more recreational projects in **[ntt](https://github.com/natemacfadden/ntt)**. This includes a random, fine, pushing triangulation algorithm written in C and a cute game for visualizing flips of vector configurations and the [vex triangulations](https://arxiv.org/abs/2512.14817) that these flips lead to.
