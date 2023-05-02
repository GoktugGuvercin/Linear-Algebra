## Span of Vectors:

Let $v_1$, $v_2$, $\cdots$, $v_n$ be vectors in the vector space $V$. If we multiply these vectors by pre-determined scalars and then sum them up, we derive their one possible linear combination. In this case, the set of all possible linear combinations of $v_1$, $v_2$, $\cdots$, $v_n$ is called span. The span of the vectors defines a subspace inside their origin vector space $V$.

$$span(v_1, v_2, \cdots, v_n) = a_1v_1 + a_2v_2 + \cdots + a_nv_n, \\,\\,\\, \forall a_i \in \mathcal{R}$$


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

At this point, the confusing part is how we should check this. In other words, the critical point is how we make sure whether all vectors in a space can be represented by linear combinations of subset $U$. In fact, we do not need to explicitly check it. Any set of $n$ linearly independent vectors spans $N$ dimensional vector space. All other cases cannot be spanning set:

1. $U = \\{v_1, v_2, \cdots, v_n\\}$ linearly independent $\rightarrow$ $U$ spans $R^n$
2. $U = \\{v_1, v_2, \cdots, v_n\\}$ linearly independent $\rightarrow$ $U$ cannot span $R^{n+k}$ where $k \in Z^+$
3. For $R^{n+k}$ where $k \in Z^-$, you cannot find $n$ number of independent vectors in $R^{n+k}$
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

The mathematical operation done between $v_i$ and $e_j$ in each iteration $(v_i \cdot e_j)e_j$ is actually projection. You can look at the following notation: $Proj_{e_j}v_i = \frac{v_i \cdot e_j}{||e_j||} \frac{e_j}{||e_j||} = (v_i \cdot e_j)e_j \\,\\,\\,\\,\\ (||e_j|| = 1)$

## Row Space, Column Space and Rank

Let's we have an $m$ x $n$ dimensional matrix $A$. The subspace defined by the span of its row vectors is called *row-space*. Similarly, the subspace spanned by the column vectors in matrix $A$ refers to *column-space* of $A$. The dimensions of row and column spaces have to be same, which refers to *rank* of $A$. To calculate the rank of a matrix, we can use many different approaches like SVD decomposition, or gauss-jordan elimination. However, the main idea lying behind all those techniques is **independence**: The dimension of any subspace spanned by a set of vectors is equal to the number of independent vectors in that set. To understand this better, we can look at the following example:

$$ A = \begin{bmatrix} 
1 & 3 & 2 & 1 \\
2 & 6 & 4 & 2 \\
5 & 4 & 9 & 3 \\ 
\end{bmatrix}$$

When we examine the matrix, we see that row $1$ and row $2$ are dependent on each other; multiplying row $1$ by scalar $2$ directly gives us row $2$. However, row $3$ cannot be expressed in terms of row $1$ and row $2$. As a result, we have $2$ independent row vectors for matrix $A$. In that case, we end up with the following outcomes: 

$$ Dim(row \\, \\, space) = 2$$

$$ Dim(col \\, \\, space) = Dim(row \\, \\, space) \rightarrow Dim(col \\, \\, space) = 2$$

$$ Rank(A) = Dim(col \\, \\, space) = Dim(row \\, \\, space) \rightarrow Rank(A) = 2$$

These outcomes also help us to understand that only $2$ column vectors in the matrix are independent. The column space spanned by these $2$ column vectors refers to a $2$ dimensional plane inside $R^3$. 
