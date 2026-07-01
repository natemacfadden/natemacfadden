# Nate MacFadden

<img src="bonsai.jpg" align="right" width="160"/>
<p align="right"><sub>See my first bonsai 'Paco'<br/>(named after one of my favorite<br/>mathematicians). I've grown quite<br/>fond of these trees - I now have<br/>4-5, including a Japanese maple,<br/>redwood, and spruce.</sub></p>

I build high-performance systems and algorithms for hard problems in geometry and combinatorics (from multithreaded C/OpenMP kernels to symmetry-aware neural networks), and ship them as tools other researchers rely on. I lead development of and am the sole active maintainer of [CYTools](https://github.com/LiamMcAllisterGroup/cytools), the standard toolkit in my field (computational string-theory geometry).

A few things I've built: [dualGNN](https://github.com/natemacfadden/dualGNN), a symmetry-aware GNN that beats a ~120M-parameter transformer baseline on sampling uniformity and zero-shot generalization with **~1300x fewer parameters**; [latticepts](https://github.com/natemacfadden/latticepts), a lattice-point enumeration kernel that materializes **~17M points/s** in parallel and is integrated into CYTools and Macaulay2; and agent harnesses that make small, untrustworthy LLMs reliable in a technical domain. These grow out of my string-theory Ph.D. at Cornell (McAllister group), a steady source of hard geometry and combinatorics problems.

**Looking for research engineer / research scientist roles at frontier AI labs.**

**Stack:** Python (PyTorch, NumPy, Numba), Cython, C (OpenMP), C++

## Machine Learning

- **[dualGNN](https://github.com/natemacfadden/dualGNN)** - Autoregressive GNN for combinatorial sampling (triangulations) under local (validity, fineness) and global (regularity) constraints out of a large population. We use signed-circuit edge features from oriented matroid theory which we show are provably necessary (sign-only features fail) and empirically sufficient for determining regularity, and invariant under the problem's symmetries. Pointer-Network-style decoding, trained with cross-entropy then REINFORCE-tuned for uniformity. Has ~92k parameters and trains in ~7.5h on a single RTX 5060 Ti. It is the most uniform sampler we tested across these diagnostics (divergence from uniformity, collision counts, sample autocorrelation); transfers zero-shot to unseen instances. Applied to Calabi-Yau enumeration up to $h^{1,1}=128$ (uniformity validated to $h^{1,1}=86$).
- **[cytools-agent](https://github.com/natemacfadden/cytools-agent)** - An agent harness that lets small open-weight models (e.g. `qwen3:8b`) reliably drive CYTools to answer research-level questions. The guiding principle is that the model is helpful but untrustworthy: a planner routes each question to a tool-calling executor, knowledge comes from a queryable encyclopedia of source-derived definitions rather than model memory, and every numeric result is backed by an evidence ledger and checked against machine-verified invariants (the harness refuses rather than guessing on a violation). Schema-constrained decoding and forgiving tool interfaces take a weak model from near-useless to usefully answering a substantial fraction of such questions, markedly more with self-consistency voting. The same tools are exposed over an MCP server.
- **[pfvscorer](https://github.com/natemacfadden/pfvscorer)** - Learned richness classifier for certain classes of Diophantine problems (i.e., 'PFVs' in string theory). Enumerating the solutions (my pfvs kernel) is fast but eventually hits a fundamental wall; pfvscorer instead predicts how many solutions a class is likely to have, before enumeration, so searches can be steered toward rich classes. Three encoders, each tailored to the symmetry of one geometric input, feed a shared trunk with sigmoid heads that predict P(#solutions > threshold) (e.g. >0 and >50).

## Optimization

- **[fanroots](https://github.com/LiamMcAllisterGroup/fanroots)** - Library for optimization over $\sim200$-dimensional piecewise-smooth functions whose analytic form changes across cone boundaries. Specifically designed for functions of 'Kahler moduli space' in string theory, for which FanRoots is used to locate special points where desired physics can be engineered, as in [Candidate de Sitter Vacua](https://arxiv.org/abs/2406.13751). Achieves 20-70x speedups over the prior methods used there (growing with dimension), and converges on geometries where they fail.
- **[The DNA of Calabi-Yau Hypersurfaces](https://doi.org/10.1002/prop.70060)** *(Fortschritte der Physik, 2025; [code](https://github.com/sheride/cyopt))* - Custom genetic algorithm with hyperparameters tuned by Bayesian optimization; combinatorial optimization over Calabi-Yau search spaces up to ~$10^{36}$ candidates, substantially outperforming MCMC, simulated annealing, and best-first search on both maximization and inverse problems. Built on [the NTFE encoding](https://arxiv.org/abs/2309.10855), which eliminates the search space's exponential redundancy.

## Systems/Kernels/HPC

- **[pfvs](https://github.com/natemacfadden/pfvs)** *(paper in preparation)* - C/Cython algorithm (with some Python prep) for generating (coni-)PFVs orders of magnitude faster than previous methods, with significantly better time and memory scaling - reaching searches an order of magnitude beyond their reach. Converted a many core-year computation into a handful of core-weeks.
- **[latticepts](https://github.com/natemacfadden/latticepts)** - High-performance C/Cython implementation of Kannan's lattice point enumeration algorithm, substantially faster than Normaliz and OR-Tools CP-SAT in some cases. For an example of the performance: `latticepts` generates ~108M lattice points in a polyhedron of interest (the strict interior of a certain 7D cone used in [Candidate de Sitter Vacua](https://arxiv.org/abs/2406.13751)) in ~13s single-threaded, or ~6.3s on 12 threads (~8M points/s, ~17M/s in parallel), materializing the full point set (~2x parallel speedup, which is materialization-bound; counting parallelizes to ~7x). Integrated into CYTools and Macaulay2.
- **[unitri](https://github.com/natemacfadden/unitri)** - Library for efficiently counting the unimodular (i.e., fine) triangulations of arbitrary-shape lattice polygons, not just rectangles. Built on Stepan Orevkov's counting code, reworked and generalized; applied to string theory in [Further Bounding the Kreuzer-Skarke Landscape](https://arxiv.org/abs/2602.16909). Counts *without enumerating* (cost depends only on the bounding box, not the number of triangulations), with exact big-integer arithmetic: e.g. the 4x4 grid's $736,983,568$ triangulations in $\sim0.33$ms, or a height-84 triangle's $\sim 7.6\times10^{65}$ triangulations in $\sim1.26$s.

## Other Software

- **[repo-review](https://github.com/natemacfadden/repo-review)** - Claude Code plugin that reviews a GitHub repo by spawning five lens-specialized sub-agents (performance, correctness, engineering, taste & positioning, documentation) that clone, build, run, test, and profile it. Invoke with `/repo-review:review <repo>`.
- **[NTFE algorithm](https://arxiv.org/abs/2309.10855)** *(code in [CYTools](https://github.com/LiamMcAllisterGroup/cytools/tree/main/src/cytools/ntfe))* - Simple algorithm for generating regular triangulations of reflexive polytopes with distinct 2-face restrictions, exponentially faster than previous methods. Such triangulations lead to potentially-inequivalent Calabi-Yau manifolds via Batyrev's construction. This algorithm is used in most CYTools workflows. Bounds on NTFE counts established in [this work](https://arxiv.org/abs/2602.16909).
- **[regfans](https://github.com/natemacfadden/regfans)** - Python package for regular triangulations of integral vector configurations, associated with [Calabi-Yau Threefolds from Vex Triangulations](https://arxiv.org/abs/2512.14817). Integrated into CYTools.
- **[FastAerosol](https://geant4.web.cern.ch/docs/advanced_examples_doc/example_fastaerosol)** *([code](https://github.com/Geant4/geant4/tree/master/examples/advanced/fastAerosol))* - C++ 'advanced example' contributed to GEANT4 for stochastic simulation of particle transport through aerosol geometries via voxelized droplet generation, with attention to time and memory efficiency. Associated with [this paper](https://www.sciencedirect.com/science/article/pii/S0010465522001023).

## CYTools

Lead developer and maintainer (BDFL) of [CYTools](https://github.com/LiamMcAllisterGroup/cytools), the standard toolkit for studying Batyrevian CY compactifications in string theory. Invited to present this software at multiple conferences. Major contributions include:
  1. a generalization to vex triangulations via `regfans`, and
  2. a significantly faster intersection number kernel.

## Selected papers

- **Sampling Triangulations and Calabi-Yau Threefolds with Autoregressive GNNs** (2026) - Nate MacFadden. [arXiv:2605.27770](https://arxiv.org/abs/2605.27770). [[code]](https://github.com/natemacfadden/dualGNN)
- **The DNA of Calabi-Yau Hypersurfaces: A Genetic Algorithm for Polytope Triangulations** (2025) - Nate MacFadden, Andreas Schachner, Elijah Sheridan. *Fortschritte der Physik* 73 (2025). [doi:10.1002/prop.70060](https://doi.org/10.1002/prop.70060), [arXiv:2405.08871](https://arxiv.org/abs/2405.08871)
- **Further Bounding the Kreuzer-Skarke Landscape** (2026) - Nate MacFadden, Stepan Yu. Orevkov, Michael Stepniczka. [arXiv:2602.16909](https://arxiv.org/abs/2602.16909)

## For fun
<!--
- **[Befunge X OEIS](https://github.com/natemacfadden/befunge)** *(in progress)* - training a transformer model to generate, on demand, a Befunge program (2D esoteric language on a torus) that emits a given OEIS sequence.
-->
- **[ntt (Nate's Triangulation Toys)](https://github.com/natemacfadden/ntt)** - recreational projects, like a cute game for visualizing flips of vector configurations and the [vex triangulations](https://arxiv.org/abs/2512.14817) that these flips lead to.
