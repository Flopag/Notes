# Méthodes numérique

## Méthode des différences finies

### Prémisse

on introduit :
- une fonction à une deux variable $u(x, t)$
- deux pas de maille $\Delta x$ et $\Delta t$
- $s$ est une rapport de pas différent selon le cas (exemple pour une [équation de diffusion](Equation%20de%20diffusion.md) : $s=\frac{\Delta t}{(\Delta x)²}$)
- $u_j^n \simeq u(j\Delta x, n \Delta t)$ / ! \\ $n$ n'est pas un exposant mais un indice
- Erreur de la solution $\varepsilon(x,t)$
	- Hypothèse : il est intégrable et carré intégrable par apport à $x$
	- $\varepsilon_k (x_j,t_n) = \hat \varepsilon(k,t_n)e^{-ikx_j}=$ mode $k$ de l'erreur

Il y a trois standard pour approximé la dérivée $\frac{\partial }{\partial x}u(j\Delta x, n\Delta t)$ :
- La différence arrière : $\frac{u_j^n-u_{j-1}^n}{\Delta x}$
- La différence avant : $\frac{u^n_{j+1}-u^n_j}{\Delta x}$
- La différence centré : $\frac{u^n_{j+1}-u^n_{j-1}}{2\Delta x}$

Il y a trois standard pour approximé la dérivée $\frac{\partial }{\partial t}u(j\Delta x, n\Delta t)$ :
- La différence arrière : $\frac{u_j^n-u_j^{n-1}}{\Delta x}$
- La différence avant : $\frac{u^{n+1}_j-u^n_j}{\Delta x}$
- La différence centré : $\frac{u^{n+1}_j-u^{n-1}_j}{2\Delta x}$

On introduit deux types d'erreurs :
- **Erreur de troquature** : erreur due aux termes $O(x)$ et $O(x²)$ qu'on a négligé
	- Local : sur un terme
	- Global : sur la solution finale (plus on fait de pas, plus on accumule une erreur)
- **Erreur d'arrondie** : a cause de l'ordinateur qui n'a as une précision infinie

Il y a trois type de schéma :
- **Explicite** : se base uniquement sur le passé
- **implicite** : se base sur le passé et le future
- **Semi-explicite** : un mélange d'implicite et explicite

### Stabilité

Le schéma est stable si il existe une constante $C$ tel que :

$$\lim_{n\rightarrow +\infty}{||\varepsilon(x,t_n)||²} \le C||\varepsilon(x,t_0)||²$$

Annalyse de Von Neumann :
1. On injecte un mode d'erreur arbitraire ($\varepsilon_k (x_j,t_n)$) dans notre équation différence
2. On simplifie toutes les exponentiels, pour obtenir une relation de récurrence entre les $\hat\varepsilon(k,t_n)$ qui dépendent de $k$
3. Le schéma est stable si aucun des modes ne diverge

### Comment choisir les [Condition initiale](Condition%20initiale.md) si on en a besoin de plusieurs ?

Écrire le schéma pour $n=0$

## Méthode des éléments finis

