# Conservation de la quantité de mouvement dans un repère inertiel

- Formule de base :
	$$\frac{d}{dt} \int_V{\rho \vec{U} \ dV} = \sum_i{}\vec{F_i}$$
- Formule après application du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) :

	$$\frac{\partial}{\partial t} (\rho \vec U) + \vec{\nabla} \bullet (\rho \vec{U}\vec{U}) = \vec{F}+\vec{\nabla} \bullet (\mathbf{\tau} - p \mathbf{I})$$

	Sous sa forme indicielle :

	$$\frac{\partial}{\partial t}(\rho u_i) + \frac{\partial}{\partial x_j} (\rho u_i u_j) = F_i - \frac{\partial p}{\partial x_i} + \frac{\partial \tau_{ij}}{\partial x_j}$$

	$$\frac{\partial}{\partial t}(\rho u_i) + \frac{\partial}{\partial x_j} (\rho u_i u_j) = F_i - \frac{\partial p}{\partial x_i} + \frac{\partial (\xi \varepsilon_V^,\delta_{ij}+2\mu \varepsilon_{ij}^,)}{\partial x_j}$$

	Sous sa forme alternative :

	$$\frac{D u_i}{Dt} = \frac{1}{\rho} \left(F_i - \frac{\partial p}{\partial x_i} + \frac{\partial \tau_{ij}}{\partial x_j} \right)$$

	Sous sa forme adimensionnel :

	$$\frac{L_c}{u_ct_c} \frac{\partial (\bar \rho \bar u_i)}{\partial \bar t} + \frac{\partial (\bar \rho \bar u_i \bar u_j)}{\partial \bar x_j}= \frac{g L_c}{u_c^2} \bar F_i - \frac{\Delta p_c}{\rho_c u_c^2} \frac{\partial \bar p}{\partial \bar x_i} + \frac{\nu_c}{u_cL_c} \frac{\partial \bar \varepsilon_{ij}^,}{\partial \bar x_j}$$

- Formule après application du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) d'un [Fluide Incompressible](Fluide%20Incompressible.md) :

$$\frac{\partial \vec U}{\partial t} + \vec{\nabla} \bullet (\vec{U}\vec{U}) = \frac{1}{\rho} \vec{F}+ \frac{1}{\rho} \vec{\nabla} \bullet p + \nu \Delta \vec U$$