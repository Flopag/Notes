# TP 6 : La numérisation

## Théorie

### Echantillonnage

Signal échantillonnée :

$$m_{\delta(t)} = \sum_{n=-\infty}^{+\infty}{m(nT_s)\delta(t-nT_s)}$$

![](attachments/Pasted%20image%2020230603171452.png)

Condition d'échantillonnage :
- La fréquence d'échantillonnage doit être strictement supérieur au double de $W = f_{max}$ ([Théorème de Shannon](../Notion/Théorème%20de%20Shannon.md)) :

$$f_s > 2W = f_{Nyquist}$$

### La quantification et le codage

Courbe de quantification uniforme :

![](attachments/Pasted%20image%2020230603171520.png)
avec :
- $\Delta$, le pas de quantification
- $n$, le nombre de niveaux de quantification
- $B$, le nombre de bits par échantillon :

$$B=log_2(n)$$



$$Q(x)=\Delta \left\lfloor \frac{x}{\delta} + \frac{1}{2}\right\rfloor$$

Plusieurs types :
- Midtread : 0V au milieu d'une marche (horizontale)
- Midrise : 0V au milieu d'un flanc montant

## Méthodes

### Déterminer la fréquence de Nyquist d'un signal

1. Trouver le maximum de la fréquence puis le multiplier pas deux