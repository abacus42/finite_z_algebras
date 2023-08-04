# Decomposing finite Z-Algebras

This is an [ApCoCoA-1](https://apcocoa.uni-passau.de/) package for computing the decomposition of finite Z-algebras. 
The Algorithms are described in the paper: 

*Martin Kreuzer, Alexei Miasnikov and Florian Walsh, Decomposing finite Z-algebras, 
Preprint 2023, available at [arXiv:2308.01735](https://arxiv.org/abs/2308.01735)*

## Installation

## Functions
* ``BilinearGenerators(Mult:LIST,NRelations:LIST,MRelations:LIST,ZSym:BOOL):LIST``

  This function computes a generating set of the maximal ring of scalars of f.
  If the parameter ZSym is set to True then it only computes generators of Z(Sym(f)).
  ```
  Mult := [[[0 ,0] ,[1 ,0]] ,[[0 ,1] ,[0 ,0]]];
  NRel := [[3 ,0] ,[0 ,3]];
  MRel := [[1 ,1] ,[ -3 ,0]];
  BM.BilinearGenerators(Mult, NRel, MRel, False);
  > Generators of End(N):
  > [[1 ,0] ,[0 ,0]]
  > [[0 ,1] ,[0 ,0]]
  > [[0 ,0] ,[1 ,0]]
  > [[0 ,0] ,[0 ,1]]
  > Generators of Sym(f):
  > [[2 ,0] ,[0 ,0]]
  > [[1 ,0] ,[0 ,1]]
  > Generators of Z(Sym(f)):
  > [[0 ,0] ,[0 ,1]]
  > [[1 ,0] ,[0 ,1]]
  > [[[1 ,0] ,[0 ,1]]]
  ```
