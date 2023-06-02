# Densité spectrale de puissance

La **densité spectrale de puissance** $\gamma_X(f)$ d'un processus aléatoire stationnaire $X(t)$ est la transformée de Fourier de sa fonction d'autocorrélation $\Gamma_{XX}(\tau)$ :

$$\gamma_X(f) = \int_{-\infty}^{+\infty}{\Gamma_{XX}(\tau) \ e^{-2\pi jf\tau} \ d\tau}$$

Elle permet donc de faire le calcul dans l'autre sens :

$$\Gamma_{XX}(\tau) = \int_{-\infty}^{+\infty}{\gamma_X(f) \ e^{2\pi jf\tau} \ df}$$

Propriétés:
- $\gamma_X(0)=\int_{-\infty}^{+\infty}{\Gamma_{XX}(\tau) \ d\tau}$
- La densité spectrale de puissance représente la répartition fréquentielle de la moyenne de la [Puissance instantanée](Puissance%20instantanée.md) :

	$$P = E\{ X^2(t) \} = \Gamma_{XX}(\tau = 0) = \int_{-\infty}^{+\infty}{\gamma_X(f) \ e^{2\pi j\tau0} \ df} = \int_{-\infty}^{+\infty}{\gamma_X(f)  \ df}$$