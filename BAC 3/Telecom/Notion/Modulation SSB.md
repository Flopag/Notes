# Modulation à bande unique (SSB)

La modulation SSB est une variation de la [Modulation d'Amplitude](Modulation%20d'Amplitude.md)

La modulation SSB permet de garder qu'une seule bande latérale dans le signal $s(t)$

## Modulation

En considérant le [Signal modulant](Signal%20modulant.md) $m(t)$à transmettre et la [Porteuse](Porteuse.md) $c(t)$, on obtient le signal suivant :

$$S(f)=U(f)H(f)$$

avec :
- $U(f) \rightleftharpoons^F u(t) = A_cm(t)\cos{(cos(2\pi f_c t))}$
- $H(f)$ est un filtre de transmittance supposé connu

A la réception, le signal en bande de base n'a subit aucune distortion à la condition que, $\forall f$ :

$$H(f-f_c)+H(f+f_c)=1$$

## Démodulation ([cohérente](Démodulation%20cohérente.md))

Même méthode que pour la [Modulation d'Amplitude](Modulation%20d'Amplitude.md)

![](attachments/Pasted%20image%2020230602095327.png)
