## Determinant

* Determinant of orthogonal matrices is either 1 or -1.
* Determinant of diagonal matrices is multplication of all diagonal entries. 
* Trace, determinant, and orthogonality are the features searched in only square matrices. 


## Orthogonal Matrices

Square matrices are called orthogonal if their column vectors form an orthonormal set in $R^n$. In other words, to figure out whether 
a matrix is orthogonal or not, we need to check the following $3$ conditions:

1. It is square matrix.
2. Its column vectors are orthogonal to each other. 
3. Norm of column vectors is equal to $1$.

Orthogonal matrices have important properties. Their orthonormal set of columns induce *length-preserving* characteristics. Hence, dot 
product of $2$ different vectors has to be same as dot product of those $2$ vectors multiplied by an orthogonal matrix. In addition to 
this, inverse of orthogonal matrices refer to their transposes:

1. $Q^TQ = I$
2. $Q^T = Q^{-1}$
3. $Qx \cdot Qy = x \cdot y$
4. $||Qx||_2 = ||x||_2 $

Inretestingly, when we apply singular-value decomposition to a square matrix $A$, its matrices $U$ and $V$ become orthogonal. This helps
to compute the determinant of $A$ in an easier way:

$$Det(A) = Det(UDV^T)$$

$$Det(A) = Det(U) * Det(D) * Det(V^T)$$

$$Det(A) = \pm1 * Det(D) * \pm1$$

$$Det(A) = \pm1 * \prod_{i=1}^n D_{ii} * \pm1$$
