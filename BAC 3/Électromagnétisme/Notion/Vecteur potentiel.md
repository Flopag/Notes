# Vecteur potentiel

Le vecteur potentiel $\vec A$ est défini comme :

$$\vec B = \vec \nabla \times \vec A$$

Cela donne aussi :

$$\vec \nabla \bullet \vec A = 0$$

A l'aide du [Théorème d'Ampère](Théorème%20d'Ampère.md), on obtient :

$$\vec \nabla^2 \vec A = - \mu_0 \vec J$$

**Équation de poisson** :

$$\vec \nabla^2 A_{x, y, z} = -\mu_0 J_{x,y,z}$$

Par analogie au [Potentiel électrique](Potentiel%20électrique.md) :

$$\vec A(\vec r) = \frac{\mu_0}{4\pi} \int_V{\frac{\vec J(\vec r')}{|\vec r - \vec r'|} \ dV'}$$

## Induction générée par une spire microscopique de [Courant](Courant.md) $I$ , de rayon $a$

$$\vec A(\vec r) = \frac{\mu_0}{4\pi}\frac{\vec m \times \vec r}{r^3}$$

où :
- $\vec m =I\pi a^2 \hat z$ est le **moment dipolaire**
- $r >> a$

Si on considère plusieurs spire microscopique dans un volume, on peut introduire le **vecteur d'aimantation** $\vec M$ qui est le moment dipolaire magnétique pas unité de volume :

$$\vec M(\vec r_{\alpha}) = \lim_{\Delta V \rightarrow 0}{\sum_{i \in \alpha}{\frac{\vec m_i}{dV}}}$$

On peut exprimer le vecteur potentiel en fonction du vecteur d'aimantation :

$$\vec A (\vec r) = \frac{\mu_0}{4\pi}\int_V{\frac{\vec M(\vec r')\times (\vec r - \vec r')}{|\vec r - \vec r'|³}dV'}$$

## Représentation en terme de [Courant](Courant.md) liées

$$\vec A(\vec r) = \frac{\mu_0}{4\pi} \int_V{\frac{\vec J_{liées}(\vec r')}{|\vec r - \vec r'|} \ dV'}+\frac{\mu_0}{4\pi} \int_S{\frac{\vec K_{liées}(\vec r')}{|\vec r - \vec r'|} \ dV'}$$

où :
- $\vec J_{liées} = \vec \nabla \times \vec M$ est une [Densité de courant](Densité%20de%20courant%20électrique.md) de polarisation en surface
- $\vec K_{liées} = \vec M \times \vec n$ est une [Densité de courant](Densité%20de%20courant%20électrique.md) de polarisation à la surface du matériau