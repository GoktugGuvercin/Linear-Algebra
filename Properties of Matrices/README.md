## Skew Symmetric Matrices

* A matrix $D$ is called *skew-symmetric* if $D^T = -D$. Skew-symmetric matrices are full of zeros on their main diagonal, and to 
validate the property of negative symmetry, their upper triangular part has to be same as lower triangular except for the sign of 
entries. 

* Skew-symmetric matrices form a vector space, so by using a vector, we can define its corresponding skew-symmetric matrix. This property 
also helps us to perform cross product in a different manner for 3D case. In other words, cross product of 3D vectors can be calculated 
by skew-symmetric matrix vector product:

$$ a = \begin{bmatrix} 
a_1 & a_2 & a_3
\end{bmatrix}^T \\,\\,\\, \rightarrow \\,\\,\\, [a]_x = A = \begin{bmatrix} 
0 & -a_3 & a_2 \\ 
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 
\end{bmatrix}$$

$$ a \times b = [a]_x \cdot b = \begin{bmatrix} 
0 & -a_3 & a_2 \\ 
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 
\end{bmatrix} \cdot \begin{bmatrix} 
b_1 \\ 
b_2 \\  
b_3 \\
\end{bmatrix}  $$
