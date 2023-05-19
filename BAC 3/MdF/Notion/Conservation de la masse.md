# Conservation de la masse (ou Continu)

> Rien ne se perd, rien ne se crée, tout se transforme.

- Formule de base :

	$$\frac{dm}{dt}=\frac{d}{dt} \int_V{\rho \ dV} = 0$$

- Formule après application du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) :

	$$\frac{\partial \rho}{\partial t} + \vec{\nabla} \bullet (\rho \vec{U}) = 0$$

	Sous sa forme indicielle :
	$$\frac{\partial \rho}{\partial t} + \frac{\partial}{\partial x_j} (\rho u_j) = 0$$

	Sous sa forme alternative :
	$$\frac{D \rho}{D t} + \rho \frac{\partial  u_j}{\partial x_j} = 0$$