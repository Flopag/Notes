# Guide d'onde

Un guide d'onde permet de forcer une onde à aller dans une direction choisie et de filtrer les amplitudes

## Guide d'onde : deux plaques parallèle

On a $\vec E$ qui est perpendiculaire au plaque et dans le sens donné par $\sigma_s$ et $\vec H$ qui est parallèle au plaque et dans le sens donné par $\vec J$ . On a donc une propagation $\vec S$ parallèle au plaque 

![](attachments/Pasted%20image%2020230726112343.png)

$\sigma_s$ et $\vec J$ sont donné par l'onde :

![](attachments/Pasted%20image%2020230726112951.png)

[Tension](Potentiel%20électrique.md) entre les deux plaques :

$$V(z,t)=\int_{P1}^{P2}{\vec E \bullet d\vec l} = aE_x(z,t)$$
Ne dépend donc pas du chemin suivit (peut être considéré comme électrostatique car $-\frac{\partial \vec B}{\partial t} = 0$)

*(demo slides chap7 p4)*

![](attachments/Pasted%20image%2020230726113540.png)

Courant (peut être considéré magnéto-statique car $\partial \vec D / \partial t$ = 0) :

$$I(z,t) = bH_y(z,t)$$

Expression de $V$ et $I$ dans le cas d'une onde progressive :

$$\left\{\begin{matrix}

\hat V(z) = aE_0e^{-jkz}\\
\hat I(z) = \frac{bE_0}{2\eta}e^{-jkz}\\
Z_0 = \frac{\hat V(z)}{\hat I_(z)} = \eta \frac a b

\end{matrix}\right.$$

Puissance transporté le long de $z$ :

$$P = \int{<S_z> dxdy} = ab \frac {E_0^2} {2\eta}$$

Equation de propagation dans le domaine temporelle :

$$\left\{\begin{matrix}

\left(\frac{\partial V}{\partial z}\right) = -L \left(\frac{\partial I}{\partial t}\right)\\
\left(\frac{\partial I}{\partial z}\right) = -C \left(\frac{\partial V}{\partial t}\right)\\
C = \varepsilon(\frac a b) = capacité \ unitaire\\
L = \mu(\frac a b) = inductance \ unitaire

\end{matrix}\right.$$
