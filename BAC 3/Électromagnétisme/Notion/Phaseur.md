# Phaseur

Soit :

$$V(t)=V_0 \ cos(\omega t+\phi)$$

On le transforme :

$$V(t) = \Re\{\hat Ve^{j\omega t}\}$$

où $\hat V = V_0 \ e^{j\phi}$ ($V_0 = |\hat V|$ et $\phi =arg(\hat V)$)

![](attachments/Pasted%20image%2020230721145348.png)

*(demo slide chap4-Maxwell p20)*

## Propriétés

- $|\hat V|$ est l'amplitude de $V(t)$
- le phaseur de la dérivée temporelle de $V(t)$ est $j\omega \hat V$
- on peut choisir l'origine dans le temps

## Théorème de la moyenne

Si $W(t)$ est le produit de deux grandes harmoniques $V(t)$ et $I(t)$ :

$$W(t)=V(t)I(t)$$

La moyenne sur une période $T$ vaut :

$$<W> = \frac{1}{T}\int_0^T{W(t) \ dt} = \frac{V_0I_0}{2}cos(\phi_V-\phi_I) = \frac{1}{2}\Re\{\hat V\hat I^*\}$$