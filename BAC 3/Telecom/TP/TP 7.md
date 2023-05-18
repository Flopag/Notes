# Tp 7 : Transmission en bande de base (1ère partie)

## Théorie

### Mise en forme d'une onde PCM

exemple d'onde PCM : $...101101001...$

Impulsion de mise en forme $\phi (t)$
![](attachments/Pasted%20image%2020230518160949.png)

Signal après mise en forme :

$$s(t)=\sum_{k=-\infty}^{+\infty}{A_k \ \phi(t-k \ T_b)}$$

avec :
- $A_k$ l'amplitude du signal de mise en forme
- $\phi (t)$ le signal de mise en forme

![](attachments/Pasted%20image%2020230518161232.png)

### Modulation PAM

PAM-$n$ : $A_k =\{\pm 1, \pm 2, ..., \pm \frac{n}{2}\}$ avec $n$ qui doit être une puissance de deux

![](attachments/Pasted%20image%2020230518160532.png)

### Bande de base (ou de Nyquist)

![](attachments/Pasted%20image%2020230518161847.png)

$$W_b = \frac{1}{T_{sin}} = \frac{1}{2T_{imp}}$$

### Densité spectrale de puissance

Densité spectrale de puissance de $s(t)$ lorsque $A_k$ est une séquence de variables aléatoires non-corrélées :
$$\gamma_s(f)= ||\Phi (f)||^2 \ \frac{1}{T} [\sigma^2_A + \mu^2_A \sum_{m=-\infty}^{+\infty}{\frac{1}{T} \delta \ (f-\frac{m}{T})}]$$

## Méthodes

### Déterminer la bande passante minimum nécessaire pour la transmission si chaque impulsion PAM peut seulement prendre $x$ niveaux de tension différents

On a que la bande de base est  :

$$W = \frac{1}{2T_{imp}}$$

Pour une modulation PAM-$n$ :

$$T_{imp} = T_b$$

On a vu au TP 6 que $\frac{1}{T_b} = B \ f_s = \log_2{L} \ f_s$ . On a donc :

$$W = \frac{\log_2{L} \ f_s}{2}$$

### Calculer la densité spectrale de puissance du signal

La densité spectral vaut :

$$\gamma_s(f)= ||\Phi (f)||^2 \ \frac{1}{T} [\sigma^2_A + \mu^2_A \sum_{m=-\infty}^{+\infty}{\frac{1}{T} \delta \ (f-\frac{m}{T})}]$$

il faut trouver chaque termes puis les remplacer:
- $\Phi (f) = F\{ \phi (t)\} = F\{ rect(\frac{t-(T_b/2)}{T_b})\}$
- $\mu_A = E(A_k)$
- $\sigma_r^2 = E(A_k^2) - \mu_A^2$
- La somme disparait (toujours) en regardant $||\Phi (f)||^2 \ \sum_{m=-\infty}^{+\infty}{\frac{1}{T} \delta \ (f-\frac{m}{T})}$ et en trouvant les valeurs de $m$ qui annulent le tout
	- si besoin : $f(x) \delta (x-a) = f(a)  \delta (x-a)$

























