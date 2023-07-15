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