# Modulation de phase (PM)

Fortement liée à la [Modulation de Fréquence](Modulation%20de%20Fréquence.md) ([Modulation angulaire](Modulation%20angulaire.md))

## Modulation

En considérant le [Signal modulant](Signal%20modulant.md) $m(t)$ à transmettre et la [Porteuse](Porteuse.md) $c(t)$, on obtient le signal suivant :

$$s(t) = A_c \cos{[2\pi f_c t + k_p m(t)]}$$

Variante en utilisant la phase :

$$A_c \cos{[2\pi (f_c + \frac{k_p}{2\pi}\frac{dm(t)}{dt})]}$$

Cette modulation est **non linéaire** contrairement à la [Modulation d'Amplitude](Modulation%20d'Amplitude.md)

## Paramètres

- $\Delta \phi(t) = \phi(t) - (2\pi f_c t + \phi_c)$
- $\beta = \max{|\Delta \phi(t)|}$ (donné par une loi)

## Analyse spectral

[Règle de Carson](Règle%20de%20Carson.md)