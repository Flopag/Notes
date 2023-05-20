# Equations d'Euler

Les équation de Navier Stokes sont simplement la combinaison de la [Conservation de la quantité de mouvement](Conservation%20de%20la%20quantité%20de%20mouvement.md) et de la [Conservation de la masse](Conservation%20de%20la%20masse.md) après l'utilisation du [Théorème de transport de Raynold](Théorème%20de%20transport%20de%20Raynold.md) en [Fluide Parfait](Fluide%20Parfait.md) :

$$
\left\{
     \begin{array}{ll}
		\frac{D \rho}{D t} + \rho \frac{\partial  u_j}{\partial x_j} = 0\\
	     \frac{D u_i}{Dt} = \frac{1}{\rho} \left(F_i - \frac{\partial p}{\partial x_i} \right)
     \end{array}
\right.
$$