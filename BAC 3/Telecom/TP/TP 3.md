# TP 3 : Les modulations analogiques (2ème partie)

## Théorie

### Modulation FM

Signal modulé :

$$s(t) = A_c cos\left[ 2\pi f_c t + 2 \pi k_f \int_0^t{m(\tau) \ d\tau} \right]$$

avec $k_f$, la sensibilité en fréquence du modulateur

### modulation FM d'une onde cosinusoïdale

Déviation de fréquence :

$$\Delta f = k_f A_m$$

indice de modulation :

$$\beta = \frac{\Delta f}{f_m}$$

Bande passante du signal modulé FM (règle de Carson) :

$$B_T \simeq 2(\Delta f + f_m)$$

### Bonus

$$cos(A+B) = cos(A) cos(B)-sin(A)sin(B)$$

$$cos(a \ sin(b)) \simeq 1$$

$$sin(a \ sin(b)) \simeq a \ sin(b)$$

$$sin(A)sin(B) = \frac{1}{2} [cos(A-B)-cos(A+B)]$$

$$cos^2(\alpha) = \frac{1+cos(2\alpha)}{2}$$

## Méthodes

### Déterminer le spectre du signal modulé en phase :
1. Calculer $\int_0^t{m(\tau) \ d\tau}$
2. Remplacer dans l'équation du signal modulé d'une modulation FM
3. Faire en sorte d'avoir $\beta$
4. Utiliser : $cos(A+B) = cos(A) cos(B)-sin(A)sin(B)$
5. Simplifier à l'aide des formules : $cos(a \ sin(b)) \simeq 1$ et $sin(a \ sin(b)) \simeq a \ sin(b)$
6. Transformation de Fourier direct de ce qu'il reste

### Déterminez une approximation de la bande passante d'un signal FM en utilisant la règle de Carson
1. Calculer $\Delta f = k_fA_m$
2. Remplacer dans la règle de Carson : $B_T \simeq 2(\Delta f + f_m)$