---
title: Problem Set 4
duedate: 16th October
layout: default
---


The exercises this week get you to think a little bit about rings of functions, to see something else that $$\mathbb{C}$$-algebras are useful for.



Question 1: Collecting some lemmas (6 marks)
===
Let $$X$$ be a finite set, and $$k$$ an integral domain.  Then $$\textrm{Fun}(X, k)$$, the set of functions of $$X$$ to $$k$$, is an $$k$$-algebra, with pointwise addition and multiplication, and structure map $$\varphi:k\to\textrm{Fun}(X,k)$$ the inclusion of $$k$$ as the constant functions.

An *idempotent* in a ring $$R$$ is an element $$e\in R$$ s.t. $$e^2=e$$.  A set of idempotents $$e_1,e_2, \dots, e_n$$ are *orthogonal* if $$e_i\cdot e_i=0_R$$ for $$i\neq j$$.  A set of orthogonal idempotents $$e_1,e_2,\cdots, e_n$$ is called *complete* if $$\sum e_i=1_R$$.


1. Prove that an element of $$\textrm{Fun}(X,k)$$ is idempotent if and only if it is the characteristic function of a subset of $$X$$.  Recall that if $$S\subset X$$, the characteristic function $$\chi_S(x)$$ is given by $$\chi_S(x)=1_k$$ if $$x\in S$$ and $$\chi_S(x)=0_k$$ if $$x\notin S$$.

2. Prove that a set of idempotents $$\chi_{S_i}$$ in $$\textrm{Fun}(X,k)$$ are orthogonal if and only if the subsets $$S_i$$ are disjoint.

3. Prove that an orthogonal set of idempotents $$\chi_{S_i}$$ in $$\textrm{Fun}(X,k)$$ is complete if and only if the union of the $$S_i$$ is $$X$$.


Question 2: Classifying algebra maps between $$\textrm{Fun}(X,k)$$. (4 marks)
===

Again, assume $$k$$ an integral domain.  Let $$f:X\to Y$$ a map between finite sets.  We define a map $$f^*:\textrm{Fun}(Y,k)\to \textrm{Fun}(X,k)$$ by $$f^*(g)=g\circ f$$; that is, the value of $$f^*(g)$$ on a point $$x\in X$$ is $$g(f(x))$$.


1. Prove $$f^*$$ is a morphism of $$k$$-algebras, and that every $$k$$-algebra morphism from $$\textrm{Fun}(Y,k)$$ to $$\textrm{Fun}(X,k)$$ is form the form $$f^*$$ for some $$f:X\to Y$$.  (Hint: Use question 1)

2. Given an example of an integral domain $$k$$, finite sets $$X, Y$$ and a *ring* homomorphism $$\textrm{Fun}(Y,k)$$ to $$\textrm{Fun}(X,k)$$ that is *not* of the form $$f^*$$ for any $$f:X\to Y$$.

