# Nate MacFadden

<img src="bonsai.jpg" align="right" width="160"/>
<p align="right"><sub>See my first bonsai 'Paco'<br/>(named after one of my favorite<br/>mathematicians). I've grown quite<br/>fond of these trees — I now have<br/>4-5, including a Japanese maple,<br/>redwood, and spruce.</sub></p>

Ph.D. candidate at Cornell. I build efficient ML for hard combinatorial problems and high-performance algorithms for computational geometry (regular triangulations ❤️). Most recent work: [dualGNN](https://github.com/natemacfadden/dualGNN), a symmetry-aware GNN ~1000x smaller than prior learned baselines on a combinatorial sampling task. Lead maintainer of [CYTools](https://github.com/LiamMcAllisterGroup/cytools), the standard toolkit in my subfield.

Particularly interested in: efficient, symmetry-aware architectures for problems in geometry, combinatorics, and graphics. Looking for research scientist / research engineer roles in industry.

**Stack:** C, C++, Cython, Python (PyTorch, NumPy, Numba)

<br clear="right"/>

## Selected papers

- **Sampling Triangulations and Calabi-Yau Threefolds with Autoregressive GNNs** (2026) - Nate MacFadden. *arXiv (forthcoming)*. [[code]](https://github.com/natemacfadden/dualGNN)
- **The DNA of Calabi-Yau Hypersurfaces: A Genetic Algorithm for Polytope Triangulations** (2025) - Nate MacFadden, Andreas Schachner, Elijah Sheridan. *Fortschritte der Physik* 73 (2025). [doi:10.1002/prop.70060](https://doi.org/10.1002/prop.70060), [arXiv:2405.08871](https://arxiv.org/abs/2405.08871)
- **Further Bounding the Kreuzer-Skarke Landscape** (2026) - Nate MacFadden, Stepan Yu. Orevkov, Michael Stepniczka. [arXiv:2602.16909](https://arxiv.org/abs/2602.16909)
- **Calabi-Yau Threefolds from Vex Triangulations** (2025) - Nate MacFadden, Elijah Sheridan. [arXiv:2512.14817](https://arxiv.org/abs/2512.14817)
- **Efficient Algorithm for Generating Homotopy Inequivalent Calabi-Yaus** (2023) - Nate MacFadden. [arXiv:2309.10855](https://arxiv.org/abs/2309.10855)

## Machine Learning & Optimization

- **[dualGNN](https://github.com/natemacfadden/dualGNN)** — Autoregressive GNN for combinatorial sampling under a hard global constraint (triangulation regularity). Signed-circuit edge features (from oriented matroid theory) are provably necessary-and-sufficient for the constraint and yield exact symmetry invariance. Pointer-Network-style decoding, trained with cross-entropy then REINFORCE-tuned for uniformity. ~92k parameters (~1000x smaller than CYTransformer), ~7.5h on a single RTX 5060 Ti, runs unmodified on an M1 MacBook. Lowest sample bias of any method tested; zero-shot transfer across unseen problem instances. Applied to Calabi-Yau enumeration up to $h^{1,1}=128$.
- **[The DNA of Calabi-Yau Hypersurfaces](https://doi.org/10.1002/prop.70060)** *(Fortschritte der Physik, 2025)* — Custom genetic algorithm with hyperparameters tuned by Bayesian optimization; combinatorial optimization over Calabi-Yau search spaces up to ~$10^{36}$ candidates, substantially outperforming MCMC, simulated annealing, and best-first search on both maximization and inverse problems. Built on [the NTFE encoding](https://arxiv.org/abs/2309.10855), which eliminates the search space's exponential redundancy.

## Software & Algorithms

- **[NTFE algorithm](https://arxiv.org/abs/2309.10855)** — Simple algorithm for generating regular triangulations of reflexive polytopes with distinct 2-face restrictions, exponentially quicker than previous methods. Such triangulations lead to potentially-inequivalent Calabi-Yau manifolds via Batyrev's construction. Bounds on NTFE counts established in [this work](https://arxiv.org/abs/2602.16909). This algorithm is implemented in [CYTools](https://github.com/LiamMcAllisterGroup/cytools).
- **[CYTools](https://github.com/LiamMcAllisterGroup/cytools)** — Lead developer and maintainer of the standard toolkit for studying Batyrevian CY compactifications in string theory. Invited to present this software at multiple conferences. Major contributions include:
  1. a generalization to vex triangulations via `regfans` (see dedicated bullet), and
  2. a significantly faster intersection number kernel (see `fanroots` for an application of this).
- **[latticepts](https://github.com/natemacfadden/latticepts)** — High-performance C/Cython implementation of Kannan's lattice point enumeration algorithm, substantially faster than Normaliz and OR-Tools CP-SAT in some cases. For an example of the performance: `latticepts` generates ~107M lattice points in a polyhedron of interest (the strict interior of certain 7D cone used in [Candidate de Sitter Vacua](https://arxiv.org/abs/2406.13751)) in only ~23s on my laptop.
- **[regfans](https://github.com/natemacfadden/regfans)** — Python package for regular triangulations of integral vector configurations, associated with [Calabi-Yau Threefolds from Vex Triangulations](https://arxiv.org/abs/2512.14817). Integrated into CYTools.
- **[fanroots](https://github.com/LiamMcAllisterGroup/fanroots)** — Library for optimization over a certain class of piecewise-smooth landscapes with combinatorial transitions: the secondary fan of point/vector configurations. The particular task was in finding roots of vector-valued functions, as in [Candidate de Sitter Vacua](https://arxiv.org/abs/2406.13751).
- **[pfvs](https://github.com/natemacfadden/pfvs)** *(paper in preparation)* — C/Cython algorithm (with some Python prep) for generating (coni-)PFVs orders of magnitude faster than previous methods, with significantly better scaling.
- **[FastAerosol](https://geant4.web.cern.ch/docs/advanced_examples_doc/example_fastaerosol)** — C++ 'advanced example' contributed to GEANT4 for stochastic simulation of particle transport through aerosol geometries via voxelized droplet generation, with attention to time and memory efficiency. Associated with [this paper](https://www.sciencedirect.com/science/article/pii/S0010465522001023).

## For fun

I put some more recreational projects in **[ntt (Nate's Triangulation Toys)](https://github.com/natemacfadden/ntt)**. This includes a random, fine, pushing triangulation algorithm written in C and a cute game for visualizing flips of vector configurations and the [vex triangulations](https://arxiv.org/abs/2512.14817) that these flips lead to.
