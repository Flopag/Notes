# Matrice

Les matrices peuvent être vu comme des ellipses :

![](attachments/Pasted%20image%2020230722112245.png)

Une **matrice adjointe** $A^*$ de $A$ est la transposé de la matrice conjugué de $A$ :

$$A = \left[\begin{matrix}

a_{11} & a_{12}\\
a_{21} & a_{22}\\
a_{31} & a_{32}

\end{matrix}\right]

\rightarrow

A^* = \left[\begin{matrix}

\bar a_{11} & \bar a_{21} & \bar a_{31}\\
\bar a_{11} & \bar a_{22} & \bar a_{33}

\end{matrix}\right]$$

Si $A=A^*$, alors la **matrice est hermitienne**

le **rang** d'une matrice est le nombre de colonnes (ou lignes) qui sont linéairement indépendant. Si aucune colonnes (ou ligne) est linéairement dépendant aux autres, alors la matrice est de rang égal à sa plus petite dimension (dit **rang plein**)

Dans le cas d'une matrice a rang plein, si le nombre de ligne est supérieur ou égale au nombre de colonnes alors, la matrice n'envoie pas deux vecteurs vers le même vecteur

une matrice carré $A$ complexe, est dites **unitaire** si la matrice adjointe $A^*$ est égal à l'inverse $A^{-1}$ :

$$A^*=A^{-1}$$

Si la matrice est réel, elle est dites **orthogonal**

**Norme** d'une matrice $A$ de dimension $n \times m$ comme le plus petit nombre $C$ qui permet de vérifier :

$$||A_x||_{(m)}\le C ||x||_{(n)}$$

La norme peut être construite à l'aide de :

$$||A||_{m,n} = max_{x\in \Im^n, ||x||_{(n)} \ne 0}{\frac{||Ax||_{(m)}}{||x||_{(n)}}} = max_{x\in \Im^n, ||x||_{(n)} = 1}{||Ax||_{(m)}}$$