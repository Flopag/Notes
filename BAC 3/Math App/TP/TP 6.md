# TP 6 : Conditions initiale d'un équation de diffusion

## Théorie

L'[Equation de diffusion](../Notion/Equation%20de%20diffusion.md) est de la forme :

$$u_t-ku_{xx}=0$$

où $k > 0$ est le coefficient de diffusion

La solution générale d'une [Equation de diffusion](../Notion/Equation%20de%20diffusion.md) est :

$$u(x,t)=\frac{1}{\sqrt{4\pi kt}}\int_{-\infty}^{+\infty}{e^{-\left(\frac{x-y}{\sqrt{4kt}}\right)^2}\phi(y) \ dy}$$

Fonction d'erreur :

$$erf(x) = \frac{2}{\sqrt{\pi}}\int_0^x{e^{-\xi^2}\ d\xi}$$

Intégrale Gaussienne :

$$\int_{-\infty}^{+\infty}{e^{-\alpha x^2} \ dx} = \sqrt{\frac{\pi}{\alpha}}$$

Fonction de Dirac :

$$\int_{-\infty}^{+\infty}{f(x)\delta(x) \ dx}=f(0)$$

## Méthodes

## Résoudre un problème de [Condition initiale](../Notion/Condition%20initiale.md) sous forme d'erreur en utilisant la solution générale de l'[Equation de diffusion](../Notion/Equation%20de%20diffusion.md)

1. Ecrire la solution générale de l'[Equation de diffusion](../Notion/Equation%20de%20diffusion.md) en remplaçant $\phi(y)$ par les [Condition initiale](../Notion/Condition%20initiale.md) (ne pas oublier de changer les bornes d'intégration)
2. Faire un changement de variable dans la solution générale pour avoir une expression qui ressemble à une fonction cible. Typiquement $\xi = \frac{x-y}{\sqrt{4kt}}$
3. Simplifier l'expression

### Changement de variable des dérivées partiel

(un exemple est plus simple)

On veut faire le changement de variable $(x,t)\rightarrow (y(x,t),z(x,t))$, on a donc :

$$\left\{\begin{matrix}

\partial_x=\frac{\partial y}{\partial x}\partial_y+\frac{\partial z}{\partial x}\partial_z\\
\partial_t=\frac{\partial y}{\partial t}\partial_y+\frac{\partial z}{\partial t}\partial_z

\end{matrix}\right.$$