Table of contents of the _xAct_ course in Prague, 2018. Mathematica Notebooks 
can be found at http://www.xact.es/xActCourse_Prague/ .

# Lecture 1

## The _xAct_ project

### The _xAct_ project

### Sylabus

### Sample session in xTensor

### Working with coordinates

### Working with exterior calculus

### Basic operations

### Cartan structure equations

### Example: Hodge Laplacian in the Schwarzschild metric



# Lecture 2

## Introduction to the Wolfram Language


## Basic elements of the Wolfram Language (WL)
Everyting in the WL is an expression.
### Summary and Exiercises


## Evaluation principles of the Wolfram Language
Expressions are evaluated using definitions until they no longer change.
### Summary and Exercises


## Performing definitions in the Wolfram Language
Ownvalues, Downvalues, Upvalues, etc.
### Summary and Exercises


## Pattern matching in the Wolfram Language
They can be regarded as a variable representing an expression. They enable the
recognition of expressions.
### Most common patterns
`Blank`, `BlankSequence`, `BlankNullSequence`
### Summary and Exercises


## Assining values in the Wolfram Language
### Values can be assigned in two ways
Delayed or non-delayed assignments

### Delayed assignments

### Non delayed assignments

### Summary and Exercises


## Working with expressions in the WL
### Two ways to work with an expression
Operate with the complete or subsets / parts of the expression

### Symmary and Exercises

## Pure functions in the WL
### Two ways of introducing a function
Downvalues, upvalues; purefunction, Lambda-function.

### Summary and Exercises



# Lecture 3

## xTensor: fast abstract tensor computer algebra



# Lecture 4

## _xTensor_ types: continuation

### The delta tensor

### Type `metric`

### Properties of the metric

### Working with multiple metrics

### Summary and Exercises

### Canonicalization in the presence of an unfrozen metric

### Summary and Exercises
The canonicalization involves an algorithm which finds a canonical index configuration for each tensor monomial of a tensorial polynomial. To learn more, read 
https://doi.org/10.1016/j.cpc.2008.05.009


# Lecture 5

## Canonicalization: continuation

### Canonicalization of expressions with non-metric compatible covariant derivatives

### Production of Christoffel tensors

### Canonicalization without introducing Christoffel tensors

### The implosion mechanism

### Summary and Exercises

## Pattern Indices

### Summary and Exercises

# Lecture 6

## Defining and working with tensorial rules



# Lecture 7

## _xTensor_ types: continuation


# Lecture 8

## The variational derivative



# Lecture 9

## The orthogonal splitting



# Lecture 10

## Working with a Killing vector



# Lecture 11

## The conformal Einstein equations



# Lecture 12

## _xCoba_: component calculus


Main features of xCoba:

* Easy translation from expressions written in abstract index notation to 
expressions written with respect to a base.

* Possibility of working with several different bases within the same session. 
Easy change of basis in tensor components.

* Full integration of covariant derivatives. Computation of the connection 
components with respect to any frame.

* Specialised functions to carry out the computation of the connection and 
the curvature tensors for a Levi-Civita connection in holonomic and 
non-holonomic frames. 

_xCoba_ is built around 3 main pillars:

* Geometric set-up: `DefBasis`.

* Storage adapted to individual components: `TensorValues`.

* Storage adapted to full sets of components: `CTensor`. 






### Component calculus with _xCoba_

### Type `Basis`

`DefBasis` introduces a frame field in a vector bundle. In addition to the 
basis name, we need to indicate the vector bundle and a set of numbers used to 
label each element of the base. `DefBasis` supplies the geometric set-up 
required for doing component computations.

### Frame vectors and co-vectors. `Basis` and its properties.

There is a special tensor used to represent any frame field. This tensor is 
`Basis`.

### Expansion of a tensor in `Basis` elements

Once we have a basis we can expand any abstract tensor or tensorial expression 
with respect to the given basis. Use the pair `SeparateBasis`, 
`TraceBasisDummy` for that.

It is also ossible to get rid of basis objects in an expansion by means of 
`ContractBasis` (This is achieved by carrying out the summation of the repeated 
indices).

### Antisymmetric products of `Basis` elements

When defining a basis, the multi-vector and multi-co-vector representing the 
wedge product of all the elements of the basis is automatically defined (the 
eta tensors). These can be thought of as the generalization of the classical 
permutation symbols ε<sub>i<sub>1</sub>i<sub>2</sub>...i<sub>n</sub></sub> and
ε<sup>i<sub>1</sub>i<sub>2</sub>...i<sub>n</sub></sup> which is naturally 
defined in classical tensor analysis. These objects are not true tensors, but 
tensorial densities and therefore we need a special notation for them in order 
to be able to use abstract indices for their representation.

### The parallel derivative

*Theorem*: let _B_ be a frame field defined on a vector bundle _S_(_M_). Then 
there exists a covariant derivative _D_<sub>_a_</sub> with vanishing curvature 
which is compatible with the frame _B_ in the sense that its action on any 
frame element gives zero. Reciprocally, for any covariant derivative whose 
curvature is zero there exists a frame field _B_ which is compatible with the 
covariant derivative. The frame field is unique up to a transformation by the 
structure group of the vector bundle. 

We will call _parallel derivative_ to any covariant derivative that is 
compatible with a frame field.

### Type `Chart`

A `chart` is a particular case of frame field (holonomic frame) in which the 
frame elements correspond to partial derivatives of coordinates.


### Summary

* Frame fields are represented in _xCoba_ using the type `Basis`.

* Coordinate charts are a particular type of frame fields. They are represented 
with the type `Chart`.

* Use `SeparateBasis` and `TraceBasisDummy` to expand any abstract tensor 
expression with respect to a frame.

* Use `ContractBasis` to carry out summations in repeated (basis) indices to 
eliminate `Basis` objects and recover back an abstract tensor expression.

### Exercise

1. Prove by carrying out an explicit expansion that the product of 2 eta 
tensors defined for a given frame is the generalized Kronecker delta `GDelta`.

## Storage of components

In _xCoba_ there are two main ways of storing tensorial or connection 
components:

* Use the `TensorValues` framework. This framework is indicated when we need 
to carry out computations with individual components. For example compute a 
single component of the Riemann tensor for a metric which has a complicated 
algebraic expression. 

* Use the `CTensor` framework. This framework is indicated when we need to 
work with complete sets of components. The components can be given with 
respect to an arbitrary basis or tensor configuration and the change of basis 
or configuration is very simple from the user point of view. For example 
we have the set of components of a tensor in a given basis and for a given 
index configuration and we change the basis and/or the index configuration.

In addition there are facilities in _xCoba_ to change from one framework to 
another.


### Storing tensor components in the `TensorValues` framework

In this framework we have lists of suitable depth to store all the components 
of the tensor in a certain basis. If we have different basis then we will need 
different sets of lists. 

### Summary

* Any abstract index tensorial expression can be transformed into an 
expression with basis indices using `ToBasis`.

* Any `Basis` index tensorial expression can be transformed into an array of 
tensor components using `ComponentArray`.

* Individual tensor components in a given basis are stored using 
`ComponentValue`. They are stored in a `FoldedRule`.

* The index configurations where tensor components have been stored are 
accessed with `TensorValues`.

* Individual tensor components are accessed with `ToValues`.

### Exercises

1. Obtain the (non-tensorial) transformation law of a connection under a 
change of basis.

### The CTensor container

The `CTensor` container is an alternative way of storing components of 
tensors. The main idea is that we have a _container of information_ that is 
able to store the components of a tensor for _any basis_ and 
_any index configuration_. 

### Change of Basis

We can give specific values to the matrix which does the change between bases 
using `SetBasisChange`.

### Introduction of a metric

We can now introduce a metric in our session and carry out the traditional 
computations with it (connection components, curvature tensors, etc). This is 
a computation that can be carried out in both the `TensorValues` and `CTensor` 
frameworks but here we illustrate only the latter. In the `CTensor` framework 
it is not necessary to use `DefMetric`.

### Summary

* `CTensor` is a container of information that is able to store the components 
of a tensor for _any basis_ and _any index configuration_. 

* `ToCTensor` is a converter that is able to compute new `CTensor` expressions 
from a given tensor or `CTensor` for different bases or index configurations.

* `SetBasisChange` stores the components of a basis change matrix relating two 
already defined basis. These components are automatically replaced when using 
`ToCTensor`. 

* `SetCMetric` declares an appropriate `CTensor` expression as the metric for 
doing component computations.

* `MetricCompute` computes the classical quantities (connection, curvature, 
etc) of a metric declared with `SetCMetric`. The metric can be given in 
coordinates or in a non-holonomic frame.


### Exercise

1. Exercise 1
Introduce in the Schwarzschild metric defined previously the Klotsch--Ströbl 
coordinates:
\[
r &= x y + 2 m,\\
t &= x y + 2 m (1 + \log(y/x)),\\
θ &= Θ,\\
ϕ &= Φ.
\]
Find the metric in these new coordinates and carry out the computation of the 
curvature tensors. 



# Lecture 13

## `CTensor` tensorial algebra

### The tensorial properties of `CTensor`

The `CTensor` container has a double role: it is a container to store the 
components of a tensor in any basis but it can also work as an usual tensor 
with abstract indices.

### Indexed `CTensor` expressions

Following the standard behaviour in _xTensor_, the `CTensor` expressions have a 
special output typesetting when indices are added.

### `CTensor`ial algebra

`CTensor`  objects build a tensor algebra and its standard tensor algebra 
operations proceed with identical notations to those in xTensor. 

### Summary

* The `CTensor` container has a double role: it works as a container for the 
components of a tensor and it it is also tensor with abstract indices.

* CTensor is registered as a tensor (`xTensorQ` returns true upon acting on 
it). Therefore it carries all the properties of a symbol belonging to the type 
`Tensor`. These properties can be queried with the corresponding functions.

* The main difference between `CTensor` and any other "ordinary tensor" is that 
its head is not atomic. Therefore it is not introduced in the session through 
`DefTensor` and it is not contained in the list `$Tensors`. 

* There is a tensor algebra of `CTensor` objects similar to the tensor algebra 
of tensors defined with DefTensor. The components stored in the CTensor are 
also subject to the operations of this algebra. 

* Use `ToCCanonical` to sort abstract indices of a `CTensor` object according 
to a pre-defined convention. Symmetries of the `CTensor` are fully taken into 
account.


### Introducing a metric

### `ToCTensor`: changes of bases and change of index configuration

### Extracting components

### Session `CleanUp`

### Summary

* The `CTensor` container is fully prepared to work with a metric and to 
perform changes of basis.

* Use `SetCMetric` to declare a given `CTensor` object as the metric of our 
session. The index configuration of any other `CTensor` can be changed with 
respect to this metric and the Levi-Civita covariant derivative compatible 
with the metric is defined.

* Use `SetBasisChange` to declare a basis change in our session or use the option 
BasisChange of DefBasis at basis definition time.

* Use `ToCTensor` as a converter to perform a change of basis on any `CTensor` 
container. The components of the change of basis matrix will be automatically 
replaced only if a change of basis was declared by following any of the 
available methods.


### Representation of covariant derivatives: the `CCovD` container

### Torsion and curvature

### `TensorDerivative`

### Summary

* The `CCovD` container plays a role similar to the `CTensor` container but it 
is designed to work with covariant derivatives.

* It requires a covariant derivate taken as a reference and a `CTensor` giving 
the components of the corresponding Christoffel tensor.

* For the case of a Levi-Civita covariant derivative an additional argument
specifying the metric tensor in the `CTensor` container can be given. 

* The container `CCovD` can be used as the argument of other _xAct_ functions
to do curvature computations and compute covariant derivatives. 

* The converter of `CCovD` is `ToCCovD` (see examples in the next section).

* Use `TensorDerivative` to compute covariant derivatives of `CTensor` objects.
It has a `CCovD` object as its second argument and its output is another 
`CTensor` object. 


### The _xCoba_ cache system

The computations involving operations with `CTensor` objects are cached. This 
means that they are stored in a cache table and they are not recomputed again, 
unless explicitly asked for by the user.


### Summary

_xCoba_ has its own cache system to store automatically computations involving 
`CTensor` objects:

* Use `PrintxCobaCache` to see the contents of the cache table.

* Use `ClearxCobaCache` to erase entries in the cache table.

* Use `xCobaCacheTable` to change cache table entries manually.

* Use `xCobaCache` to add entries to the cache table.


# Lecture 14.
## Curvature computations
MetricCompute

### Combination of TensorValues and CTensor frameworks

### Computation of Cartan scalars for the Schwarzschild metric in a null
tetrad

### pp-Wave: computation of Cartan scalars

### Kerr--Newman in an orthogonal frame

### Kerr solution in Boyer Lindqvist coordinates and a null tetrad

### General 2d metric connection with torsion

### A hard example: The Pomeransky-Senkov metric

### Vector analysis in 3 dimensions

