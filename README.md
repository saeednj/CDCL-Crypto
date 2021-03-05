# CDCL(Crypto)

CDCL(Crypto) is a CDCL SAT solver for cryptanalysis problems (inspired by the
CDCL(T) paradigm in SMT solvers). It uses a programmatic SAT design to extend
the logical reasoning components of a SAT solver (propagation and conflict
analysis) with domain-specific knowledge about the cryptographic primitives
being analyzed by the solver. The base solver used in this project is MapleSAT.


## Usage

This repository hosts the implementation of the general framework of
CDCL(Crypto) described in [1]. The programmatic callback is the function
`Solver::callbackFunction` within `src/core/Solver.cc`, which contains
comments and a sample code on how to use the function. For each problem,
the user should encode their higher level constraints inside this function. The assigned value to each variable `x` can be read by `value(x)`, and returned reason/conflict clauses should be in `vec<Lit>` (Minisat format).



## References

[[1]](https://arxiv.org/abs/2005.13415) Nejati, Ganesh, "CDCL(Crypto) SAT
Solvers for Cryptanalysis", CASCON 2019.

[[2]](https://link.springer.com/chapter/10.1007/978-3-319-98334-9_47) Nejati,
Horacek, Gebotys, Ganesh, "Algebraic Fault Attack on SHA Hash Functions Using
Programmatic SAT Solvers", CP 2018


