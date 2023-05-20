# Equations de Navier Stokes

Les équation de Navier Stokes sont simplement la combinaison de la [Conservation de la quantité de mouvement](Conservation%20de%20la%20quantité%20de%20mouvement.md) et de la [Conservation de la masse](Conservation%20de%20la%20masse.md) après l'utilisation du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) en [Incompressible](Fluide%20Incompressible.md):

$$
\left\{
     \begin{array}{ll}
		\vec{\nabla} \bullet \vec{U} = 0\\
	     \frac{\partial \vec U}{\partial t} + \vec{\nabla} \bullet (\vec{U}\vec{U}) = \frac{1}{\rho} \vec{F}+ \frac{1}{\rho} \vec{\nabla} \bullet p + \nu \Delta \vec U
     \end{array}
\right.
$$