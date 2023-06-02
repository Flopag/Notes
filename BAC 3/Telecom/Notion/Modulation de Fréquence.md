# Modulation de fréquence (FM)

Fortement liée à la [Modulation de Phase](Modulation%20de%20Phase.md) ([Modulation angulaire](Modulation%20angulaire.md))

## Modulation

En considérant le [Signal modulant](Signal%20modulant.md) $m(t)$ à transmettre et la [Porteuse](Porteuse.md) $c(t)$, on obtient le signal suivant :

$$s(t) = A_c \cos{[2\pi (f_c+k_f \ m(t))]}$$

Variante en utilisant la phase :

$$A_c \cos{[2\pi f_c t + 2\pi k_f \int_0^t{m(\tau) d\tau}]}$$

Cette modulation est **non linéaire** contrairement à la [Modulation d'Amplitude](Modulation%20d'Amplitude.md)

## Paramètres

- $\Delta f(t) = f(t) - f_c$
- $\Delta f = \max{|\Delta f(t)|}$ (est donnée par une loi)

## Analyse spectral

[Règle de Carson](Règle%20de%20Carson.md)