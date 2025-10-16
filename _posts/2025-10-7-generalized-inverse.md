---
layout: post
title: Generalized Inverse [IN PROGRESS]
date: 2025-10-07 00:00 +0700
categories: [Math, Linear Algebra]
tags: [math, algebra, linear algebra]    
description: Generalized Inverse. This blog assumes that readers have already grasped the basics of Linear Algebra.
math: true 
---

The concept of the generalized inverse of a matrix arises from the fundamental need to extend the idea of the matrix inverse beyond the realm of square and nonsingular matrices. In classical linear algebra, the inverse of a square matrix $$\textbf{A}$$ exists only if $$\textbf{A}$$ is non-singular, meaning its determinant is non-zero. However, in many real-world problems, we frequently deal with rectangular matrices or singular square matrices where the standard inverse does not exist. These situations commonly occur when solving systems of linear equations that are either overdetermined (more equations than unknowns) or underdetermined (more unknowns than equations). In such cases, the need arises for a more general concept of inversion even when a true inverse cannot be defined.

## Invertible matrix
### Definition  
<blockquote class="box-definition" markdown="1">
<div class="title" markdown="1">
**Definition.** Invertible matrix
</div>
A square matrix $$\textbf{A} \in \mathbb R^{n \times n}$$ is **invertible** if there exists a matrix $$\textbf{B}$$ such that:

$$
\textbf{AB} = \textbf{BA} = \textbf{I}
$$


$$\textbf{B}$$ is called **inverse matrix** of $$\textbf{A}$$, denoted $$\textbf{A}^{-1}$$
</blockquote>

<blockquote class="box-theorem" markdown="1">
<div class="title" markdown="1">
**Theorem. Invertible matrix theorem** 
</div>
Let $\textbf{A} \in \mathbb R^{n \times n}$. The following statements are either all true or all false for any given matrix:
- $\textbf{A}$ is invertible
- $\textbf{A}^\top$ is invertible
- The linear transformation mapping from $\textbf{x}$ to $\textbf{Ax}$ is invertible
- $\textbf{A}$ has full rank: $\text{rank}(\textbf{A}) = n$
- $\textbf{A}$ has nonzero determinant: $\text{det}(\textbf{A}) \neq 0$
</blockquote>

### A geometric perspective 
A matrix $\textbf{A}$ can represent a linear mapping. In particular, every linear transformation $T : \mathbb R^m \mapsto \mathbb R^n$ can be represented by a matrix $\textbf{A} \in \mathbb R^{m \times n}$ such that: 

$$T(x) = \textbf{Ax}$$

In the case of an invertible matrix $\textbf{A} \in \mathbb{R}^{n \times n}$, its inverse $\textbf{A}^{-1}$ also represents the inverse transformation $T^{-1}$. This means that for every output vector $\textbf{y} = T(\textbf{x}) = \textbf{A}\textbf{x}$, there exists a unique input vector $\textbf{x} = T^{-1}(\textbf{y}) = \textbf{A}^{-1}\textbf{y}$. 

By definition of the inverse transformation, applying $T^{-1}$ after $T$ must return the original input vector. In other words, for any $\mathbf{x} \in \mathbb{R}^n$

$$T^{-1}(T(\textbf{x})) = \textbf{x}$$

Since $T$ is represented by the matrix $\mathbf{A}$, and $T^{-1}$ is represented by its inverse $\mathbf{A}^{-1}$, this composition of transformations can be expressed in matrix form as:
$$T^{-1}(T(\textbf{x})) = \textbf{A}^{-1}\textbf{A}\textbf{x} $$

We know that $\textbf{A}^{-1}\textbf{A} = \textbf{I}$, and thus $\textbf{A}^{-1}\textbf{A}\textbf{x} = \textbf{Ix} = \textbf{x}$. This show that the composition of a linear transformation and its inverse resulted in an identity mapping, represented by the matrix $\textbf{I}$, which align with the definition of inverse transformation. 