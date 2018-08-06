http://www.xact.es/xActCourse_Prague/

# Lecture 1

## The xAct project

### The xAct project

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

## xTensor types: continuation

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

## xTensor types: continuation


# Lecture 8

## The variational derivative



# Lecture 9

## The orthogonal splitting



# Lecture 10

## Working with a Killing vector



# Lecture 11

## The conformal Einstein equations



# Lecture 12

## `xCoba`: component calculus
Main pillars: `DefBasis`, `TensorValues`, `CTensor`

### Component calculus with `xCoba`

### Type `Basis`
`DefBasis` introduces a frame field in a vector bundle.

### Frame vectors and co-vectors. `Basis` and its properties.
`Basis` follows the same conventions of `delta` in relation to a metric.

### Expansion of a tensor in `Basis` elements
`SeparateBasis`, `TraceBasisDummy`, `ContractBasis`

### Antisymmetric products of `Basis` elements
The totally-antisymmetric `eta` tensor densities

### The parallel derivative
There is a one-to-one correspondence between a frame field (up to a transformation) and a covariant derivative which has zero-curvature and gives zero when acting on a frame element.

### Type `Chart`
A `Chart` is a holonomic frame in which the frame elements correspond to partial derivatives.

### Summary and Exercises


## Storage of components
Two main ways of storing tensorial or connection components in `xCoba`: `TensorValues` and `CTensors`

### Storing tensor components in the `TensorValues` framework

### Summary and Exercises

### The CTensor container

12.1.4. Change of Basis

12.1.5. Introduction of a metric

12.1.6. Summary and Exercises



Lecture 13. CTensor tensorial algebra



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

