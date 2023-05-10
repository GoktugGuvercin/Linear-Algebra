
## Inverse of Matrices

In real numbers, we say that number $a$ has a multiplicative inverse if the number $b$ exists such that $a * b = 1$. In that case, number
$b$ becomes multiplicative inverse of $a$ and it is equal to $\frac{1}{a}$. This idea can be generalized into the matrices in same manner:

Let's assume that matrix $A$ be an invertible (regular) matrix. If the multiplication of matrix $B$ by matrix $A$ results in identity 
matrix $I$, then we call matrix $B$ as inverse of $A$. 

$$ A \cdot B = B \cdot A = I \\,\\,\\, \rightarrow \\,\\,\\, B = A^{-1}$$

Each matrix can have at most $1$ multiplicative inverse, and invertibility can be searched for only square matrices. Almost all real numbers
have a corresponding inverse; only exception is $0$. On the other hand, we can find so many square matrices without any inverse in
linear algebra, which are called singular. Singular matrices are alike that their determinant is equal to $0$. This means that when we
apply elemantary row operations to these matrices, their at least one row will be reduced to a full of zeros. In other words, its rank
will not be equal to its shape of square.

$$ A \\,\\, singular \\,\\, \leftrightarrow \\,\\, det(A) = 0$$

$$ A \\,\\, singular \\,\\, \leftrightarrow \\,\\, rank(A) \neq n$$
