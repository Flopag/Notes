# Equation d'onde

## Qu'est ce qu'une équation d'onde ?

![](attachments/Pasted%20image%2020230713092226.png)

l'équation d'onde représente des ondes qui se propagent

On fait l'hypothèse que $x \in \Re$ pour deux raisons :
- cela permet une très grande simplification mathématique
- beaucoup de phénomène physique restent valable

Forme générale de l'équation d'onde (équation du seconde ordre homogène) :

$$u_{tt}-c²u_{xx} = 0 \ \ \ , x \in \Re$$
où $c$ est la vitesse de propagation de l'onde

On peut directement voir que c'est une équation [hyperbolique](EDP.md)

La solution générale (voir démo) est :

$$u(x,t) = f(x+ct)+g(x-ct)$$

Une solution unique intéressante (voir démo) :

$$u(x,t)=\frac{1}{2}[\phi(x+ct)+\phi(x-ct)]+\frac{1}{2c}\int_{x-ct}^{x+ct}{\psi(s) \ ds}$$

## Principe de causalité

Principe de causalité : Les ondes qui sont solution de cette équation d'onde se déplacent à une vitesse que ne dépasse jamais $c$

En effet, on peut voir que dans la solution unique, on ne prend en compte uniquement les valeurs de $\psi$ dans l'interval $[x-ct, x+ct]$ et des valeur de $\phi$ en $x-ct$ et $x+ct$

On a donc un **domaine d'influence** qui est la région de l'espace qui est influencé par la condition initiale en un point donné 

On a aussi un **domaine de dépendance** qui est la portion de l'axe des $x$ sur lequel on impose une [Condition initiale](Condition%20initiale.md) qui influence le point que l'on considère

## Approximation de l'équation d'onde à l'aide de [Méthodes numérique](Méthodes%20numérique.md)

### [Méthode des différences finies](Méthodes%20numérique.md)

Schéma explicite *(démo slides 05b_Waves_approx p4)* :

$$u^{n+1}_j = s \ (u^n_{j+1}+u^n_{j-1})+2(1-s)u_j^n-u_j^{n-1}$$

avec $s=c²\frac{(\Delta t)²}{(\Delta x)^2}$

[Condition initiale](Condition%20initiale.md) *(démo slides 05b_Waves_approx p10)* :

$$
\left\{\begin{matrix}

u^{0}_j=\phi_j\\
u^{1}_j=\frac{s}{2}(\phi_{j+1}+\phi_{j-1})+(1-s)\phi_j+\psi_j\Delta t

\end{matrix}\right.
$$

Stable si *(démo slides 05b_Waves_approx p13)* :

$$s \le 1$$

## DEMO : Conservation de l'énergie

voir slides "3-waves" à partir de la slide 46

La solution n'est pas atténué $\rightarrow$ conservation de l'énergie

## DEMO : Etablissement de la solution générale

Forme générale d'une équation d'onde :

$$u_{tt}-c²u_{xx} = 0$$

On peut séparer cette équation en deux opérateurs du première ordre :

$$u_{tt}-c²u_{xx} = \left(\frac{\partial}{\partial t}-c \frac{\partial}{\partial x}\right) \left(\frac{\partial}{\partial t}+c \frac{\partial}{\partial x}\right) u = 0$$

On peut donc résoudre cette équation en deux étapes (en ajoutant une nouvelle [Variable dépendante](Variable%20dépendante.md) $v$) :

$$
\left\{\begin{array}a

u_t+cu_x=v\\
v_t-cv_x=0

\end{array}\right.
$$

On doit donc résoudre une [équation non homogène](EDP.md) et une [équation homogène](EDP.md)

### Résolution de l'[équation homogène](EDP.md)

Résolution de :

$$v_t-cv_x=0$$

La résolution suit celle montrer pour l'[Equation de transport](Equation%20de%20transport.md) (ou [TP 1](../TP/TP%201.md))

On obtient la solution générale :

$$v(x,t)=h(x+ct)$$

où $h()$ est une fonction quelconque

### Résolution de l'[équation non homogène](EDP.md)

Résolution de :

$$u_t+cu_x=v$$

On remplace par le résultat précédent :

$$u_t+cu_x = h(x+ct)$$

Pour avoir la solution générale de l'[équation non homogène](EDP.md), on fait la somme entre une solution particulière de l'[équation non homogène](EDP.md) $f$ et la solution générale de l'équation homogénéisé $g$ (on peut le faire car l'équation est [linéaire](EDP.md))

#### Solution particulière

On trouve directement une solution particulière :

$$u(x,t) = f(x+ct)$$

où $f()$ est une fonction quelconque

En effet, si on met la solution dans l'équation (pour vérifier) :

$$u_t+cu_x = c \ f'(x+ct) + c \ f'(x+ct) = 2c \ f'(x+ct) = h(x+ct)$$

où $f'$ correspond à la dérivé par apport à une variable *(Je ne comprend pas le sens mais c'est ce qui est mis)*

#### Solution générale

Résolution de :

$$u_t+cu_x=0$$

La résolution suit celle montrer pour l'[Equation de transport](Equation%20de%20transport.md) (ou [TP 1](../TP/TP%201.md))

On obtient la solution générale :

$$u(x,t)=g(x-ct)$$

où $g()$ est une fonction quelconque

#### Assemblage de $f$ et $g$

La solution générale de l'[équation non homogène](EDP.md) est :

$$u(x,t) = f(x+ct)+g(x-ct)$$

### Solution générale de l'équation d'onde

La solution générale est donc :

$$u(x,t) = f(x+ct)+g(x-ct)$$

## DEMO : Deux [Condition initiale](Condition%20initiale.md) permettent d'avoir une solution unique

voir slides "3-waves" à partir de la slide 24

Resultat :

$$u(x,t)=\frac{1}{2}[\phi(x+ct)+\phi(x-ct)]+\frac{1}{2c}\int_{x-ct}^{x+ct}{\psi(s) \ ds}$$

avec :
- $\phi(x)=f(x)+g(x)$
- $\psi (x)=cf'(x)-cg'(x)$