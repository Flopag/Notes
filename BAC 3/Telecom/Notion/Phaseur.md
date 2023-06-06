# Phaseur

Le phaseur permet de réécrire une grandeur sinusoidale

Grandeur sinusoïdale $x(t)$ $\rightarrow$ phaseur $\hat X$ :

$$x(t)=X \ cos(\omega t+\theta) \rightarrow \hat X=Xe^{j\theta}$$

Phaseur $\hat X$ $\rightarrow$ grandeur sinusoïdale $x(t)$ :

$$x(t) = Re(\hat X \ e^{j\omega t}) = Re(X \ e^{j(\omega t + \theta)}) = X \ cos(\omega t+\theta)$$

Dérivée d'un phaseur :

$$\frac{\partial (\hat X \ e^{j\omega t})}{\partial t} = j \omega \hat X \ e^{j\omega t}$$
