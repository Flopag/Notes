# TP 7 : Variable séparable (partie 1)

## Théorie



## Méthodes

### Méthode des variable séparable

1. Poser $u(x,y)=X(x)Y(y)$
2. Injecter dans l'équation pour séparer les termes en $X$ et $Y$, on obtient une équation de la forme : $L_s(X)=L_s(Y)=\lambda$
3. Former deux EDO, une en mélangeant $L_s(X)$ avec $\lambda$ et l'autre en mélangeant $L_s(Y)$ avec $\lambda$
4. Résoudre (sans utiliser les conditions auxilliaire) les deux ODE tout en discutant de $\lambda$ (les différente solutions en fonction des parties de $\lambda$ sont appelé solution propre)
5. Pour la suite, seul les solution propre qui vérifie les [Condition limites](../Notion/Condition%20limites.md) **homogène** peuvent être gardé pour la suite (on obtient une expression et des valeurs de $\lambda$) (/ ! \\ les [Condition limites](../Notion/Condition%20limites.md) non homogène seront utilisé à l'étape 7)
6. Construire $u(x,y)=X(x)Y(y)$ en sommant les solutions propre 
	- Exemple : $u(x,y)=X(x)Y(y)|_{\lambda < 0} + X(x)Y(y)|_{\lambda = 0} + X(x)Y(y)|_{\lambda > 0}$
7. Déterminer les constantes restante à l'aide de la [Condition initiale](../Notion/Condition%20initiale.md) et de la théorie des séries de Fourier :
	- $\phi(x) = \sum_n^\infty{F_n \ sin(n\pi x)} \rightarrow F_m = 2 \int_{-\infty}^{+\infty}{\phi(x) \ sin(m\pi x) \ dx}$ (peut être résolut par partie)