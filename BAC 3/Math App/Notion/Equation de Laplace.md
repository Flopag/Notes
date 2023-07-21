# Equation de Laplace

## Qu'est ce qu'une équation de Laplace

L'équation de Laplace représente un phénomène à l'équilibre

Représentation de Laplace en :
- 1D : $\vec \nabla \bullet \vec \nabla u =\Delta u = u_{xx} = 0$
- 2D : $\vec \nabla \bullet \vec \nabla u = \Delta u = u_{xx}+u_{yy}=0$
- 3D : $\vec \nabla \bullet \vec \nabla u =\Delta u = u_{xx}+u_{yy}+u_{zz}$

Une **fonction harmonique** est une solution de l'équation de Laplace (/ ! \\ on ne parle pas de $cos$ et $sin$ dans ce contexte)

Une **équation de Poisson** est une équation de Laplace [non homogène](EDP.md) :

$$\Delta u = f$$

## Principe du maximum/minimum

si $u(x,y)$ ou $u(x,y,z)$ est une fonction harmonique dans un domaine $D$ en 2D ou en 3D et que la fonction $u$ est continue sur le domaine $D$ et sur la frontière du domaine $D$ alors, les valeurs extreme de $u$ sont atteinte sur la frontière du domaine $D$ et nul-part ailleurs sauf si $u$ est une constante 

*(demo slides 08_Laplace p14)*

## Propriétés d'invarience

- L'équation de Laplace reste inchangé si on applique une translation au variable indépendante
- L'équation de Laplace reste inchangé si on applique une rotation au variable indépendante

## Unicité de la solution pour un [problème de Dirichlet](Condition%20limites.md)

*(demo slides 08_Laplace p19)*

/ ! \\ on parle d'un [problème de Dirichlet](Condition%20limites.md), ça ne fonctionne pas pour un [problème de Neumann](Condition%20limites.md)

## Notation

$\mathbf{x} = (x,y)$ en 2D et $\mathbf{x} = (x,y,z)$ en 3D

$|\mathbf{x}| = \sqrt{x^2+y^2}$ en 2D et $|\mathbf{x}| = \sqrt{x^2+y^2+z^2}$ en 3D

$\mathbf{x}_M$ et $\mathbf{x}_m$ sont respectivement, le maximum et le minimum du domaine $D$ comme énonce dans le principe du maximum/minimum :

$$u(\mathbf{x}_m) \le u(\mathbf{u})\le u(\mathbf x_M) \ \ \ , \forall \mathbf x \in D$$

## Résolution dans des domaines spécifiques

### Dans un rectangle

*(demo slides 08_Laplace p35)*

### Dans un parallélépipède rectangle

*(demo slides 08_Laplace p43)*

### Dans un disque

*(demo slides 08_Laplace p46)*

Formule de poisson :

$$u(r,\theta) = (a^2-r^2)\int_{0}^{2\pi}{\frac{h(\phi)}{a^2-2ar \ cos(\theta-\phi) + r²}\ \frac{d\phi}{2\pi}}$$

la valeur de n'importe quel fonction harmonique en n'importe quel point est la valeur moyenne de cette fonction harmonique le long de n'importe quel cercle centré sur le point considéré et restant a l'intérieur du domaine

ou

La valeur d'une fonction harmonique en un point est égal à la moyenne sur n'importe quel disque centrer sur ce point ou n'importe quel boule (en 3D) pour autant que ces cercles reste bien à l'intérieur du domaine

## Approximation de l'équation de Laplace à l'aide de [Méthodes numérique](Méthodes%20numérique.md)

### [Méthode des différences finies](Méthodes%20numérique.md)

Schema numérique explicite (on calcule les valeurs $n$ à l'aide des valeurs de $n-1$ ) *(Demo slides 09b_Laplace_approx p5)* : 

$$u_{j,k} = \frac{1}{4}(u_{j+1,k}+u_{j-1,k}+u_{j,k+1}+u_{j,k-1})$$

où $j$ est la case selon $x$ et $k$ la case selon $y$

On peut voir que $u_{j,k}$ vaut la valeur moyenne des cases autour de lui (propriété des disks mais en discrète)

On retrouve aussi le principe du maximum à l'aide de cette moyenne
