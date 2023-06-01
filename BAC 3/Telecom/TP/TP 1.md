# Tp 8 : Transmission en bande de base (2ème partie)

## Théorie

### Définitions et notations

Transformée de Fourier direct :

$$G(f) = \int_{-\infty}^{+\infty}{g(t) \ e^{-2\pi jft} \ dt}$$

### Quelques signaux fondamentaux

Fonction sinc :

$$sinc(t) = \frac{\sin{(\pi t)}}{\pi t}$$

Fonction échelon :

$$u(t) = 
\left\{
\begin{array} 
	1 & t > 0\\
	-1 & t<0	
\end{array}
\right.$$

### Bonus

$$\sin{x} = \frac{e^{jx}-e^{-jx}}{2j}$$

$$\cos{x} = \frac{e^{jx}+e^{-jx}}{2}$$

## Méthodes

### Calculez la transformée de Fourier de l'impulsion sinus donnée à la figure suivante
1. Trouver l'expression de la fonction $g(t)$ à transformée à partir du dessin
2. Utiliser $g(t)$ dans la transformée de Fourier direct pour avoir $G(f)$
