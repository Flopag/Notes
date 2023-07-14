# TP 2

## Trouver la solution générale d'une [Equation de transport](../Notion/Equation%20de%20transport.md) [non linéaire](../Notion/EDP.md)

On a une équation à résoudre du type :

$$a(u,x,t)u_t+b(u,x,t)u_x=f(u,x(t),t)$$

et une [Condition initiale](../Notion/Condition%20initiale.md) du type :

$$u(x,0)=g(x)$$

1. Se ramener à la forme canonique :

$$u_t+\frac{b}{a}u_x = \frac{f}{a}$$

2. Trouver les deux EDO du type :

$$
\left\{\begin{array}\

\frac{du}{dt}=\frac{f}{a} \ \ \ (1)\\
\frac{dx}{dt}=\frac{b}{a} \ \ \ (2)

\end{array}\right.
$$

/ ! \\ l'intégrale de $0$ vaut une constante
/ ! \\ si il y a $u$ dans l'équation $(2)$, on peut le remplacer par son expression provenant de $(1)$, et ce, avant de dériver

3. Résoudre ces deux EDO
4. Remplacer une constante obtenue en résolvant $(1)$ à l'aide de la [Condition initiale](../Notion/Condition%20initiale.md) (en posant $x_0=x(0)$)

/ !  \\ Ne pas oublier de remplacer la constante dans l'expression de $(2)$ si elle y est

5. Remplacer $x$ par $x(0) = x_0$ dans $(2)$ pour y trouver la constante
6. Isoler $x_0$ dans l'équation trouvé au point 5
7. Injecter l'expression du point 6 (l'expression de $x_0$) dans l'expression du point 4 (l'expression de $u$)