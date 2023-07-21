# Equation d'onde

Dans un [Matériau LHI](Matériau%20LHI.md), en utilisant les [Equation de Maxwell](Equation%20de%20Maxwell.md), on trouve les équations d'ondes :

$$
\left\{\begin{matrix}

\vec \nabla^2\vec E-\mu\varepsilon\frac{\partial² \vec E}{\partial t²}=\mu\sigma \frac{\partial \vec E}{\partial t}+\vec \nabla \frac{\rho_{libre}}{\varepsilon}\\
\vec \nabla^2\vec H-\mu\varepsilon\frac{\partial^2\vec H}{\partial t^2}=\mu\sigma \frac{\partial \vec H}{\partial t}

\end{matrix}\right.
$$

Interprétation :
- Les termes en $\mu\varepsilon$ proviennent de la densité de courant de déplacement $\frac{\partial \vec D}{\partial t}$ non-dissipatif
- Les termes en $\mu\sigma$ proviennent de la densité de courant de conduction $\sigma\vec E$ dissipatif

*(Demo slides chap5-ondes p1)*

On a l'équation d'onde à résoudre :

$$(\nabla^2-\mu\varepsilon\frac{\partial^2}{\partial t^2})\vec E = \vec 0$$

On voit que la vitesse de propagation $v = \left(\frac{1}{\mu\varepsilon}\right)^{1/2} = \frac{c}{\sqrt{\mu_r\varepsilon_r}}=\frac{c}{n}$, avec $c$ la vitesse de la lumière et $n$ l'indice de réfraction du milieu

On résout l'équations d'ondes pour obtenir :

$$\vec H(z,t) = \hat y\frac{kE_0}{\omega \mu} \ cos(\omega t - k z)$$

*(Demo slides chap5-ondes p6)*

**Impédance intrinsèque du milieu de propagation** :

$$\eta = \frac{E_x}{H_y} = \frac{\omega\mu}{k}=v\mu=\sqrt{\frac{\mu}{\varepsilon}}$$

[Vecteur de Poynting](Vecteur%20de%20Poynting.md) instantané :

$$\vec S(z,t)=\vec E \times \vec H = \hat z \frac{E^2_0}{\eta} \ cos^2(\omega t-kz)$$

![](attachments/Pasted%20image%2020230721170554.png)

## Résolution d'une équation d'onde à une dimension

voir le cours de [mathématique appliqué](../../Math%20App/Notion/Equation%20d'onde.md)

Forme de l'équation d'onde :

$$\left(\frac{\partial^2}{\partial z^2}-\frac{1}{v^2}\frac{\partial^2}{\partial t^2}\right)A(z,t) = 0$$

Solution générale (avec $f$ et $g$ des fonction quelconque) :

$$A(z,t)=f(z-vt)+g(z+vt)=onde \ progressive + onde \ rétrograde$$

Une **onde harmonique** est de la forme :

$$A(z,t)=A_0 \ cos(\omega t-kz+\phi)$$

avec :
- $A_0$ l'amplitude
- $\omega = 2\pi f$ la pulsation
- $f$ la fréquence
- $k=\frac{2\pi}{\lambda}$ le nombre d'onde
- $\lambda$ la longueur d'onde
- $v=\frac{\omega}{k}$ la vitesse de phase

Une onde harmonique en terme de [Phaseur](Phaseur.md) :

$$\hat A(z) = A_0 e^{-jkz+j\phi}$$

On utilise une onde harmonique car c'est plus simple et c'est linéaire

Un **paquet d'ondes** prend donc la forme :

$$A(z,t) = \Re\left\{\int_{-\infty}^{+\infty}{\hat A_k \ e^{-jkz} e^{j\omega t} dk}\right\}$$