# TP 2 : Electrostatique (capacité et image)

## Théorie

$$

\left\{\begin{matrix}

\vec \nabla \times \vec E = \vec 0\\
\vec \nabla \bullet \vec D = \rho_{libre}

\end{matrix}\right.
$$

avec :
- $\vec E = -\vec \nabla V$
- $\vec D=\varepsilon\vec E$ (dans un [Matériau LHI](../Notion/Matériau%20LHI.md))

Si on assemble tous ça, on obtient :

$$\vec \nabla \bullet (\varepsilon \vec \nabla V)=-\rho_{libre}$$

Si les conditions limites sont appropriées, on a un problème bien posé (solution unique)

[Principe de superposition](../Notion/Principe%20de%20superposition.md)

Hypothèse dans le cours :
- $\varepsilon$ est constant par région ([équation de poisson](../Notion/Potentiel%20électrique.md)) :

$$\Delta V = \frac{-\rho_{libre}}{\varepsilon} \ \ \ \ par \ région$$
- $\rho_{libre} = 0$ hors des conducteurs ([équation de Laplace](../Notion/Potentiel%20électrique.md)) :

$$\vec\nabla²V=0$$

- dans un conducteur parfait :

$$
\left\{\begin{matrix}

\vec E = \vec 0\\
V = cste\\
charge \ libre \ en \ surface

\end{matrix}\right.
$$

Condition de transport (a l'interface de deux régions non conductrice) :

$$
\left\{\begin{matrix}

V_1|_\Gamma = V_2|_\Gamma\\
\varepsilon_1\vec \nabla V_1 - \hat n|_\Gamma = \varepsilon_2\vec \nabla V_2 - \hat n \rightarrow (\vec D_1 - \vec D_2)\bullet \hat n=\sigma_{libre = 0}

\end{matrix}\right.
$$

où $\Gamma$ est la frontière entre les deux régions

[Capacité électrique](../Notion/Capacité%20électrique.md) : $c=\frac{Q}{V_0}$ entre deux électrode où $Q$ est la [Charge](../Notion/Charge.md) libre dans une électrode et $V_à$ la [d.d.p](../Notion/Potentiel%20électrique.md) entre les deux électrodes

## Bonus

$$\Delta V = \int_a^b{\vec E \bullet d\vec l}$$

## Méthodes

### Calcul de la [Capacité électrique](../Notion/Capacité%20électrique.md)

1. Trouver $V_0$ et $Q$
2. Utiliser la formule $c = \frac{Q}{V_0}$

### Calcul de $V_0$ sachant $Q$

1. Calculer $\vec E$ avec le [théorème de Gauss](../Notion/Loi%20de%20Gauss.md) (il faut prendre les symétries et / ! \\ c'est non systématique)
2. $V_0 = -\int_{el1}^{el2}{\vec E_0 d\vec l}$

### Calcul de $Q$ sachant $V_0$

1. Résoudre l'[équation de Laplace](../Notion/Potentiel%20électrique.md) hors des électrodes
2. En déduire le [Champ électrique](../Notion/Champ%20électrique.md) : $\vec E = - \vec \nabla V$
3. Calculer $Q$ avec le [théorème de Gauss](../Notion/Loi%20de%20Gauss.md) : $\int_S{\vec D \bullet d\vec S} = Q$

### Méthode des images

Dans certain cas, on peut donner $V$ directement à partir de résultat connu. Si $V$ satisfait Laplace et les condition limites $\rightarrow$ c'est une solution unique