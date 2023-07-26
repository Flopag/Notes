# Déplacement électrique

On considère un système contenant des [Charge](Charge.md) [libres](Conducteur.md) et [liées](Conducteur.md). Le déplacement électrique $\vec D$ peut être défini comme :

$$\vec D = \varepsilon_0\vec E+\vec P \left[\frac{C}{m²}\right]$$

La divergence de $\vec D$ ne dépend que des [Charge](Charge.md) libre :

$$\vec \nabla \bullet \vec D = \rho_{libre}$$

Après application du [Théorème de la divergence de Gauss](Théorème%20de%20la%20divergence%20de%20Gauss.md) :

$$\int_S{\vec D\bullet d\vec S}=Q_{libre}$$

/ ! \\ $\vec D$ n'a pas les même propriété que le [Champ électrique](Champ%20électrique.md) $\vec E$, $\vec D$ ne dérive pas d'un potentiel

*(Demo ch 2 p34)*

## Condition limite

$$\hat n_{21} \bullet (\vec D_1-\vec D_2) = \sigma_s$$
*(Demo ch 6 p1)*

![](attachments/Pasted%20image%2020230717152934.png)

Si on est dans le cas d'un [Conducteur parfait](Conducteur.md) dans le milieu 2, on a une conductivité $\sigma \rightarrow \infty$  et donc l'[épaisseur de peau](Effet%20de%20peau.md) est $\delta \rightarrow 0$, ce qui donne la condition limite :

$$\hat n_{21} \bullet (\hat{\vec D_1}) = \sigma_s$$