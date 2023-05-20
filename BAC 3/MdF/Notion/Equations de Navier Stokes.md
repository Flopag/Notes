# Equations de Navier Stokes

Les équation de Navier Stokes sont simplement la combinaison de la [Conservation de la quantité de mouvement](Conservation%20de%20la%20quantité%20de%20mouvement.md) et de la [Conservation de la masse](Conservation%20de%20la%20masse.md) après l'utilisation du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) :

$$
\left\{
     \begin{array}{ll}
		\frac{\partial \rho}{\partial t} + \vec{\nabla} \bullet (\rho \vec{U}) = 0\\
	     \frac{\partial}{\partial t} (\rho \vec U) + \vec{\nabla} \bullet (\rho \vec{U}\vec{U}) = \vec{F}+\vec{\nabla} \bullet (\mathbf{\tau} - p \mathbf{I})
     \end{array}
\right.
$$