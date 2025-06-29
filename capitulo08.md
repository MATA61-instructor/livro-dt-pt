# Chapter 8 – Intermediate Representations

## 8.1 Introduction

Most production compilers make use of an intermediate representation
(IR) that lies somewhere between the abstract structure of the source
language and the concrete structure of the target assembly language.

An IR is designed to have a simple and regular structure that facilitates
optimization, analysis, and efficient code generation. A modular compiler
will often implement each optimization or analysis tool as a separate module
that consumes and produces the same IR, so that it is easy to select and
compose optimizations in different orders.

It is common for an IR to have a defined external format that can be
written out to a file in text form, so that it can be exchanged between
unrelated tools. Although it may be visible to the determined programmer, 
it usually isn’t meant to be easily readable. 
When loaded into memory, the IR is represented as a data structure, 
to facilitate algorithms that traverse its structure.

There are many different kinds of IR that can be used; some are very
close to the AST we used up to this point, while others are only a very
short distance from the target assembly language. Some compilers even
use multiple IRs in decreasing layers of abstraction. 
In this chapter, we will examine different approaches to IRs and consider 
their strengths and weaknesses.


## 8.2 Abstract Syntax Tree

## 8.3 Directed Acyclic Graph

## 8.4 Control Flow Graph

## 8.5 Static Single Assignment Form

## 8.6 Linear IR

A linear IR is an ordered sequence of instructions that is closer to the final
goal of an assembly language. It loses some of the flexibility of a DAG
(which does not commit to a specific ordering) but can capture expres-
sions, statements, and control flow all within one data structure. This 
enables some optimization techniques that span multiple expressions.

There is no universal standard for a linear IR. A linear IR typically looks
like an idealized assembly language with a large (or infinite) number of
registers and the usual arithmetic and control flow operations. Here, let
us assume an IR where LOADand STORare used to move values between
memory and registers, and three-address arithmetic operations read two
registers and write to a third, from right to left. Our example expression
would look like this:

```
1. LOAD a -> %r1
2. LOAD $10 -> %r2
3. ITOF %r2 -> %r3
4. FADD %r1, %r3 -> %r4
5. FMUL %r4, %r4 -> %r5
6. STOR %r5 -> x
```


## 8.7 Stack Machine IR

## 8.8 Examples

### 8.8.1 GIMPLE - GNU Simple Representation

### 8.8.2 LLVM - Low Level Virtual Machine

### 8.8.3 JVM - Java Virtual Machine

## 8.9 Exercises

1. Add a step to your compiler to convert the AST into a DAG by
performing a post-order traversal and creating one or more DAG nodes
corresponding to each AST node.

2. Write the code to export a DAG in a simple external representation as
shown in this chapter. Extend the DAG suitably to represent control
flow structures and function definitions.

3. Write a scanner and parser to read in the DAG external representation
and reconstruct it as a data structure. Think carefully about the
grammar class of the IR, and choose the simplest implementation
that works.

4. Building on steps 2 and 3, write a standalone optimization tool that
reads in the DAG format, performs a simple optimization like 
constant folding, and writes the DAG back out in the same format.


## 8.10 Further Reading

1. R. Cytron, J. Ferrante, B. Rosen, M. Wegman, and F. Kenneth Zadeck.
“Efficiently computing static single assignment form and the
control dependence graph.” ACM Transactions on Programming Lan-
guages and Systems (TOPLAS) volume 13, number 4, 1991.
https://doi.org/10.1145/115372.115320

2. J. Merrill, “Generic and GIMPLE: A new tree representation for
entire functions.” GCC Developers Summit, 2003.

3. C. Lattner and V. Adve, “LLVM: A Compilation Framework for Lifelong
Program Analysis & Transformation”, IEEE International
Symposium on Code Generation and Optimization, 2004.
https://dl.acm.org/citation.cfm?id=977673

