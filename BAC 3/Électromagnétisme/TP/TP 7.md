# TP 7 : Champs variable (partie 2)

## Théorie

Equations de Maxwell :

$$\left\{\begin{matrix}

\vec \nabla \times \vec E = -\frac{\partial \vec B}{\partial t}&(1)\\
\vec \nabla \times \vec B = \vec J + \frac{\partial \vec D}{\partial t} = j_{total}&(2)\\
\vec \nabla \bullet \vec B = 0&(3)\\
\vec \nabla \bullet \vec D = \rho_{libre}&(4)

\end{matrix}\right.$$

vecteur de pointing :

$$\vec S(x,y,z,t) = \vec E(x,y,z,t)\times\vec H(x,y,z,t) \ \left[\frac{W}{m²}\right]$$

### Perte pas effet Joule

$\vec E$ dans un milieu de conductivité $\sigma \ne 0$ et non parfait $\rightarrow$ $\vec J = \sigma \vec E$

sachant $\vec E$ produit $\Delta V$, $\vec J$ produit $I$ et $\Delta V = RI$, alors :

$$I=G_c\Delta V$$

où $G_c = \frac{1}{R} = \frac{\int_s {\vec J d\vec S}}{\Delta V} =\frac{\int_s {\sigma\vec E d\vec S}}{\Delta V}$

La puissance vaut :

$$P = \Delta V I$$

### Perte par polarisation diélectrique

On les modélise localement par l'ajout d'une partie imaginaire à la permittivité (/ ! \\ c'est une modélisation, le véritable $\varepsilon$ n'a pas changé) :

$$\tilde \varepsilon = \varepsilon'+j\varepsilon''_{polarisation}$$

où $\varepsilon' = \varepsilon_0\varepsilon_r$

On les modélise par une conductance équivalente $G_{pol}$ :

$$Y = j\omega C$$
où $C=\varepsilon f(d)$

Si on couple les deux, on obtient :

$$Y = j\omega (\varepsilon'-j\varepsilon''_{pol}) f(d)$$
ou, autrement dit :

$$Y=j\omega C+G_{pol}$$

### Les deux pertes en même temps

On définit :

$$\tilde \varepsilon = \varepsilon'-j(\varepsilon''_{pol}+\frac \sigma \omega)$$

Ce qui donne :

$$Y=j\omega C + G_{pol}+G_c$$

### Perte par [hystérésis](../Notion/Matériaux%20magnétique.md)

$$\vec E_{1 \ cycle} = \oint{\vec H\bullet d\vec B}$$

## Méthodes

### Construire un circuit équivalent

1. Construire le circuit

### Calculer l’impédance $Z$ d'un circuit équivalent

1. Construire le circuit équivalent
2. Faire la somme de toutes les impédance $Z$ d'une boucle
	1. Pour une résistance : $Z=R$
	2. Pour un condensateur : $Z = \frac{1}{j\omega C}$

### Calculer le courant $\hat I$ d'un circuit équivalent

1. Construire le circuit équivalent
2. Calculer $Z$
3. $\hat I = \frac{\hat V}{Z}$ (/ ! \\ dans certain cas, le courant ne circule pas dans la boucle)

### Calculer la conductance $G$

$$G =\Re\{Y\}$$

$$G_c = \frac{1}{R} = \frac{\int_s {\vec J d\vec S}}{\Delta V} =\frac{\int_s {\sigma\vec E d\vec S}}{\Delta V}$$

