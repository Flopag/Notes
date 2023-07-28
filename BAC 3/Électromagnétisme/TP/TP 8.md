# TP 8 : Lignes régime harmonique (paramètre unitaires)

## Théorie

Milieu LHI ($\varepsilon$ et $\mu$ constant) sans sourus ($\vec J$ et $\rho$ nulles), on a :

$$\left\{\begin{matrix}

\vec \nabla^2\vec E - \mu\varepsilon \frac{\partial^2\vec E}{\partial t^2}=0\\
\vec \nabla^2\vec H-\mu\varepsilon\frac{\partial^2\vec H}{\partial t^2}=0

\end{matrix}\right.$$
Sous forme de phaseurs :

$$\left\{\begin{matrix}

\vec \nabla^2 \hat{\vec E} + \omega^2\mu\varepsilon \hat{\vec E}=0\\
\vec \nabla^2 \hat{\vec H} + \omega^2\mu\varepsilon \hat{\vec H}=0

\end{matrix}\right.$$

/ ! \\ $\vec E$ et $\vec H$ sont couplé ! $\vec \nabla \times \vec E = - \mu \frac{\partial \vec H}{\partial t}$ et $\vec \nabla \times \vec H = \varepsilon \frac {\partial \vec E}{\partial t}$

Onde plane progressive :

$$\left\{\begin{matrix}

\hat{\vec E} = E_0 e^{-jkz}\hat r\\
\hat {\vec H} = \frac {E_0} \eta e^{-jkz}

\end{matrix}\right.$$

où :
- $k=\omega\sqrt{\mu\varepsilon}$ est le nombre d'onde
- $\omega = 2\pi f$ est la vitesse angulaire de l'onde
- $v=\frac{\omega}{k}=\frac{1}{\sqrt{\mu\varepsilon}}$ est la vitesse de propagation
- $\eta = \frac{\hat{\vec E}_x}{\hat{\vec H_y}}=\sqrt{\frac{\mu}{\varepsilon}}$ est l’impédance caractéristique

Dans l'air :
- $jk \in \Im \rightarrow$ milieu non dissipatif
- $\eta = 377\Omega\rightarrow$ pas de déphasage (car réel)

Dans un milieu dissipatif : 
- $\varepsilon \rightarrow \tilde \varepsilon = \varepsilon'-j\left(\varepsilon''_{pol}+\frac \sigma \omega\right)$
	- où $\varepsilon''_{pol}$ est due au diélectrique non idéal et $\frac \sigma \omega$ est due a une conductivité non nul
- $jk=j\omega\sqrt{\mu \tilde \varepsilon} = \alpha + j\beta$
	- où $\alpha$ est le facteur d'atténuation et $\beta$ la vitesse de phase tel que $v_P=\frac{\omega}{\beta}$

Bon conducteur ($\varepsilon''_{pol} = 0$ et $\sigma >> \omega \varepsilon'$), alors :
- $\tilde \varepsilon = -j\frac \sigma \omega$
	- $jk=(1+j)\frac 1 \delta$
	- $\eta = (1+j-\frac 1 {\delta \sigma}) = Z_s=R_s+j\omega L_s$
	- $\delta = \sqrt{\frac 2 {\mu\omega\sigma}}$

Vecteur de Poyting :

$$\vec S = \vec E \times \vec H$$

Sa valeur moyenne sur une période (dans la direction de propagation) vaut :

$$<\vec S> = \Re\{\frac 1 2 \hat {\vec E}\times \hat {\vec H}^*\}$$

Théorème de Poyting :

$$\int_s{<\vec S> \ d\vec s} = P_{moyenne \ traversant \ s}$$

Condition de transmission :

$$\left\{\begin{matrix}

\hat n \times (\vec E_1-\vec E_2) = 0\\
\hat n \times (\vec H_1-\vec H_2) = \vec J_S\\
\hat n \times (\vec B_1-\vec B_2) = 0\\
\hat n \times (\vec D_1-\vec D_2) = \sigma_S

\end{matrix}\right.$$

/ ! \\ $\sigma_S [C/m] \ne \rho [C/m^2]$ et $\vec J_S [A/m]\ne \vec J[A/m^2]$

![](attachments/Pasted%20image%2020230728095240.png)

## Méthodes

### Puissance émise par un vecteur de Poynting $\vec S$

Utiliser le théorème de Poyting


### Calculer la valeur efficace de $\hat{\vec E}$ à partir de $\vec S$

1. Utiliser $\hat H_0=\frac {\hat E_0} \eta$ dans le théorème de Poyting
2. Isoler $|\hat E_0|$
3. Utiliser $E_{eff} = \frac{|\hat E_0|}{\sqrt{2}}$

### Sachant $E_0$ et $\sigma$, calculer la valeur moyenne de la puissance absorbé par unité de surface d'une onde qui frappe une plaque de conducteur

Expression de l'onde incidente (l'onde qui n'a pas encore touché la plaque) :

$$E_i = \left\{\begin{matrix}

\hat{\vec E} = E_0 e^{-jk_1z}\hat r\\
\hat {\vec H} = \frac {E_0} {\eta_1} e^{-jk_1z}

\end{matrix}\right.$$

Expression de l'onde réfléchie (l'onde qui a rebondi sur la plaque) :

$$E_r = \left\{\begin{matrix}

\hat{\vec E} = \rho E_0 e^{-jk_1z}\hat r\\
\hat {\vec H} = \rho \frac {E_0} {\eta_1} e^{-jk_1z}

\end{matrix}\right.$$

où $\rho$ est l'indice de réflexion

Expression de l'onde transmise (l'onde qui est rentré dans la plaque) :

$$E_t = \left\{\begin{matrix}

\hat{\vec E} = \tau E_0 e^{-jk_2z}\hat r\\
\hat {\vec H} = \tau \frac {E_0} {\eta_2} e^{-jk_2z}

\end{matrix}\right.$$

où $\tau$ est l'induce de transmission

1. Construire les conditions de transmission ($z = 0$ est la position de la plaque) :

$$(\hat E_i+\hat E_r)|_{z=0} = \hat E_t|_{z=0}$$

$$(\hat H_i+\hat H_r)|_{z=0} = \hat H_t|_{z=0}$$

2. Isoler $\tau$ et $\rho$ pour avoir leur valeurs
3. Calculer la puissance absorbé par unité de surface :

$$|<\vec S_t>|_{z=0} = |<\vec S_i>|_{z=0} - |<\vec S_r>|_{z=0}$$

### Exprimer la puissance dissipée en fonction de l'amplitude du champs magnétique à la surface du bloc  par intégration directe de la puissance dissipée par effet Joule

1. Calculer la puissance à l'aide du théorème de Poynting
2. Effet Joule :
	1. $\hat {\vec E} = E_0e^{-\frac{1+j}{\delta} z}\hat x$
	2. $\hat{\vec J} = \sigma \hat {\vec E}$
3. $P = \frac 1 2 \int_V{\Re\{\hat{\vec J}\hat{\vec E}^*\} \ dv}$