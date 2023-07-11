# EDP linéaire du première ordre

## A coefficients constant

[EDP](EDP.md) de la forme :

$$au_x+bu_y=0$$

### Résolution

On introduit :

$$\vec V = a \vec e_x + b \vec e_y = (a, b)$$

L'[EDP](EDP.md) devient :

$$\vec V . \vec \nabla u = 0$$

Ce résultat montre que l'[EDP](EDP.md) $u$ est constant sur une direction $\vec V$

![](attachments/Pasted%20image%2020230711152212.png)

Les lignes où $u(x,y) = cste$ sont appelé des **lignes caractéristiques** et ont la forme :

$$bx - ay = cste$$

On a donc la solution de l'[EDP](EDP.md) qui devient :

$$u(x, y) = f(cste) = f(bx - ay)$$

On a plusieurs solution, si on veut avoir une solution unique, on va devoir avoir des condition auxiliaires

## A coefficient variable

[EDP](EDP.md) de la forme :

$$a(x,y)u_x + b(x,y)u_y = 0$$


### Résolution

En utilisant la même méthode qu'avec un coefficient constant, on a :

$$\vec V = (a, b)$$

![](attachments/Pasted%20image%2020230711161546.png)

On a donc des **courbes caractéristiques** au lieu d'avoir des lignes caractéristiques, elles sont de la forme (qui est une équation différentielle ordinaire ,ODE) :

$$\frac{dy}{dx} = \frac{b}{a}$$

Si $a = 1$ et $b = y$ On obtient :

$$y = cste \ e^x$$

Si on prend en considérations une seul courbe caractéristique, on obtient une 

On a donc la solution de l'[EDP](EDP.md) qui devient :

$$u(x,y) = f(cste) = f(y \ e^{-x})$$