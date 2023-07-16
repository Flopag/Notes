# Equation de diffusion

## Qu'est ce qu'une équation de diffusion ?

L'équation de diffusion représente un phénomène de diffusion

Forme générale de l'équation de diffusion (équation du seconde ordre homogène) :

$$u_t - ku_{xx}=0$$

## Principe du maximum

Si $u(x,t)$ satisfait l'équation de diffusion $u_t - ku_{xx}$ dans un rectangle $R(0 \le x\le l, 0 \le t \le T)$ dans l'espace temporelle, alors la valeur maximale de $u(x,t)$ est supposé soit en $t=0$ soit sur les valeurs limites $x=0$ ou $x=l$

L'équation de diffusion tend donc a homogénéiser la solution

*Le principe est logique si on pense à un barreau chauffé en un point ou au bord*

*Demo slides 4-Diffusion p8*

![](attachments/Pasted%20image%2020230714102732.png)

## Principe du minimum

Pareil que le principe du maximum mais avec le minimum

la démo est la même mais avec $-u(x,t)$

## DEMO : Une [Condition initiale](Condition%20initiale.md) et de [Condition limites](Condition%20limites.md) permettent d'avoir une solution unique

Problème de Dirichlet = combinaison de [Condition initiale](Condition%20initiale.md) et de [Condition limites](Condition%20limites.md)

*Demo slides 4-Diffusion p14*

## DEMO : [Stabilité](Problème%20bien%20posé.md)

*Demo slides 4-Diffusion p19*

## Approximation de l'équation de diffusion à l'aide de [Méthodes numérique](Méthodes%20numérique.md)

### [Méthode des différences finies](Méthodes%20numérique.md)

Schema numérique explicite (on calcule les valeurs $n$ à l'aide des valeurs de $n-1$ ) *(Demo slides 4-Diffusion_approx p20)* : 

$$u_j^{n+1} = s \ (u^n_{j+1}+u^n_{j-1})+(1-2s)u_j^n$$

où $s=\frac{\Delta t}{(\Delta x)²}$

Le schéma est stable si $s < \frac{1}{2}$ *(Demo slides 4-Diffusion_approx p35)*

si on utilise un schema numérique implicite (on calcule les valeurs $n$ à l'aide des valeurs de $n-1$ et $n+1$), on gagne en stabilité

Schéma semi-explicite :

$$\frac{u_j^{n+1}-u^n_j}{\Delta t} = (1-\theta) \frac{u^n_{j+1}-2u_j^n+u_{j-1}^n}{(\Delta x)²}+\theta \frac{u^{n+1}_{j+1}-2u_j^{n+1}+u_{j-1}^{n+1}}{(\Delta x)²}$$

où $\theta \in [0,1]$
