# Champ électrique

Le champ électrique $\vec E$ en un point de l'espace est la [force de Coulomb](Loi%20de%20Coulomb.md) $\vec F$ divisé par la [Charge](Charge.md) $Q$ :

$$\vec E = \frac{\vec F}{Q} = \frac{1}{4\pi \varepsilon_0}\frac{q}{r_{Qq}²} \ \hat r_{Qq} \left[\frac{V}{m}\right]$$

![](attachments/Pasted%20image%2020230712141801.png)

## Ligne de champ

Les lignes de champ représente le [Champ électrique](Champ%20électrique.md) $\vec E$

Les lignes sont parallèle à $\vec E$ et leur densité est proportionnelle à $|\vec E|$

Les lignes commencent sur des [Charge](Charge.md) positives et se termine sur des [Charge](Charge.md) négatives

/ ! \ les lignes de champs ne se croisent jamais

![](attachments/Pasted%20image%2020230712145840.png)

## Champ électrique pour une distribution continue

En utilisant le [Principe de superposition](Principe%20de%20superposition.md), on obtient :

$$\vec E = \frac{1}{4\pi \varepsilon_0} \sum_i{q_i\frac{\vec r - \vec r_{qi}}{|\vec r - \vec r_{qi}|³}}$$

En utilisant la [Densité de charge](Densité%20de%20charge.md) sur une distribution continue, on obtient :

$$\vec E = \frac{1}{4\pi \varepsilon_0} \int_V{\rho(x', y', z')\frac{\vec r - \vec r'}{|\vec r - \vec r'|³} \ dV'}$$

avec
- $\vec r'$ la distance entre l'origine et le volume infinitésimale considéré
- $dV' = dx'dy'dz'$

## Divergence du champ électrique

[Loi de Gauss](Loi%20de%20Gauss.md)

## Rotationnel du champ électrique

[Loi de Stockes](Loi%20de%20Stockes.md)

## Condition limite

$$\hat n_{21} \times (\vec E_1-\vec E_2) = 0$$
*(Demo ch 6 p6)*

![](attachments/Pasted%20image%2020230717152934.png)

Si on est dans le cas d'un [Conducteur parfait](Conducteur.md) dans le milieu 2, on a une conductivité $\sigma \rightarrow \infty$  et donc l'[épaisseur de peau](Effet%20de%20peau.md) est $\delta \rightarrow 0$, ce qui donne la condition limite :

$$\hat n_{21} \times (\hat{\vec E_1}) = 0$$