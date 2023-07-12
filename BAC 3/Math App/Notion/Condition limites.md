# Condition limite

## Qu'est ce qu'une condition limite ?

Une condition limite spécifie l'état à l'extrémité d'un domaine $D$ où l'[EDP](EDP.md) est valide

Si le domaine n'a pas d’extrémité, la condition limite sera en l’infini

Si le domaine est séparé en deux parties avec des propriétés différentes, on utilisera des conditions de saut

Il y a trois types de condition limites :
- **Condition de Dirichlet** (D) : on impose directement directement $u$ sur tous les points de la frontière
	- Equation de la forme : $u = g(x,t)$
- **Condition de Neumann** (N) : on impose la dérivé de $u$ sur tous les points de la frontière
	- Equation de la forme : $\frac{\partial u}{\partial n} = g(x,t)$
- **Condition de Robin** (R) : combinaison de Dirichlet et Neumann

Ces conditions limites sont souvent écrit sous la forme d'équation

## Homogénéité d'une condition limite

Une condition limite est homogène si, dans son équation, $g(x,t) = 0$. Sinon, il est inhomogène