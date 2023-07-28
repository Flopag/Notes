# TP 6 : Champs variable (partie 1)

## Théorie

Conductance (en $[S]=[1/\Omega]$) d'un condensateur est la partie réel de l'admittence, lié aux pertes

Il y a deux contributions :
- Courant de conduction, pertes par effet joule, courant entre les armatures du condensateur : $\vec J=\sigma_{diélectrique} \vec E \rightarrow G_c$
- Polarisation diélectrique : $G_{pol}$

Dans un condensateur idéal, les pertes sont nulles : $G_c=G_{pol}=0$

### Conductance de conduction $G_c$ :

$$I = G_c \ \Delta V$$

où :
- $I$ est le courant total s'écoulant entre les armatures
- $\Delta V$ est la différence de potentiel électrique entre les armatures

On obtient donc :

$$G_c=\frac{I}{\Delta V}=\frac{\int_s{\vec J \bullet d\vec S}}{\Delta V} = \frac{\int_s {\sigma \vec E \bullet d\vec S}}{\Delta V}$$

![](attachments/Pasted%20image%2020230724152740.png)

### Perte par polarisation diélectrique :

Modélisé localement par l'ajout d'une partie imaginaire à la permittivité $\varepsilon$ (permittivité effective) :

$$\tilde \varepsilon = \varepsilon '-j(\varepsilon_{pol}'')$$

où :
- $\varepsilon ' = \varepsilon_0 \varepsilon_r$ 
- $\varepsilon_{pol}''$ modélise les pertes par polarisation diélectrique

Modélisé globalement par une conductance équivalente $G_{pol}$

### Perte totales (sur un domaine où $\varepsilon$ et $\sigma$ sont constant)

Pour un condensateur idéal (= sans perte), on a :

$$Y = j\omega C$$

où :
- $Y$ est l'admittance, $=\frac{\hat I}{\hat V}$ (régime harmonique uniquement)
- $C$ est la capacité du condensateur

On peut écrire la capacité d'un condensateur comme le produit d'un facteur géométrique $f(d)$ et d'une permittivité $\varepsilon$ :

$$C=\varepsilon f(d)$$

Si on prend en compte les pertes de conduction et de polarisation, on obtient la permittivité effective suivante :

$$\tilde \varepsilon = \varepsilon '-j(\varepsilon_{pol}''-\frac{\sigma}{\omega})$$

L'admittance devient :

$$Y=j\omega\tilde \varepsilon f(d) = \sigma f(d)+\omega \varepsilon_{pol}''f(d)+j\omega\varepsilon'f(d) = G_c+G_{pol}+j\omega C$$

Avec $G_c + G_{pol}=G_{total}$ qui est la perte total

### Autre

Régime quasi-statique $\rightarrow$ circuit localisé ($\lambda = \frac{v}{f}>> dim \ du \ circuit$) $\rightarrow$ champs $\vec E$, $\vec B$, $\vec D$ et $\vec H$ sont identique aux champs statique

Théoème d'Ampère Maxwell :

$$\oint_C{\vec H\bullet d\vec l} = \int_S{\left(\vec J+\frac{\partial \vec D}{\partial t}\right) \bullet d\vec S}$$

$$\vec \nabla \times \vec H = \vec J + \frac{\partial}{\partial t}\vec D$$

Courant de conduction :

$$I_c = \int_S{\vec J\bullet d\vec S}$$

Courant de déplacement :

$$I_D = \int_S{\frac{\partial \vec D}{\partial t} \bullet d\vec S}$$

Dérivée d'un phaseur :

$$\frac{\partial \bullet}{\partial t}\rightarrow j\omega \hat\bullet$$

## méthodes

## Déterminer la résistance électrique

Si la conductivité $\sigma$ et $\varepsilon$ sont constant dans le milieu, alors calculer $C$ ou $G_c$ suffit pour calculer l'autre à l'aide de :

$$C = \frac{G_c\varepsilon}{\sigma}$$

### Calcul de $G_c$

On doit trouver $I$ et $\Delta V$ pour utiliser la formule :

$$G_C=\frac{I}{\Delta V}$$

#### Méthode 1

1. Imposer $\Delta V$
2. Déduire $V(r)$ par Laplace (voir [TP 2](TP%202.md))
3. Calculer $\vec E$ (voir [TP 2](TP%202.md)) avec $\vec E = -\vec \nabla V$
4. Calculer $\vec J=\sigma \vec E$
5. Intégrer pour obtenir $I$ (voir [TP 4](TP%204.md)) avec $I=\int_s{\vec J \bullet d\vec S}$

#### Méthode 2

1. Imposer $I$
2. Déduire $\vec J$
3. Calculer $\vec E=\frac{\vec J}{\sigma}$
4. Déduire $\Delta V = -\int_1^2{\vec E \bullet d\vec l}$

### Déterminer l'expression du courant de déplacement

1. Calculer $\vec E$
2. $\hat{\vec D} = \varepsilon \vec E$
3. Utiliser la formule $I_D = \int_S{\frac{\partial \vec D}{\partial t} \bullet d\vec S}$ sous forme de phaseur $\rightarrow I_D = \int_S{\omega j \hat{\vec D} \bullet d\vec S}$