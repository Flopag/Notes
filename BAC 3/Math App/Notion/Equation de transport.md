# EDP linéaire du première ordre (Equation de transport)

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

On a plusieurs solution, si on veut avoir une solution unique, on va devoir avoir des condition auxiliaires ([Condition initiale](Condition%20initiale.md) , [Condition limites](Condition%20limites.md))

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

## Résolution si non linéaire

*(voir slides 09_Non_linear)*

On considère l'équation générale :

$$u_t = a(u) \ u_x = 0$$

On peut construire des lignes caractéristique en résolvant :

$$\frac{dx}{dt}=a(u(x,t))$$

### Avec une [Condition initiale](Condition%20initiale.md) $\phi$

La pente de la ligne caractéristique est donnée par :

$$a(u(c,t)) = a(u(z,0)) = a(\phi(z))$$

L'équation de la ligne caractéristique est donc :

$$z=x - t \ a(\phi(z))$$

La solution est donc :

$$u(x,t)=u(z,0)=\phi(z(x,t))$$

![](attachments/Pasted%20image%2020230720105323.png)

Les lignes caractéristiques ne vont pas s'intersecter si $a$ est une fonction croissante (ils sont nommé **onde d’extension** ou **onde de raréfaction**) :

$$a(\phi(z))\le a(\phi(w)) \ \ \ , z \le w$$

Si ce n'est pas le cas, on a une fonction discontinu qui donne une **solution faible** (une solution d'une forme intégré de l'[EDP](EDP.md), c'est une solution dans le sens d'une [Distribution](Distribution.md))

![](attachments/Pasted%20image%2020230720110530.png)

On défini la forme conservative de l'équation général :

$$u_t + [A(u)]_x = 0$$

résoudre l'[EDP](EDP.md) au sens des [Distribution](Distribution.md) signifie, trouver une solution (faible) $u$ qui vérifie :

$$\int_{0}^{\infty}{\int_{-\infty}^{+\infty}{\left[u\psi_t+a(u)\psi_x\right] \ dx}\ dt} = 0$$

où $\psi(x,t)$ est une [Fonction test](Fonction%20test.md)