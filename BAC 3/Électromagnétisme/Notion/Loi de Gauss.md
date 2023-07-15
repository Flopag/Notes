# Loi de Gauss

## Pour le [Champ électrique](Champ%20électrique.md)

Le [Flux du champ électrique](Flux%20du%20champ%20électrique.md) $\phi_E$ au travers d'une surface fermée $S$ est proportionnel à la [Charge](Charge.md) totale contenue dans le volume délimité par $S$ : 

$$\phi_E = \int_S{\vec E \ \bullet \ d\vec S} = \frac{Q_V}{\varepsilon_0}$$

avec $\vec S = \vec n \ S$ dans la direction perpendiculaire extérieur à la surface fermée 

*Il est bien de prendre la surface de Gauss $S$ perpendiculairement au [Champ électrique](Champ%20électrique.md) $\vec E$*

![](attachments/Pasted%20image%2020230712150603.png)

### Forme différentielle

En utilisant le [Théorème de la divergence de Gauss](Théorème%20de%20la%20divergence%20de%20Gauss.md), on obtient :

$$\vec \nabla \bullet \vec E = \frac{q}{\varepsilon_0}$$

### Dans un [Matériau LHI](Matériau%20LHI.md)

$$\phi_E = \int_S{\vec D \ \bullet \ d\vec S} = \frac{Q_V}{\varepsilon}$$

## Pour le [Champ d'induction magnétique](Champ%20d'induction%20magnétique.md)

Pour toutes surface fermée délimitant un volume $V$ arbitraire :

$$\int_S{\vec B(\vec r)\bullet d\vec S} = 0$$

Par [Théorème de la divergence de Gauss](Théorème%20de%20la%20divergence%20de%20Gauss.md) :

$$\int_V{\vec \nabla \bullet \vec B \ dV} = 0$$

Puisque $V$ est quelconque :

$$\vec \nabla \bullet \vec B = 0$$