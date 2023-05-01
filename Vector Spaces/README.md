## Span of Vectors:

You have a linear space V, and there is a subset of that space containing the items $v_1$, $v_2$, and $v_3$. All linear combinations of those 
items creates a new set, which is called span. In other words, span is a set enclosing all possible linear combinations.

$span(v_1, v_2, v_3) = a_1v_1 + a_2v_2 + a_3v_3$

Where $a_1$, $a_2$, and $a_3$ are arbitrary scalars.


## Spanning Set (Generating Set):


If all items in the linear space $V$ can be represented by linear combinations of subset $U$, then $U$ is called as spanning set or 
generating set for linear space $V$. In this case, we generally say that $U$ would span linear space $V$.

$$ e_1 = \begin{bmatrix}
    1 \\
    0 \\
    0 \\
\end{bmatrix} \\, \\, \\, \\,  \\, e_2 = \begin{bmatrix}
    0 \\
    1 \\
    0 \\
\end{bmatrix} \\, \\, \\, \\,  \\, e_3 = \begin{bmatrix}
    0 \\
    0 \\
    1 \\
\end{bmatrix}$$

$$ span(e_1, e_2) \neq R^3, \\,\\,\\, span(e_1, e_2) \subset R^3 $$

$$ span(e_1, e_2, e_3) = R^3 \rightarrow U = \\{e_1, e_2, e_3\\} = Generating \\,\\, Set$$


## Independence

Let's we have a set of $n$ vectors denoted by $U$. If any of these vectors cannot be expressed by the linear combination of other $n-1$ vectors
in $U$, then we say that these vectors are independent.

$$ U = \\{v_1, v_2, v_3, ..., v_n\\}$$

$$ a_1v_1 + a_2v_2 + a_3v_3 + ..., + a_nv_n \neq a_iv_i  \\,\\,\\, \forall i \in range(1, n)$$


In this case, any linear combination of $n$ vectors should have only trivial solution. To make sure of it, we need to have a valid test.
First, we send the term $a_iv_i$ to the left side of the equation, and organize the equation in a matrix form $Va = 0$.

$$ a_1v_1 + a_2v_2 + a_3v_3 + ..., + a_iv_i + ..., + a_nv_n = 0 $$

$$ \begin{bmatrix}
    | & | & | \cdots | \\
    v_1 & v_2 & v_3 \cdots v_n \\
    | & | & | \cdots | \\
\end{bmatrix} \cdot \begin{bmatrix}
    a_1 \\
    a_2 \\
    \vdots \\
    a_n \\ 
\end{bmatrix} = 0 $$

If $V$ is invertible, meaning $det(V) \neq 0$, then the equation $a = V^{-1} \cdot 0$ is satisfied, and only one solution which is trivial solution for $a$ shows up. 
Otherwise, non-trivial solutions also exist for $a$, so columns of $V$ are not linearly independent.

## Basis

Let's we have a set of n vectors. To be able to become a basis for linear space $V$, these n number of vectors have to satisfy two 
different conditions specified below:

1) $\\{v_1, v_2, ..., v_n\\}$ is a generating set for linear space $V$
2) $\\{v_1, v_2, ..., v_n\\}$ is composed of n different vectors independent from one another.

In other words, any vector in our linear space V can be expressed in terms of linear combination of basis vectors, and these basis 
vectors cannot be interpreted by each other, so they are regarded as independent. 

* A basis is can be expressed with many different characteristics:
  * Basis = Minimum-sized generating set for linear space $V$ 
  * Basis = Maximum-sized independence set for linear space $V$

* $Size(Basis) = Dim(V)$

* There can be multiple bases for a linear vector space. A vector taken from that space can be represented in terms of those multiple 
bases. In that case, representation coefficients would be different for each of them. 

## Orthogonal and Orthonormal Sets

Let's we have a set of $n$ non-zero vectors called $U$. If dot product of all possible vector pairs derived from this vector set is equal to zero, $U$ is called as orthogonal set. The vectors in an orthogonal set have to be linearly independent. If all those vectors are of unit length, then it is called as orthonormal set. Dividing orthogonal vectors by their respective norms helps to form ortonormal set. A basis for a vector space does not have to be orthogonal or orthonormal set, but standard basis $\\{e_1, e_2, e_3\\}$ is orthonormal set. 

$$ U = \\{v_1, v_2, v_3, \cdots, v_n\\} $$

$$ v_i \cdot v_j = 0, \\,\\,\\, whenever \\,\\, i \neq j \\,\\, \rightarrow \\,\\, U = orthogonal $$

$$ u_i = \frac{v_i}{||v_i||}, \\,\\,\\, \forall i \in range(0, n) \\,\\, \rightarrow \\,\\, U = orthonormal $$

## Gram-Schmidt Process

Gram-Schmidt process is a method used to convert a given set of vectors into their orthogonal and orthonormal versions. It is actually $2$-step process where a vector in the set is orthogonalized in each iteration as a step $1$, and then those orthogonalized vectors are divided by their norms to form their respective orthonormal correspondences. Orthogonalization of vector $v_i$ is dependent on orthonormal of vector $v_{i - 1}$, so these $2$ steps are applied in alternate order. To understand the algorithm better, we can look at the following example:

$$Input: V = \\{v_1, v_2, v_3\\}$$

$$ Iteration 1: o_1 = v_1 \\,\\,\\,\\,\\,\\,\\,\\,\\,\\, e_1 = \frac{o_1}{||o_1||} $$

$$ Iteration 2: o_2 = v_2 - (v_2 \cdot e_1)e_1 \\,\\,\\,\\,\\,\\,\\,\\,\\,\\, e_2 = \frac{o_2}{||o_2||} $$

$$ Iteration 3: o_3 = v_3 - (v_3 \cdot e_2)e_2 - (v_3 \cdot e_1)e_1  \\,\\,\\,\\,\\,\\,\\,\\,\\,\\, e_3 = \frac{o_3}{||o_3||} $$

$$Output 1: Orthogonal \\,\\, Set = \\{o_1, o_2, o_3\\}$$

$$Output 2: Orthonormal \\,\\, Set = \\{e_1, e_2, e_3\\}$$

The mathematical operation done between $v_i$ and $e_j$ in each iteration (v_i \cdot e_j)e_j is actually projection. You can look at the following notation: $Proj_{e_j}v_i = \frac{v_i \cdot e_j}{||e_j||} \frac{e_j}{||e_j||} = (v_i \cdot e_j)e_j \\,\\,\\,\\,\\ (||e_j|| = 1)$
