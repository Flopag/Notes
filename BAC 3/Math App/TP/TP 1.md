# TP 1 : Equation de transport linéaire

## Trouver la solution générale d'une [Equation de transport](../Notion/Equation%20de%20transport.md)

On a l'équation sous la forme générale :

$$a(x,y) u_x + b(x,y) u_y = 0$$

On introduit $\vec \nabla u$ :

$$(a \ \vec e_x + b \ \vec e_y) \ \vec \nabla u=0$$

On est sur des [courbes caractéristiques](../Notion/Equation%20de%20transport.md), on peut donc calculer leur expression à l'aide de :

$$\frac{dy}{dx} = \frac{b}{a}$$

On intègre en multipliant par $dx$ et en mettant $a$ et $b$ la où c'est le plus logique, par exemple :

$$\int dy = \int \frac{b}{a}\ dx \ \  \ ou \ \ \ \int a \ dy = \int b\ dx \ \ \ ou \ \ \ ...$$

Ce qui va introduire une constante $c$ qu'on va devoir isoler

La solution est donc de la forme :

$$u(x,y) = f(c(x,y))$$

Si on a une [Condition limites](../Notion/Condition%20limites.md) ou [Condition initiale](../Notion/Condition%20initiale.md), on peut trouver la solution unique en remplaçant, dans la solution précédente, par cette condition.

## Dessiner les courbes caractéristique d'une [Equation de transport](../Notion/Equation%20de%20transport.md)

On doit faire les même étapes que pour trouver la solution générale mais en s'arrentant quand on a une valeur de $y$ en fonction de $x$ et $c$

On a juste à dessiner une courbe pour plusieurs valeurs de $c$

## Trouver la solution générale d'une [Equation de transport](../Notion/Equation%20de%20transport.md) non homogène

On a l'équation sous la forme générale :

$$a(x,y) u_x + b(x,y) u_y = g(x,y, u)$$

On introduit $\vec \nabla u$ :

$$(a \ \vec e_x + b \ \vec e_y) \ \vec \nabla u=g$$

Vu que la dérivée directionnel n'est plus nul, on a plus de [courbes caractéristiques](../Notion/Equation%20de%20transport.md) constantes. On calcule leur expression comme dans le cas homogène :


$$\frac{dy}{dx} = \frac{b}{a}$$

On résout cette EDO pour trouver $y(x,c)$

Sur ces lignes, $u$ satisfait :

$$\frac{du}{dx} = \frac{g}{a}$$

On résout cette EDO (à l'aide de l'EDO précédente) :

$$\frac{du}{dx} = \frac{\partial u}{\partial x} + \frac{\partial u}{\partial y}\frac{\partial y}{\partial x} = u_x + \frac{\partial y}{\partial x} u_y = \frac{g}{a}$$

On fini la résolution de cette EDO avec les méthodes vue au cours d'analyse 1