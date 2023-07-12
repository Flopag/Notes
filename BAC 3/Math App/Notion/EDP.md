# Equation à Dérivée Partiel (EDP ou PDE)

## Qu'est ce qu'une EDP? 

Une EDP est une identité qui lie les [variables indépendantes](Variable%20indépendante.md) et la [variable dépendante](Variable%20dépendante.md) et des dérivées partielles de $u$ par apport a ces [Variable indépendante](Variable%20indépendante.md)

## Qu'est ce qu'une solution d'une EDP ?

Une solution d'une EDP est une fonction $u(x, y, ...)$ qui satisfait l'équation, au moins sur une région des [Variable indépendante](Variable%20indépendante.md)

Une EDP a la forme générale suivante :

$$\mathscr{L}u = g$$

avec $g$ une fonction de [Variable indépendante](Variable%20indépendante.md) ou $=0$ et $L$ est un opérateur

## Ordre d'une EDP

L'ordre d'une EDP est l'ordre de la plus grande dérivée de L'EDP

ex :

- $F(x, U_x) = 0$ est une EDP du première ordre
- $F(x, U_x, U_{xx}) = 0$ est une EDP du deuxième ordre

## Linéarité d'une EDP

Une EDP ($\mathscr{L}$) est **linéaire** si :

- $\mathscr{L}(u+v)=\mathscr{L}u+\mathscr{L}v$
- $\mathscr{L}(cu)=c\mathscr{L}u$

 pour toute fonction $u$ et $v$ et constante $c$

Une EDP est **quasi-linéaire** si les dérivées d'ordre maximum apparaissent de manière linéaire, et ce, pour chacune des [Variable indépendante](Variable%20indépendante.md). Ces EDP (si d'ordre 2) peuvent être transformé en [Système d'EDP du première ordre](Système%20d'EDP%20du%20première%20ordre.md)

Exemple : $u_xu_{xx}+u_y³u_{xy}+(tan \ u)u_{yy}=f(u, u_x, u_y)$ est quasi-linéaire

## Homogénéité d'une EDP

Si $\mathscr{L}$ est un opérateur linéaire si $g = 0$ 

## Type d'EDP

### EDP du première ordre :

[Equation de transport](Equation%20de%20transport.md)

### EDP du deuxième ordre :

EDP générale du deuxième ordre avec deux [Variable indépendante](Variable%20indépendante.md) :

$$a_{11} u_{xx}+2a_{12}u_{xy} + a_{22}u_{yy} + a_1u_x+a_2u_y+a_0u=0$$
**Théorème** : L'équation peut être réduit en une des trois formes canonique plus simple par une transformation linéaire des [Variable indépendante](Variable%20indépendante.md) :
- Forme **elliptique** si $a_{12}² < a_{11}a_{22}$ $\rightarrow$ $u_{xx}+u_{yy}+... = 0$ avec $...$ les termes d'ordre 1 et 0
	- [Equation de Laplace](Equation%20de%20Laplace.md)
- Forme **hyperbolique** si $a_{12}² > a_{11}a_{22}$ $\rightarrow$ $u_{xx}-u_{yy}+... = 0$
	- [Equation d'onde](Equation%20d'onde.md)
- Forme **parabolic** si $a_{12}² > a_{11}a_{22}$ $\rightarrow$ $u_{xx}+... = 0$
	- [Equation de diffusion](Equation%20de%20diffusion.md)
