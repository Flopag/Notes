# Equation de Maxwell

$$
\left\{\begin{matrix}

\vec \nabla \times \vec E = -\frac{\partial \vec B}{\partial t}&(1)\\
\vec \nabla \times \vec B = \vec J + \frac{\partial \vec D}{\partial t} = j_{total}&(2)\\
\vec \nabla \bullet \vec B = 0&(3)\\
\vec \nabla \bullet \vec D = \rho_{libre}&(4)

\end{matrix}\right.
$$

## Interpretation

### (1)

C'est la **loi de Faraday-Lenz** :

$$\oint_{boucle}{\vec E \bullet d\vec l} = -\frac{\partial}{\partial t}\int_{S}{\vec B\bullet d\vec S}$$

$$force \ électromotrice \ induite = -\frac{\partial}{\partial t} flux \ magnétique \ embrassé$$

$$V_{fem} = -\frac{\partial \Phi}{\partial t}$$

Une variation du flux magnétique embrassé par la boucle induit une force électromotrice

Dans le cas d'un [Conducteur](Conducteur.md), la force électromotrice ce traduit en [Courant](Courant.md) induit, produisant une [Induction magnétique](Induction%20magnétique.md) qui s'oppose à la variation de flux magnétique initiale

![](attachments/Pasted%20image%2020230719142922.png)

**[Courant](Courant.md) de Foucault** est le [Courant](Courant.md) induit par la force électromotrice :

$$V_{fem} = \frac{\partial \Phi}{\partial t} \rightarrow IR=V_{fem} \rightarrow P = \frac{v_{fem}}{R}$$

![](attachments/Pasted%20image%2020230719144043.png)

### (2)

$$\oint_{boucle}{\vec H \bullet d\vec l} = \int_S{\left(\vec J+\frac{\partial \vec D}{\partial t}\right) \bullet d\vec S}$$

où $\frac{\partial \vec D}{\partial t}$ est la densité de courant de déplacement

### (3)

$$\int_S{\vec B\bullet d\vec S} = 0$$

### (4) 

$$\int_S{\vec D \bullet d\vec S} = Q_{libre}$$

Très utile quand il y a des symétries

## Les équations de Maxwell en utilisant les [phaseurs](Phaseur.md)

On introduit le [Phaseur](Phaseur.md) :
$$\vec E(x,y,z,t)=\vec E(x,y,z)cos(\omega t+\phi) \rightarrow \hat {\vec E}(x,y,z) = \vec E(x,y,z)e^{j\phi}$$

La dérivée temporelle :

$$\frac{\partial}{\partial t}\rightarrow j\omega$$

Equations de Maxwell :

$$\left\{\begin{matrix}

\vec \nabla \times\hat{\vec E} = -j\omega\hat{\vec B}&(1)\\
\vec \nabla \times \hat {\vec H}=\hat {\vec J}+j\omega \hat{\vec D}&(2)\\
\vec \nabla \bullet \hat{\vec B}=0&(3)\\
\vec \nabla \bullet \hat {\vec D} = \hat \rho_{libres}&(4)

\end{matrix}\right.$$