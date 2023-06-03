# Quantification

La quantification est le processus consistant à transformer un échantillon d'amplitude $m[nT_s]$ d'un message $m(t)$ pris au temps $t=nT_s$ en une amplitude $v[nT_s]$, choisie dans un ensemble fini de valeurs possible

![](attachments/Pasted%20image%2020230603205639.png)

Image montrant une quantification uniforme

![](attachments/Pasted%20image%2020230603205649.png)

Un **quantificateur** $\phi(.)$ est une application qui envoie la variable aléatoire $M$ d'amplitude continue sur une variable aléatoire discrète $V$ :

$$\phi : M \rightarrow V$$

---

**Erreur de quantification** $Q$ :

$$Q=V-M$$

---

**Bruit de quantification** $\sigma^2_Q$ :

$$\sigma^2_Q = \frac{1}{3} m_{max}^22^{-2R}$$

Avec $R$, le nombre de bit utilisé par échantillon

---

**Pas de quantification** $\Delta$ :

$$\Delta = \frac{2m_{max}}{L}$$

avec $L$, le nombre de niveau possible

---

**Rapport signal à bruit de quantification** $\frac{\sigma^2_M}{\sigma_Q^2}$ :

$$\left(\frac{S}{N}\right)^2 = \frac{\sigma^2_M}{\sigma_Q^2} = \left(\frac{3\sigma^2_M}{m^2_{max}}\right) 2^{2R}$$

---

Pour une quantification uniforme, l'ajout d'un bit supplémentaire (passage de $R$ bits à $R+1$ bits) augmente le rapport signal à bruit de $6 \ [db]$
