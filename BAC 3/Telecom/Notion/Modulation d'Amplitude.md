# Modulation d'amplitude (AM)

![](attachments/Pasted%20image%2020230601103618.png)

## Modulation

La **modulation d'amplitude** est le processus par lequel l'amplitude de la [Porteuse](Porteuse.md) $c(t)$ varie linéairement avec le [Signal modulant](Signal%20modulant.md) $m(t)$. On a donc le signal :

$$s(t) = A(t) \ cos{(2\pi f(t) t + \phi (t))}$$

qui devient :

$$s(t) = A(t) \ cos{(2\pi f_c t)}$$

avec $A(t) = A_c(1+k_a m(t))$ , $|k_am(t)| < 1$ (sinon surmodulation)

## Analyse spectral

La [Transformée de Fourier](Transformée%20de%20Fourier.md) de $s(t)$ est :

$$S(f) = \frac{A_c}{2} [\delta(f-f_c) + \delta(f+f_c)] + \frac{k_aA_c}{2} [M(f-f_c) + M(f+fc)]$$

Avec :
- $\delta(f-f_c) + \delta(f+f_c)$, la porteuse
- $M(f-f_c)$, le [Signal modulant](Signal%20modulant.md) décalé de $f_c$ vers la droite
- $M(f+f_c)$ ,le [Signal modulant](Signal%20modulant.md) décalé de $f_c$ vers la gauche

![](attachments/Pasted%20image%2020230601104450.png)

## Démodulation ([cohérente](Démodulation%20cohérente.md))

étapes :
1. multiplier le signal $s(t)$ par la [Porteuse](Porteuse.md) : $s(t)\cos{(2\pi f_c t)}$
2. faire un filtrage passe bas pour supprimer ce qu'on ne veut pas

![](attachments/Pasted%20image%2020230602091638.png)

## Variantes

- [Modulation DSB-SC](Modulation%20DSB-SC.md)
- [Modulation QAM](Modulation%20QAM.md)
- [Modulation SSB](Modulation%20SSB.md)
- [Modulation VSB](Modulation%20VSB.md)