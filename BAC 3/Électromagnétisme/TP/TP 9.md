# TP 9 : Ligne régime harmonique (paramètre unitaires, description)

## Théorie

Deux conducteurs qui transportent un signal sur une longueur $L \ge \lambda$ $\rightarrow$ circuit distribué

TEM : $\vec E$ et $\vec H$ sont perpendiculaire à la direction de propagation $\rightarrow$ équation des télégraphiste

On peut séparer le circuit distribué en plein de circuit localisé de longueur $dz << \lambda$ :


$$\left\{\begin{matrix}

\frac{\partial \hat V(z)}{\partial z} = -Z(\omega)\hat I(z)\\
\frac{\partial \hat I(z)}{\partial z} = -Y(\omega)\hat V(z)

\end{matrix}\right.$$

où $Z=R+j\omega L$ et $Y = G+j\omega C$

avec :
- $C$ : capacité associée à la distribution du champ électrique
- $L$ : somme des inductances interne et externe, associées à la distribution du champ magnétique respectivement à l'intérieur et entre les conducteurs
- $R$ : du aux courants s'écoulant selon $\hat z$ et associé aux pertes ohmiques et en particulier à l'effet de peau dans les conducteurs aux hautes fréquences
- $G$ : du aux courants s'écoulant selon $\hat x$ et $\hat y$, associé aux pertes ohmiques et à la tangente $\delta$ du diélectrique entre les conducteurs

![](../Questions/attachments/Pasted%20image%2020230727092134.png)

En haute fréquence, $I$ est uniforme dans le conducteur

En basse fréquence, $I$ est uniforme sur une épaisseur de peau $\delta$

Solution des équation des télégraphiste :

$$\left\{\begin{matrix}

\hat V (z) = \hat V_+ e^{-\gamma z}+\hat V_-e^{\gamma z}\\
\hat I (z) = \frac{\hat V_+}{Z_0} e^{-\gamma z}-\frac{\hat V_-}{Z_0}e^{\gamma z}

\end{matrix}\right.$$


$$\gamma =\sqrt{ZY} = j\omega\sqrt{L C}$$

$$Z_0 = \sqrt{\frac Z Y} = \sqrt{\frac{ L}{C}}$$

Pour une ligne idéale ($R=0$, $G=0$) :

$$Z_0=\sqrt{Z}$$

$$\alpha = 0$$

$$\beta = \omega\sqrt{LC}$$

Pour une ligne a faible perte ($R << \omega L, G << \omega C$) :

$$Z_0 = \sqrt{\frac L C}$$

$$\alpha = \frac 1 2 (G Z_0+ \frac R {Z_0})$$

$$\beta = \omega \sqrt{LC}$$

Pour le cas générale :

$$Z_0 = \sqrt{\frac{R+j\omega L}{G+j\omega C}}$$

$$\gamma = \sqrt{(R+j\omega L) (G+j\omega C)}$$

## Méthodes

### Cette ligne travaille-t-elle en régime de haute ou de basse fréquence ?

Basse fréquence si l'épaisseur de peau $\delta = \sqrt{\frac 2 {\omega\mu\sigma}}$ est plus grande que le rayon du cable

### Cette ligne travaille-t-elle en régime de faible pertes ?

Faible perte si $R << \omega L$ et $G << \omega C$

### Déterminer la vitesse de phase

$$v_p = \frac \omega \beta$$

où $\beta = \Im\{\gamma\}$

### Déterminer les paramètre unitaire $C$, $L$, $R$ et $G$, l'impédance caractéristique $Z_0$ et le coefficient d'atténuation

1. Haute fréquence ou basse fréquence?
2. Calculer $Y=j\omega\tilde \varepsilon f(d)$
	1. où 
	2. $\tilde \varepsilon = \varepsilon' - j(\varepsilon''_{pol} + \frac \sigma \omega)$
	3. $C = \Im\{\frac Y \omega\}$ (à vérifier)
	4. $G = \Re\{Y\}$
3. Calculer $R=R_{conducteur intérieur} + R_{conducteur extérieur}$ 
	1. $R_i$ sont calculer à l'aide de la loi de Pouillet : $R = \frac 1 {\sigma \delta \Delta y}$
	2. où
	3. $\delta = rayon$ si $\delta > rayon$
	4. $\Delta y = 2\pi r$ (pour un cercle)
4. Calculer $L$ comme dans le [TP 5](TP%205.md) ($L_{tot} = \sum{L_i}$)
5. Faible perte, idéal ou cas générale ?
6. Calculer $Z_0$ et $\alpha$ en fonction du point 5