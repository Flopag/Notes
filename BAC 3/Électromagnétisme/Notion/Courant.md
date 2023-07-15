# Courant

Le courant électrique est la vitesse de variation de [Charge](Charge.md) :

$$I = \frac{dQ}{dt} \ [A]$$
Le courant à travers une surface vaut :

$$I = -\frac{dQ}{dt} = -\int_V(\frac{\partial \rho}{\partial t}) \ dV$$

Si on regarde le courant électrique à l'aide de [Densité de courant électrique](Densité%20de%20courant%20électrique.md), on a :

$$I = \int_S{\vec J \bullet d\vec S}$$

En utilisant le [Théorème de la divergence de Gauss](Théorème%20de%20la%20divergence%20de%20Gauss.md) :

$$I = \int_V{(\vec \nabla \bullet \vec J) \ dV}$$

En combinant le courant à travers une surface et celui utilisant la [Densité de courant électrique](Densité%20de%20courant%20électrique.md), on obtient **l'équation de continuité** :

$$\vec \nabla \bullet \vec J +\frac{\partial \rho}{\partial t}=0$$

![](attachments/Pasted%20image%2020230715144958.png)