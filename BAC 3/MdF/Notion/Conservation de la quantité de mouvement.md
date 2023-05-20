# Conservation de la quantité de mouvement dans un repère inertiel

- Formule de base :
	$$\frac{d}{dt} \int_V{\rho \vec{U} \ dV} = \sum_i{}\vec{F_i}$$
- Formule après application du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) :

	$$\frac{\partial}{\partial t} (\rho \vec U) + \vec{\nabla} \bullet (\rho \vec{U}\vec{U}) = \vec{F}+\vec{\nabla} \bullet (\mathbf{\tau} - p \mathbf{I})$$

	Sous sa forme indicielle :

	$$\frac{\partial}{\partial t}(\rho u_i) + \frac{\partial}{\partial x_j} (\rho u_i u_j) = F_i - \frac{\partial p}{\partial x_i} + \frac{\partial \tau_{ij}}{\partial x_j}$$

	Sous sa forme alternative :

	$$\frac{D u_i}{Dt} = \frac{1}{\rho} \left(F_i - \frac{\partial p}{\partial x_i} + \frac{\partial \tau_{ij}}{\partial x_j} \right)$$

- Formule après application du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) d'un [Fluide Incompressible](Fluide%20Incompressible.md) :

$$\frac{\partial \vec U}{\partial t} + \vec{\nabla} \bullet (\vec{U}\vec{U}) = \frac{1}{\rho} \vec{F}+ \frac{1}{\rho} \vec{\nabla} \bullet p + \nu \Delta \vec U$$