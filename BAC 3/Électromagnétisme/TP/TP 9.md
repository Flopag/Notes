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

En basse fréquence, $I$ est uniforme sur une épesseur de peau $\delta$

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

Pour une ligne a faible perte ($R << \omega L, G << \omega c$) :

$$Z_0 = \sqrt{\frac L C}$$

$$\alpha = \frac 1 2 (G Z_0+ \frac R {Z_0})$$

$$\beta = \omega \sqrt{LC}$$

Pour le cas générale :

$$Z_0 = \sqrt{\frac{R+j\omega L}{G+j\omega C}}$$

$$\gamma = \sqrt{(R+j\omega L) (G+j\omega C)}$$

## Méthodes