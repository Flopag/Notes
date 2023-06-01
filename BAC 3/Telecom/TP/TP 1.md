# Tp 1 : La transformée de Fourier

## Théorie

### Définitions et notations

Transformée de Fourier direct :

$$G(f) = \int_{-\infty}^{+\infty}{g(t) \ e^{-2\pi jft} \ dt}$$

### Propriétés

Multiplication dans le domaine temporel :

$$g_1g_2 \rightleftharpoons^F G_1 \otimes G_2$$

Multiplication dans le domaine fréquentiel :

$$g_1 \otimes g_2 \rightleftharpoons^F G_1  G_2$$

Egalité de Parseval :

$$Energie = \int_{-\infty}^{+\infty}{||g(t)||^2 \ dt} = \int_{-\infty}^{+\infty}{||G(f)||^2 \ df}$$

### La fonction Delta de Dirac

propriété :

$$g(t) \otimes \delta(t+fc) = g(t+fc)$$

### Quelques signaux fondamentaux

Fonction sinc :

$$sinc(t) = \frac{\sin{(\pi t)}}{\pi t}$$

Fonction échelon :

$$u(t) = 
\left\{ 
\begin{array} 
	&1 & t > 0\\
	-1 & t<0	
\end{array}
\right.$$

### Transformées de Fourier

$$sinc (at) \rightleftharpoons^F \frac{1}{a} rect\left(\frac{f}{a}\right)$$

$$\sin{(2\pi f_c t)} \rightleftharpoons^F \frac{1}{2j} [\delta(f-f_c) - \delta(f+f_c)]$$

### Bonus

$$\sin{x} = \frac{e^{jx}-e^{-jx}}{2j}$$

$$\cos{x} = \frac{e^{jx}+e^{-jx}}{2}$$

## Méthodes

### Calculez la transformée de Fourier de l'impulsion sinus donnée à la figure suivante
1. Trouver l'expression de la fonction $g(t)$ à transformée à partir du dessin
2. Utiliser $g(t)$ dans la transformée de Fourier direct pour avoir $G(f)$
	- Par calcul direct si $g(t)$ est simple
	- Par multiplication dans le domaine temporel

## Déterminer l'énergie du signal $g(t)$
1. Si besoin, calculer la transformée de fourier $G(f)$ si $g(t)$ est trop complexe à intégrer puis utiliser l'égalité de Parseval
