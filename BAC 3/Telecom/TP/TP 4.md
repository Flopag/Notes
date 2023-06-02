# TP 4 : Outils stochastiques (1ère partie)

## Théorie

### Fonction de distribution de probabilité

$$F_X(x) = p(X \leq x)$$

Propriétés :
- $F_X(x)$ est comprise entre 0 et 1
- $F_X(x)$ est une fonction monotone non-décroissante de $x$, c'est-à-dire : $F_X(x_1)\leq F_x(x_2)$ si $x_1 \leq x_2$

### Fonction de densité de probabilité

$$f_X(x) = \frac{dF_X(x)}{dx}$$

Propriétés :
- $f_X(x)$ est toujours non-négative
- $f_X(x)$ possède sous sa courbe une aire totale égale à 1 : $\int_{-\infty}^{+\infty}{f_X(\eta) \ d\eta}=1$

### Probabilité d'une intervalle

$$p(x_1 > X \leq x_2) = F_X(x_2) - F_X(x_1) = \int_{X_1}^{x_2}{f_X(x) \ dx}$$

### Cas de plusieurs variables aléatoires

#### Fonction de distribution conjointe :

$$F_{X, Y}(x, y) = p(X \leq x, Y \leq y)$$

Propriétés :
- $F_{X, Y}(x, y)$ est comprise entre 0 et 1
- $F_{X, Y}(x, y)$ est une fonction monotone non-décroissante de $x$ et $y$

#### Fonction de densité de probabilité conjointe

$$f_{X, Y}(x, y) = \frac{\partial^2 F_{X, Y}(x, y)}{\partial x \partial y}$$

Propriétés :
- $f_{X, Y}(x, y)$ est toujours non-négative
- $f_{X, Y}(x, y)$ possède sous sa courbe une aire totale égale à 1 : $\int_{-\infty}^{+\infty}{\int_{-\infty}^{+\infty}{f_{X, Y}(\eta, \nu) \ d\nu d\eta}}=1$

#### Fonction de densité marginale

$$f_X(x) = \int_{-\infty}^{+\infty}{f_{X,Y}(x, \mu) \ d\mu}$$

#### Fonction de densité conditionnelle

$$f_Y(y|x) = \frac{f_{X, Y}(x, y)}{f_X(x)}$$

#### $X$ et $Y$ statiquement indépendantes si :

$$f_Y(y|x) = f_Y(y)$$

ou

$$f_{X, Y}(x, y) = f_X(x)f_Y(y)$$

#### Correlation

$$E\{ XY \} = \int_{-\infty}^{+\infty}{\int_{-\infty}^{+\infty}{xy \ f_{X, Y}(x, y) \ dx dy}}$$

Propriétés :
- $X$ et $Y$ sont corrélé si la correlation $\neq 0$
- $X$ et $Y$ sont non-corrélé si la correlation $=0$

### Moment statiques

#### Moyenne statique

$$\mu_X(t) = E\{ X(t) \} = \int_{-\infty}^{+\infty}{xf_{X(t)}(x) \ dx}$$

#### Fonction d'auto-correlation statique

$$\Gamma_{XX}(t_1, t_2) = R{X(t_1)X(t_2)} = \int_{-\infty}^{+\infty}{\int_{-\infty}^{+\infty}{x_1x_2f_{X(t_1),X(t_2)}(x_1, X_2) \ dx_1dx_2}}$$

### Stationnarité au sens large #Important

Soit un processus aléatoire $X(t)$, stationnaire au sens stricte. Alors :

$$\mu_X(t)=\mu_X \ \ \ ,\forall t$$

$$\Gamma_{XX}(t_1, t_2) = f(t_2-t_1) \ \ \ ,\forall t_1 \ et \ t_2$$

Un processus aléatoire est stationnaire au sens large si il vérifie les deux conditions :
- Sa moyenne est indépendante du temps
- Sa fonction d'auto-correlation ne dépend que de la différence entre les temps d'observation

### Bonus

Intégrale de Gauss :

$$\int_{-\infty}^{+\infty}{e^{-ax^2} \ dx} = \sqrt{\frac{\pi}{a}}$$

Variable gaussienne de moyenne $\mu$ et de variance $\sigma$ :

$$f_X(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$

## Méthodes

### Déterminer si un processus aléatoire du type $X(t) = A + B \ t$ est stationnaire au sens large

1. Calculer la moyenne statique
	1. Réduire l'espérence totale en plusieurs petite espérance
	2. Calculer les petites espérance
	3. Tout recoller pour avoir l'espérence totale
	4. si elle est nul, on continue, sinon c'est que ce n'est pas stationnaire au sens large
2. Calculer la fonction d'auto-correlation statique
	1. Réduire l'espérence totale en plusieurs petite espérance
	2. Calculer les petites espérance
	3. Tout recoller pour avoir l'espérance totale
	4. Si elle est fonction de $t_1 - t_2$, stationnaire au sens large, sinon c'est que ce n'est pas stationnaire au sens large