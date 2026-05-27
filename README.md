# Nate MacFadden

<img src="bonsai.jpg" align="right" width="160"/>
<p align="right"><sub>See my first bonsai 'Paco'<br/>(named after one of my favorite<br/>mathematicians). I've grown quite<br/>fond of these trees — I now have<br/>4-5, including a Japanese maple,<br/>redwood, and spruce.</sub></p>

Ph.D. candidate at Cornell. I work on computational geometry (regular triangulations ❤️), machine learning for combinatorial problems, and string compactifications. Currently looking for ML research roles in industry. I like efficient solutions to computational problems.

**Languages:** C, C++, Python

<br clear="right"/>

## ML Work

- **[dualGNN](https://github.com/natemacfadden/dualGNN)** - GNN architecture for uniformly sampling fine, regular triangulations. Encodes the polytope/polygon's combinatorics and regularity via its oriented matroid, enabling symmetry invariance and zero-shot generalization to other polytopes/polygons. By utilizing [the NTFE encoding (2-face restrictions)](https://arxiv.org/abs/2309.10855), the model is small (~92k parameters; ~1000x smaller than other learned models), trains quickly (~7.5hrs on my 5060Ti), and can be used to sample CYs at high Hodge numbers (tested up to $h^{1,1}=86$ and $h^{1,1}=128$; architecture runs up to the max $h^{1,1}=491$).
- **[The DNA of Calabi-Yau Hypersurfaces](https://arxiv.org/abs/2405.08871)** — Used [the NTFE encoding (2-face restrictions)](https://arxiv.org/abs/2309.10855) for a combinatorial optimization task: search over Calabi-Yau manifolds arising from Batyrev's construction, optimizing user-defined objective functions. Tested a range of optimization methods (genetic algorithms, best first search, simulated annealing, and MCMC) with various objective functions on search spaces up to ~500M candidates. All methods proved viable, with the genetic algorithm generally outperforming the rest.

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

I put some more recreational projects in **[ntt](https://github.com/natemacfadden/ntt)**. This includes a random, fine, pushing triangulation algorithm written in C and a cute game for visualizing flips of vector configurations and the [vex triangulations](https://arxiv.org/abs/2512.14817) that these flips lead to.
