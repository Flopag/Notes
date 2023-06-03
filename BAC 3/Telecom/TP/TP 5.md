# TP 5 : Outils stochastiques (2ème partie)

## Théorie

### Filtrage d'un processus aléatoire

#### Sortie du filtre : processus aléatoire

$$Y(t) = h(t) \otimes X(t) = \int_{-\infty}^{+\infty}{h(\tau) X(t-\tau) d\tau}$$

Propriétés :
- Si le filtre est linéaire, la sortie a la même distribution que l'entrée

#### Moyenne

$$\mu_Y = E\{ Y(t) \} = \mu_X H(0)$$

#### Variance

$$\sigma^2_Y=E\{ (Y-\mu_Y)^2 \}$$

$$\sigma^2_Y=\Gamma_{YY}(0) \ \ \ ,si \ \mu_Y = 0$$

#### Fonction d'auto-corrélation

$$\Gamma_{YY}(t_1, t_2) = E\{ Y(t_1)Y(t_2) \}$$

$$\Gamma_{YY}(\tau) = \int_{-\infty}^{+\infty}{\gamma_Y(f) \ e^{2\pi jf\tau} \ df}$$

#### Densité spectrale de puissance

$$\gamma_Y = \int_{-\infty}^{+\infty}{\Gamma_{YY}(\tau) \ e^{-2\pi jf\tau} \ d\tau}$$

**Théorème de Wiener-Kintchine** :

$$\gamma_Y(f) = ||H(f)||^2 \gamma_X(f)$$

### Bruit blanc gaussien

$$\Gamma_{XX}(\tau)=\frac{N_0}{2}\delta(t)$$

$$\gamma_X(f) = \frac{N_0}{2}$$

## Méthodes

### Faire $h(t) \otimes X(t)$

1. Ecrire $h(t) \otimes X(t) = \int_{-\infty}^{+\infty}{h(\tau) X(t-\tau) d\tau}$
2. changer les bornes de l'intégrale à l'aide de $h(\tau)$
3. poser $u = t-\tau$