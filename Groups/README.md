## Definition of Groups

In mathematics, a group is a non-empty set associated with an operator: $G = (S, \cdot)$ Any two elements from this group is combined by the operator to derive other group elements. However, this does not mean that every set with an operator refers to a group. The following $4$ properties need to be satified so that our set-operator pair can be regarded as a group:

1) Closure: $\\,\\,\\,\\,\\,\\, \forall \\, a_1, \\, a_2 \in S \\,\\,\\, a_1 \cdot a_2 \in S$
1) Associative Law: $\\,\\,\\,\\,\\,\\, \forall \\, a_1, \\,\\, a_2, \\,\\, a_3 \\, \in S \\,\\,\\, (a_1 \cdot a_2) \cdot a_3 = a_1 \cdot (a_2 \cdot a_3) $
3) Identity element: $\\,\\,\\,\\,\\,\\, \exists \\, a_I \in S \\,\\,\\, s.t. \\,\\,\\, \forall a \in S, \\,\\, a_I \cdot a = a \cdot a_I = a$
4) Reverse: $\\,\\,\\,\\,\\,\\, \forall \\, a \in S, \\, \exists \\, a^{-1} \in S, \\,\\,\\, s.t. \\,\\,\\, a \cdot a^{-1} = a_I$

At this point, the properties for identity and reverse elements can be confusing. To be more clear, it is better also to expresse verbally: 

* In identity condition, there has to be an element in the set called identity such that any element from set should gives rise to itself when it is combined with idendity element by the operator.
* In reverse condition, every element in the set should possess its inverse that can be derived by the operator on idendity.

## Topological and Discrete Groups

As you noticed, the groups are actually abstract mathematical objects working with binary operators at the top of special properties, but if they satisfy the continuity condition, they acquire specific topology in the space. In that case, they can be described and illustrated in a geometrical perspective. These groups are called ***topological group***. Each topological group is the combination of the group and respective topological space.

Real numbers form a topological group under *addition* operator. On the other hand, this is not the case for integer numbers; instead
they comprise a discrete group lacking continuity. The main difference between discrete and topological groups is the continuity 
condition itself. Discrete groups do not have specific topology, so their expression in terms of a geometrical object becomes impossible. At this point, we need to consider *neighborhood* to understand the continuity in a better way.

Let's pick up an item called $a$ from a group. If its neighborhood only contains itself, then this means that our group proves to be
lack of continuity. 

$$ Z = \\{- \infty, \cdots, -3, -2, -1, 0, \\, 1, \\, 2, \\, 3, \cdots, \infty \\} $$

$$ Element \\,\\,\\, a = 1 $$

$$ One \\,\\, Neighborhood \\,\\, of \\,\\, Element \\,\\,\\, a = [0.5, 1.5] $$

$$b \not \subset [0.5, 1.5] \\,\\,\\, \forall b \in Z$$

## Manifolds and Their Relationship with Groups

In mathematics, each manifold is actually a topological space where its local regions can be mapped into Euclidean space by preserving
its topological properties. Since topological spaces are also the groups with a topology, each manifold naturally becomes a group. In that case, if you have an n-dimensional manifold, that manifold refers to a topological group with the property that 
each point in the group has a neighborhood that is homeomorphic to an open subset of n-dimensional Euclidean space. The groups intersect with manifolds at this point.

## 3 Types of Multi-View Geometry Groups

In multi-view image geometry, we have $3$ main groups:

1) General Linear Group $GL(n)$: It is the set of $n \times n$ invertible matrices together with matrix multiplication operator.

2) Special Orthogonal Group $SO(n)$: It is the set of all orthogonal matrices with determinant $1$. It is also called as rotation group, because its elements are usual rotation matrices around a point or a line for $2D$ and $3D$ cases. It is defined with matrix multiplication operator. 

3) Special Euclidean Group $SE(n)$: It consists of rigid transformation matrices. These matrices are combination of rotation matrix and translation vector in homogenous coordinate system.
