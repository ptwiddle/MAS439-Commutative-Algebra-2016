---
layout: lecture
title: Lecture 14&#58; Noetherian rings
Comments: True
---
 

Motivation: How complicated can finitely generated algebras be?  
====

To make things tractable, we want to study rings that are 'finite' in some way; for instance, finitely generated algebras.  Yesterday we saw using the universal property of polynomial rings that any finitely generated $$R$$ algebra is of the form $$R[x_1,\dots, x_n]/I$$, for some ideal $$I$$, that somehow captures the ``relations'' among the generators.  

A further finiteness condition we might ask is that there aren't too many relations.  Namely, that the ideal $$I$$ is not too complicated -- perhaps that $$I$$ is generated by a small set. 

Using the division algorithms, we have seen that $$\mathbb{Z}$$ and $$k[x]$$ are principle ideal domains -- that is, every ideal is only generated by one element.  However, this fails horribly for $$k[x,y]$$.

Example: Ideals in $$k[x,y]$$ can require arbitrarily many generators.
===

Declare the *total degree* of a monomial $$a x^ny^m$$ to be $$n+m$$.  Let $$I_N$$ be the $$k$$ span of all monomial of degrees at least $$N$$.  Then we claim that $$I_k$$ requires at least $$k+1$$ generators.

We give only the idea of the proof.  Note that the monomials of degree exactly $$N$$ form a vector space of dimension $$N+1$$, with basis $$x^N, x^{N-1}y,x^{N-2}y^2,\dots, y^N$$.  Since multiplying by polynomials only raise the degree, we're basically going to need to our generators to span this vector space, and hence there should be at least $$N+1$$ of them.


The question remains if there are any ideals of $$k[x,y]$$ that are *not* finitely generated -- we will introduce the notion of Noetherian rings to show that in fact they are not.


Definition
===

A ring $$R$$ is *Noetherian* if it satisfies the *Ascending chain condition*: any ascending chain of ideals $$I_1\subset I_2\subset I_3\subset \cdots $$ eventually stabilizes -- that is, there is an $$N$$ with $$I_n=I_N$$ for all $$n\geq N$$.

Proposition
===

A ring $$R$$ is Noetherian if and only if every ideal $$I\subset R$$ is finitely generated.

Proof
===

First, suppose that every ideal of $$R$$ is finitely generated, and consider an increasing chain of ideals $$I_1\subset I_2\subset\cdots$$.  

We first note that $$I=\cup I_k$$ is an ideal (note, it is *not* true that $$I\cup J$$ is an ideal in general -- we must use the fact that the $$I$$'s are contained in each other).  To see this, suppose that $$r,s\in I$$; we must show that $$ar\in I$$ for any $$a\in R$$ and that $$r+s\in I$$.  But since $$r,s\in I$$, there exists some $$N$$ with $$r,s\in I_N$$.  Then $$ar\in I_N\subset I$$ and $$r+s\in I_N\subset I$$, and we are done.

Now, by supposition the ideal $$I$$ is finitely generated, say $$I=\langle r_1,\dots, r_n\rangle$$.  But then as before there is some $$N$$ with $$r_1,\dots, r_n\in I_N$$, but then $$I=\langle r_1\dots, r_n\rangle\subset I_N\subset I$$, and hence $$I_N=I$$, and hence $$I_n=I_N$$ for all $$n\geq N$$.

To prove the other direction, let $$R$$ be Noetherian and assume for contradition that $$I\subset R$$ is an ideal that is not finitely generated; we construct a nonstabilizing ascending chain of ideals $$I_1\subset I_2\subset\cdots$$. Our chain of ideals will all be contained in $$I$$, and will be constructed inductively as follows.  

Begin by picking any $$f_1\in I$$, and declare $$I_1=(f_1)$$.  Since $$I$$ is not finitely generated, in particular $$I_1\neq I$$.  Hence, there is some $$f_2\in I\setminus I_1$$, and we declare $$I_2=(f_1,f_2)$$.  

Inductively, assume that we have chosen elements $$f_1,\dots, f_n\in I$$, with $$I_k=(f_1,\dots,f_k)$$ an ascending chain of finitely generated ideals.  Then in particular $$I_n\subset I$$ is a finitely generated ideal, and hence not all of $$I$$, and there exists an $$f_{n+1}\in I, f_{n+1}\notin I_n$$, and we may continue our construction.  $$\quad\square$$

Examples
===

1. A field $$k$$ has only $$0$$ and $$k$$ as ideals, and hence is Noetherian.
2. Any ideal in $$\mathbb{Z}$$ is generated by one element, hence $$\mathbb{Z}$$ is Noetherian.  (Note, though, that there are arbitrarily long ascending chains of ideals --  $$(p^N)\subset (p^{N-1})\subset (p^{N-2})\subset\cdots\subset (p)\subset (0)$$
3. Since ideals in $$R/I$$ are in bijection with ideals of $$R$$ that contain $$I$$, if $$R$$ is Noetherian then $$R/I$$ is Noetherian.



Theorem (Hilbert's basis Theorem)
===

Let $$R$$ be a Noetherian ring.  Then $$R[x]$$ is Noetherian.


Before we prove Hilbert's basis theorem, observe the following corollary:

Corollary
===
Let $$k$$ be a field.  Then any finitely generated $$k$$ algebra $$R$$ is Noetherian.

Proof
===
Since $$R$$ is a finitely generated $$k$$ algebra, $$R=k[x_1,\dots, x_n]/I$$ for some ideal $$I$$.  Since $$k$$ is Noetherian, by Hilbert's basis theorem and induction $$k[x_1,\dots, x_n]$$ is Noetherian.  Since any quotient of a Noetherian ring is Noetherian, we have $$R$$ is Noetherian.

Proof of Hilbert's basis theorem
===

Suppose $$I\subset R[x]$$; we must show $$R$$ is finitely generated.  The idea is to do something like the division algorithm, and find enough polynomials in $$I$$ so that given any other polynomial in $$g$$ we can match the leading term of our polynomial and decrease its degree.

Thus, define $$J_d$$ be the set of leading coefficients of degree $$d$$ polynomials in $$I$$, that is:

$$J_d=\left\{ a_d\in R \text{ such that there exists } f=a_dx^d+a_{d-1}x^{d-1}+\cdots +a_0\in I\right\}$$

First, observe that $$J_d$$ is an ideal of $$R$$: if $$a,b\in J_d$$, then there exists $$f=a x^d+\cdots, g=bx^d+\cdots\ in I$$, and $$f+g\in I$$ since $$I$$ is an ideal, and $$f+g$$ has leading coefficient $$a+b$$, and so $$a+b\in J_d$$.  Similarly, if $$a\in J_d$$, then there exists $$f=ax^d+\cdots \in I$$, and if $$r\in R$$ then $$rf=arx^d+\cdots\in I$$, and hence $$rf\in I_d$$.

Second, observe that $$J_d\subset J_{d+a}$$, since if $$a\in J_d$$, then there is an $$f=ax^d+\cdots in I$$, and hence $$xf=ax^{d+1}+\cdots \in I$$ has degree $$d+1$$ and leading coefficient $$a$$.  

Now, we start to use the fact that $$R$$ is Noetherian.  First, the ascending chain of ideals $$I_0\subset I_1\subset \cdots I_n\subset $$ must eventually stabilize, and hence there is some $$N$$ with $$I_n=I_N$$ for $$n>N$$.  

Second, each of the $$I_d$$ is finitely generated, say by $$k(d)$$ elements $$r_{d, \ell}, 1\leq \ell\leq k(d)$$.  By the definition of $$I_d$$, there are polnomials $$f_{d, \ell}, 0\leq \ell\leq k(d)$$ with $$f_{d,\ell}=r_{d,\ell}x^d+\cdots$$.

We claim that the $$\{f_{d,\ell}, 0\leq d\leq N, 1\leq \ell\leq k(d)\}$$ generates $$I$$.  That is let $$g\in I$$, we claim that $$g\in \langle f_{d,\ell}\rangle$$.  

We prove this by induction on the degree of $$g$$.  A degree zero element of $$I$$ is just an element of $$R$$, and hence an element of $$I_0$$, and the $$f_{0,\ell}$$ generate $$I_0$$.

Now, assume that all polynomials in $$I$$ of degree strictly less than $$n$$ are in $$\langle f_{d,\ell}\rangle$$, and assume that $$g$$ is a polynomial of degree $$n$$; we show that $$g\in \langle f_{d,\ell}\rangle$$.  Let $$g=a_nx^n+\cdots$$.  By definition $$a_n\in I_n$$, and hence if $$n<N$$ we can write $$a_n=\sum b_\ell r_{d, \ell}$$, and if $$n\geq N$$ we can write $$a_n=\sum b_\ell r_{N,\ell}$$.  

Then the polynomial 

$$h=\left\{\begin{array}[cc]{}\sum b_\ell f_{d,\ell} & d\leq N \\ x^{d-N} \sum b_\ell f_{d, N} & d > N \end{array}\right.$$

has the form $$a_nx^n$$.  Thus, the polnomial $$g-h$$ has degree strictly less than $$n$$ and is in $$I$$, and so by assumption is in in $$\langle f_{d,\ell}\rangle$$, and hence $$g\in \langle f_{d, \ell} \rangle\quad \square$$


 



