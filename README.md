# Decomposing finite Z-Algebras

This is an [ApCoCoA-1](https://apcocoa.uni-passau.de/) package for computing the decomposition of finite Z-algebras. 
The Algorithms are described in the paper: 

*Martin Kreuzer, Alexei Miasnikov and Florian Walsh, Decomposing finite Z-algebras, 
Preprint 2023, available at [arXiv:2308.01735](https://arxiv.org/abs/2308.01735)*

## Installation

## Functions
* ``BilinearGenerators(Mult:LIST,NRelations:LIST,MRelations:LIST,ZSym:BOOL):LIST``

  This function computes a generating set of the maximal ring of scalars of a bilinear map f.
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
  
* ``BilinearPresentation(Generators:LIST,NRelations:LIST):LIST``

  This function computes a presentation of the maximal ring of scalars of a bilinear map f
  ```
  Mult := [[[0,0],[1,0]],[[0,1],[0,0]]];
  NRel := [[3,0],[0,3]];
  MRel := [[1,1],[-3,0]];
  Gens := BM.BilinearGenerators(Mult, NRel, MRel, False);
  BM.BilinearPresentation(Gens, NRel);
  > Relations of S(f): [[3]]
  > Representation of Multiplication: [[1]]
  > Representation of the Identity: [1]
  > [S2::3x[1],S2::x[1]^2-x[1],S2::x[1]-1]
  ```
  
* ``ZAlgebraMaxRing(Mult:LIST,Relations:LIST,Identity:BOOL):RECORD``

  Computes the maximal ring of scalars of a finite Z-algebra given by a multiplication table an relations
  ```
  Mult:=[[[0,0,0,0],[0,1,0,0],[0,0,0,0],[0,0,0,0]],
       [[0,-1,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,0]],
       [[0,0,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,1]],
       [[0,0,0,0],[0,0,0,0],[0,0,0,-1],[0,0,0,0]]];
  Rel:=[[3,0,0,0],[0,0,3,0]];
  ZA.ZAlgebraMaxRing(Mult,Rel);
  > Record[Generators:=[Mat([
  >   [1,0,0,0],
  >   [0,1,0,0],
  >   [0,0,0,0],
  >   [0,0,0,0]
  > ]), Mat([
  >   [0,0,0,0],
  >   [0,0,0,0],
  >   [0,0,1,0],
  >   [0,0,0,1]
  > ])],
  > Presentation:=[x[1]^2-x[1],x[1]x[2],x[2]^2-x[2],
  >                 x[1]+x[2]-1],
  > Relations:=[[3,0,0,0], [0,0,3,0]]]
  ```

  
