# Physics-Inspired Optimization of the Quadratic Assignment Problem

Master thesis by Moritz Klein
TU Darmstadt · Fraunhofer IGD · 2026

GPU-accelerated physics-inspired optimization for the Quadratic Assignment
Problem, operating directly in permutation space.

## Abstract

Quantum and quantum-inspired methods usually encode the Quadratic Assignment
Problem (QAP) as a QUBO, which inflates the search space from $n!$ to $2^{n^2}$
states and depends on fragile penalty terms. This thesis reformulates
physics-inspired annealing dynamics to operate directly on integer
permutations, so every move produces a feasible solution and no QUBO is needed.
All methods are implemented from scratch in `ASSA.jl`, a GPU-accelerated solver
framework in Julia, and evaluated on QAPLIB and brain connectome graph
matching. Population Annealing outperforms Tabu Search across the Taillard
benchmark families under a 150-second time limit, and the solvers scale to
connectome instances with $n = 1000$.

## Methods

- Simulated Annealing (SA)
- Simulated Quantum Annealing (SQA)
- Momentum Annealing (MA), with a new caching strategy for cost updates
- Parallel Tempering (PT), including **PT-SQA**, a hybrid of replica exchange and
  multi-slice SQA dynamics
- Population Annealing (PA)

## Highlights

- Direct optimization in permutation space, without QUBO penalty constraints
- GPU-accelerated implementation in Julia (`ASSA.jl`)
- Benchmarks on QAPLIB and brain connectome graph matching
- Problem sizes up to $n = 1000$
- New best-known solution for `tai175e01`: **59286** (previous: 59732)

## Documents

- [Thesis (PDF)](./thesis.pdf)
- [Defense slides (PDF)](./presentation.pdf)
