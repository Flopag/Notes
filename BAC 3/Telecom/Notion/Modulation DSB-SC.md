# Modulation à double bande latérale et porteuse supprimée (DSB-SC)

La modulation DSB-SC est une variation de la [Modulation d'Amplitude](Modulation%20d'Amplitude.md)

Avantages :
- On a une économie de puissance par apport à la [Modulation d'Amplitude](Modulation%20d'Amplitude.md) puisqu'il n'y a pas de [Porteuse](Porteuse.md)
Inconvénient :
- L'absance de résidu de [Porteuse](Porteuse.md) peut compliquer la démodulation cohérente puisque le récepteur va devoir le produire lui même

## Modulation

En considérant le [Signal modulant](Signal%20modulant.md) $m(t)$ à transmettre et la [Porteuse](Porteuse.md) $c(t)$, on obtient le signal suivant :

$$s(t) = m(t)c(t) = A_cm(t)\cos{(2\pi f_ct)}$$