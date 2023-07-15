# Loi de Biot-Savart

On considère une distribution de [Courant](Courant.md) en régime établit :

$$\frac{\partial \rho}{\partial t} = 0$$

Par [équation de continuité](Courant.md) :

$$\frac{\partial \rho}{\partial t} = 0 \rightarrow \vec \nabla \bullet \vec J$$

Le [Champ d'induction magnétique](Champ%20d'induction%20magnétique.md) produit par un [Conducteur](Conducteur.md) parcouru par un [Courant](Courant.md) $I$ :

$$\vec B(\vec r) = \frac{\mu_0}{4\pi} \int{\frac{(Id\vec l \times \hat{\vec r}_{rel})}{r^2_{rel}}} \ [T]$$

![](attachments/Pasted%20image%2020230715150150.png)

Pour une distribution volumique de [Courant](Courant.md) décrite par une [Densité de courant électrique](Densité%20de%20courant%20électrique.md) $\vec J (\vec r)$, la loi devient :

$$\vec B(\vec r) = \frac{\mu_0}{4\pi} \int{\frac{(\vec J(\vec r) \times (\vec r - \vec r'))}{|\vec r - \vec r'|^3} \ dV'}$$