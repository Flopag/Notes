# Modulation en quadrature de phase (QAM)

La modulation QAM est une variation de la [Modulation d'Amplitude](Modulation%20d'Amplitude.md)

Avantages :
- Cette modulation permet de transmettre deux signaux simultanément sur une même bande de fréquence

## Modulation

En considérant les [Signal modulant](Signal%20modulant.md) $m_1(t)$ et $m_2(t)$ à transmettre et la [Porteuse](Porteuse.md) $c(t)$, on obtient le signal suivant :

$$s(t) = A_c m_1(t) \cos{(2\pi f_ct)} + A_c m_2(t)\sin{(2\pi f_c t)}$$

## Démodulation ([cohérente](Démodulation%20cohérente.md))

Même méthode que pour la [Modulation d'Amplitude](Modulation%20d'Amplitude.md) mais en utilisant $cos()$ pour récupérer $m_1(t)$ et $sin()$ pour récupérer $m_2(t)$ et de deux filtres passe bas.
