# Tp 8 : Transmission en bande de base (2ème partie)

## Théorie

### Récepteur numérique

![](attachments/Pasted%20image%2020230519170920.png)

### Implémentation du filtre adapté

Réponse impulsionnelle du filtre adapté :
$$h(t)=\alpha \phi(T_b-t)$$

Par convolution :
$$y(t) = x(t) \otimes h(t)$$

### Probabilité d'erreur

Dans le cas NRZ :
$$P_e = \frac{1}{2} erfc\left( \sqrt{\frac{E_b}{N_0}} \right)$$
$$E_b = A^2 T_b$$

avec :
- $E_b = \int_0^{T_b}{P \ dt} = A^2 T_b$ (si NRZ), l'énergie du signal par bit
- $N_0$, la densité spectrale de puissance du bruit blanc gaussien

### Bonus

- $(a + b) \ \otimes \ c = a \ \otimes \ c + b \ \otimes \ c$
- $a \otimes b = b \otimes a$
- $a(kt) \otimes b(lt) = \int_{-\infty}^{+\infty}{a(kt)g(l(t-\tau)) \ d\tau}$
- $h(t-a) \otimes g(t-b) = \left[ h(u)\otimes g(u) \right]_{u=t-a-b}$

## Méthodes

### Déterminer l'allure du signal à la sortie du filtre adapté

1. Calcul (dessin) de l'onde binaire $g(t) = \sum_{k=-\infty}^{+\infty}{A_k \ \phi(t-kT)}$ correspondant à la séquence de bits obtenue au récepteur (sur base des valeurs des symboles $A_k$, de l'onde de mise en forme $\phi(t)$)
2. Calcul de la réponse impulsionnelle du filtre adapté $h(t)=\alpha \phi(T-t)$
3. Calcul du produit de convolution de la réponse impulsionnelle du filtre adapté avec l'onde de mise en forme $p(t)=h(t)\otimes \phi (t)$
4. Calcul (dessin) de la sortie du filtre adapté $y(t)= \sum_{k=-\infty}^{+\infty}{A_k p(t-kT)}$ (ou $y(t) = x(t) \otimes h(t)$)
5. Échantillonnage de la sortie du filtre adapté $y(nT)$

### Déterminer la probabilité d'erreur

1. Déterminer $\sqrt{\frac{E_b}{N_0}}$
2. $P_e = \frac{1}{2} erfc\left( \sqrt{\frac{E_b}{N_0}} \right)$

### Déterminer le débit binaire maximal transmissible si on impose une probabilité d'erreur maximal

1. Déterminer  $\frac{E_b}{N_0}$ à l'aide de l'erreur maximal
2. Déterminer $T_b$
3. $R_b = 1/T_b$