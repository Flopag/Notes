### Processus stationnaire au sens large

## Conditions

Soit un processus aléatoire $X(t)$, stationnaire au sens stricte. Alors :

$$\mu_X(t)=\mu_X \ \ \ ,\forall t$$

$$\Gamma_{XX}(t_1, t_2) = f(t_2-t_1) \ \ \ ,\forall t_1 \ et \ t_2$$

Un processus aléatoire est stationnaire au sens large si il vérifie les deux conditions :
- Sa moyenne est indépendante du temps
- Sa fonction d'auto-correlation ne dépend que de la différence entre les temps d'observation

## Filtrage

Soit $X(t)$ up processus stochastique stationnaire au sens large, $H(f)$ la transmittance d'un filte linéaire et $Y(t)$ le processus à la sortie du système linéaire (filtre)

Propriétés :
- Théorème : $\mu_Y = \mu_X \ H(f=0)$
- $Y(t)$ est un processus stationnaire au sens large
- [Théorème de Wiener-Kintchine](Théorème%20de%20Wiener-Kintchine.md) : $\gamma_Y(f) = ||H(f)||^2 \gamma_X(f)$