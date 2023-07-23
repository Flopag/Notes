# Vecteur de Poynting

Le vecteur de Poynting $\vec S$ représente la propagation :

$$\vec S(x,y,z,t) = \vec E(x,y,z,t)\times\vec H(x,y,z,t) \ \left[\frac{W}{m²}\right]$$

En utilisant des [Phaseur](Phaseur.md) :

$$<\vec S> (x,y,z) = \frac{1}{2}\Re\{\hat {\vec E}(x,y,z)\times \hat {\vec H}^*(x,y,z)\}$$

## Théorème de Poynting : Conservation de l'énergie

*(voir slides chap4-Maxwell p12)*

Théorème :

$$-\int_V{\left(\vec H\bullet \frac{\partial \vec B}{\partial t}+\vec E\bullet \frac{\partial \vec D}{\partial t}\right) \ dV}=\int_S{(\vec E\times\vec H)\bullet d\vec S}+\int_V{\vec J \bullet \vec E \ dV}$$

Interpretation :
- $\int_V{\left(\vec H\bullet \frac{\partial \vec B}{\partial t}+\vec E\bullet \frac{\partial \vec D}{\partial t}\right) \ dV}$ décrit le taux de variation par unité de temps de l'énergie emmagasinée par le champs électromagnétiques dans le volume $V$ (dans une [Matériau LHI](Matériau%20LHI.md))
- $\int_V{\vec J \bullet \vec E \ dV}$ décrit la puissance dissipé par effet Joule dans le volume $V$

## Vecteur de Poynting moyenné sur une période

On définit les [Phaseur](Phaseur.md) $\hat{\vec E}$ et $\hat{\vec H}$, pour une onde progressive :

$$\left\{\begin{matrix}

\hat {\vec E} = \hat xE_0e^{-jkz}\\
\hat{\vec H} = \hat y \frac{E_0}{\eta} e^{-jkz}

\end{matrix}\right.$$

où $k=\frac{\omega}{v}=\omega \sqrt{\mu\varepsilon}$ et $\eta = \sqrt{\frac{\mu}{\varepsilon}}$

On a donc :

$$<\vec S> = \frac{1}{2} \Re\{\hat{\vec E}\times\hat{\vec H}^*\} = \hat z\frac{E_0^2}{2\eta}$$

## Solution générale de l'[Equation d'onde](Equation%20d'onde.md) dans un isolant

$$\left\{\begin{matrix}

\hat{\vec E} = \hat x\left(\hat E_+e^{-jkz}+\hat E_-e^{jkz}\right)\\
\hat{\vec H} = \hat y\left(\frac{\hat E_+}{\eta}e^{-jkz}-\frac{\hat E_-}{\eta}e^{jkz}\right)

\end{matrix}\right.$$

On peut voir qu'il y a un signe $-$, ce signe représente l'onde rétrograde. Il suffit de changer le sans de $\vec H$ pour changer le sens de la propagation (règle de la main droite, $\vec S = \vec E \times \vec H$)

## Solution générale progressive de l'[Equation d'onde](Equation%20d'onde.md) dans un [Conducteur](Conducteur.md)

$$\left\{\begin{matrix}

\hat{\vec E} = \hat x E_0 e^{-jkz}\\
\hat{\vec H} = \hat y \frac{E_0}{\eta} e^{-jkz}

\end{matrix}\right.$$

où :
- $k=\omega \sqrt{\mu \tilde \varepsilon}$
- $\eta = \sqrt{\frac{\mu}{\tilde \varepsilon}}$
- $\tilde \varepsilon = \varepsilon(1-j\frac{\sigma}{\omega \varepsilon})$ est la permittivité effective

On peut insérer dans l'équation générale, $\gamma =jk = \alpha+j\beta$ :

$$\left\{\begin{matrix}

\hat{\vec E} = \hat x E_0 e^{-\gamma z}\\
\hat{\vec H} = \hat y \frac{E_0}{|\eta|} e^{-\gamma z} e^{-j\phi_\eta}

\end{matrix}\right.$$
où :
- $\alpha$ est le coefficient d’amortissement 
- $\eta = |\eta| e^{j\phi_\eta}$ 

On peut voir que $\vec H$ à un retard de phase $\phi_\eta$ par apport à $\vec E$

Dans le cas d'un milieu a faible [conductivité](Conducteur.md) ($\sigma << \omega \varepsilon$), la vitesse de propagation est indépendante de la fréquence et la constante d'atténuation est indépendante de la fréquence *(demo slides chap5-ondes p17)*

Dans le cas d'un [bon conducteur](Conducteur.md) ($\sigma >> \omega \varepsilon$), la vitesse de propagation varie fortement avec la fréquence, pareil pour la constante d'atténuation. On y définis l'**épaisseur de peau** *(demo slides chap5-ondes p18)* : 

$$\delta = \sqrt{\frac{2}{\omega\sigma\mu}}$$

On en déduit $\gamma = \frac{1}{\delta} + j\frac{1}{\delta}$

On à donc la solution générale qui devient  *(demo slides chap5-ondes p19)* :

$$\left\{\begin{matrix}

\hat{\vec E} = \hat x E_0 e^{-(1+j)z/\delta}\\
\hat{\vec H} = \hat y E_0 \frac{\sigma\delta}{\sqrt{2}}e^{-(1+j)z/\delta}e^{-j\pi/4}

\end{matrix}\right.$$

![](attachments/Pasted%20image%2020230723152425.png)