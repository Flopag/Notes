# Méthodes numérique

## Méthode des différences finies

### Prémisse

on introduit :
- une fonction à une deux variable $u(x, t)$
- deux pas de maille $\Delta x$ et $\Delta t$
- $s$ est une rapport de pas différent selon le cas (exemple pour une [équation de diffusion](Equation%20de%20diffusion.md) : $s=\frac{\Delta t}{(\Delta x)²}$)
- $u_j^n \simeq u(j\Delta x, n \Delta t)$ / ! \\ $n$ n'est pas un exposant mais un indice
- Erreur de la solution $\varepsilon(x,t)$
	- Hypothèse : il est intégrable et carré intégrable par apport à $x$
	- $\varepsilon_k (x_j,t_n) = \hat \varepsilon(k,t_n)e^{-ikx_j}=$ mode $k$ de l'erreur

Il y a trois standard pour approximé la dérivée $\frac{\partial }{\partial x}u(j\Delta x, n\Delta t)$ :
- La différence arrière : $\frac{u_j^n-u_{j-1}^n}{\Delta x}$
- La différence avant : $\frac{u^n_{j+1}-u^n_j}{\Delta x}$
- La différence centré : $\frac{u^n_{j+1}-u^n_{j-1}}{2\Delta x}$

Il y a trois standard pour approximé la dérivée $\frac{\partial }{\partial t}u(j\Delta x, n\Delta t)$ :
- La différence arrière : $\frac{u_j^n-u_j^{n-1}}{\Delta x}$
- La différence avant : $\frac{u^{n+1}_j-u^n_j}{\Delta x}$
- La différence centré : $\frac{u^{n+1}_j-u^{n-1}_j}{2\Delta x}$

On introduit deux types d'erreurs :
- **Erreur de troquature** : erreur due aux termes $O(x)$ et $O(x²)$ qu'on a négligé
	- Local : sur un terme
	- Global : sur la solution finale (plus on fait de pas, plus on accumule une erreur)
- **Erreur d'arrondie** : a cause de l'ordinateur qui n'a as une précision infinie

Il y a trois type de schéma :
- **Explicite** : se base uniquement sur le passé
- **implicite** : se base sur le passé et le future
- **Semi-explicite** : un mélange d'implicite et explicite

### Stabilité

Le schéma est stable si il existe une constante $C$ tel que :

$$\lim_{n\rightarrow +\infty}{||\varepsilon(x,t_n)||²} \le C||\varepsilon(x,t_0)||²$$

Annalyse de Von Neumann :
1. On injecte un mode d'erreur arbitraire ($\varepsilon_k (x_j,t_n)$) dans notre équation différence
2. On simplifie toutes les exponentiels, pour obtenir une relation de récurrence entre les $\hat\varepsilon(k,t_n)$ qui dépendent de $k$
3. Le schéma est stable si aucun des modes ne diverge

### Comment choisir les [Condition initiale](Condition%20initiale.md) si on en a besoin de plusieurs ?

Écrire le schéma pour $n=0$

## Méthode des éléments finis

La méthode consiste à :
1. Discrétiser le domaine d'étude en plusieurs éléments (triangle, etc )
2. Choisir une approximation de la solution en écrivant cette solution comme une combinaison linéaire de fonction de base (souvent des polynômes) qui ont un support local sur les éléments
3. Choisir un nombre fini de [Fonction test](Fonction%20test.md) (souvent les mêmes que les fonctions de base)

![](attachments/Pasted%20image%2020230721111914.png)

![](attachments/Pasted%20image%2020230721120125.png)

![](attachments/Pasted%20image%2020230721120146.png)

## Méthodes stationnaire

Permet de résoudre l'équation matriciel $Ax=b$

La forme générale de la méthode d'écrit :

$$x_n=x_{n-1}+k^{-1}(b-Ax_{n-1})$$

On décomposer $A$ en :
- Une diagonal $D$
- Une triangulaire inférieur $L$
- Une triangulaire supérieur $U$

### Méthode de Jacobi

*(Voir slides 09b_Laplace_approx p11)* 

$$K=D$$

### Méthode de Gauss-Seidel

*(Demo slides 09b_Laplace_approx p13)* : 

$$K=D+L$$

## Méthode de Krylov

Permet de résoudre l'équation matriciel $Ax=b$ sans avoir besoin de stocker $A$ (qui peut etre très grand)

Les méthodes de Krylov sont des méthodes non stationnaire qui fonctionne par projection dans des sous espaces de Krylov

Un sous espace de Krylov est un espace généré par des vecteurs de base qui sont le membre de droite (donc $b$) et des application de puissance successive de $A$ sur le membre de droite ($b$), ils ont donc la forme :

$$b, Ab, A(Ab) , a(A(Ab)), ...$$

On a donc pas besoin de stocker la matrice $A$ mais seulement son application

Cette méthode est liée au théorème de Caley-Hamilton :

> Soit une matrice $A (m\times m)$ avec le polynôme caractéristique : 
> 
> $$p(\lambda)=det(\lambda I-A)=\lambda^m+c_{m-1}\lambda^{m-1}+...+c_1\lambda+c_0$$
> Alors :
>
>$$A^m+c_{m-1}A^{m-1}+...+c_1A+c_0I=0$$

Il y a plusieurs méthodes en fonction de l'équation :

![](attachments/Pasted%20image%2020230718144056.png)

### Conjugate Gradients

#### Notations

Une matrice réel symétrique et définie positive $A\in \Re^{m\times m}$

On veut résoudre :

$$Ax=b$$

La solution exacte du système est :

$$x_* = A^{-1}b$$

Le $n^{eme}$ sous espace de Krylov généré par $b$ est défini comme :

$$K_n = K_n(A,b) = <b, Ab, ..., A^{n-1}>$$

On défini la norme $A$ de $x$ comme :

$$||x||_A = \sqrt{x^TAx}$$

#### Qu'est ce que la méthode ?

C'est un système de formule de recurrence qui vont générer une suite d'itéré qu'on va appeler $x_n\in K_n$, à l'étape $n$, l'itéré appartiendra au $n^{ème}$ sous espace de Krilov, a chaque pas $n$ la norme $A$ de l'erreur $e_n = x_*-x_n$ est la plus petite possible

Donc, la méthode minimise $||e_n||_A$ a chaque itération :

$$||e_n||_A\le ||e_{n-1}||_A$$

Il y a trois propriétés :
- $K_n = <x_1, x_2, ..., x_n> = <p_0, p_1, ..., p_{n-1}> = <r_0, r_1, ..., r_{n-1}> = <b, Ab, ..., A^{n-1}b>$
- $r_n^Tr_j=0 \ \ (j < n)$
- $p_n^TAp_j=0 \ \ (j < n)$

*(demo et explications slides 10_CG p15)*

#### Etapes

1. On choisit une approximation initiale $x_0$ (le plus simple, est de prendre $x_0=0$)
2. On défini un vecteur $r_0$ comme le vecteur résidu (si $x_0 = 0$, alors $r_0 = b$)
3. On défini un vecteur $p_0$ comme la direction des sous espace (initialement $p_0=r_0$)
4. Début de la boucle $for(int \ n = 1; cond; ++n)$ :
	1. On calcule une longueur de pas $\alpha_n = \frac{r_{n-1}^Tr_{n-1}}{p_{n-1}^TAp_{n-1}}$
	2. On calcule la prochaine estimation de la solution $x_n = x_{n-1}+\alpha_np_{n-1}$
	3. On calcule le prochain vecteur résidu $r_n = r_{n-1}-\alpha_np_{n-1}$
	4. On calcule un nombre $\beta_n = \frac{r_n^Tr_n}{r_{n-1}^Tr_{n-1}}$
	5. On calcule le prochain vecteur direction $p_n=r_n+\beta_np_{n-1}$

## Méthode SVD (Singular Value Decomposition)

Fonctionne pour n'importe quel matrice (même rectangulaire)

Pourquoi étudier le SVD ?
- Il intervient dans énormément d'algorithmes
- Il a un intérêt conceptuelle, permet d'avoir un autre point de vu de l'algèbre linéaire

### Interprétation géométrique

On considère une [Matrice](Matrice.md) $A$ réel et de [rang plein](Matrice.md), son application sur $x$ donne donc une hyperellipse :

![](attachments/Pasted%20image%2020230722112648.png)

Une hyperellipse est le résultat d'une dilatation en appliquant des facteurs de dilation $\sigma_1, ..., \sigma_m$ dans des directions normales, dons les vecteurs unitaires sont $u_1, ..., u_m$. Le vecteur $\{\sigma_i, u_i\}$ correspond au **demi axe principaux** de l’ellipse

![](attachments/Pasted%20image%2020230722113053.png)

Le [rang](Matrice.md) de $A$ est le nombre de $\sigma_i$ non nul

Caractérisation de la [Matrice](Matrice.md) $A$ à partir des éléments géométriques, à l'aide de :
- **Valeur singulière** : les longueurs des demi axes principaux $\rightarrow \sigma_1, ..., \sigma_n$ (ils sont numéroté par ordre décroissant)
- **Vecteur singulier à gauche** : les vecteurs de norme unitaire orienté selon les demi axe principaux $\rightarrow u_1, ..., u_n$ (la numérotation correspond à leur valeur singulière)
- **vecteur singulier à droite** : les vecteurs $v_1, ..., v_n$ dont l'image par application de la [Matrice](Matrice.md) $A$ sont les demis axes principaux

![](attachments/Pasted%20image%2020230722113933.png)

### Interprétation formel

A partir de l'interpretation géométrique, on comprend que :

$$Av_j=\sigma_ju_j \ \ \ \ , 1\le j\le n$$

Sous forme [matriciel](Matrice.md) (sous **forme réduite**) :

$$AV=\hat U\hat\Sigma$$

![](attachments/Pasted%20image%2020230722114417.png)

On sait que $V$ est [unitaire](Matrice.md), on peut donc transformé l'équation précédente (c'est toujours la forme réduite) :

$$A=\hat U \hat \Sigma V^*$$

![](attachments/Pasted%20image%2020230722114930.png)

Pour avoir une **décomposition complète**, on va rendre $\hat U$ [unitaire](Matrice.md) (en rajoutant des colonnes orthonormé avec toutes les autres colonnes) et rendre $\hat \Sigma$ compatible à $U$ (en ajoutant des lignes remplis de $0$) :

![](attachments/Pasted%20image%2020230722115226.png)

![](attachments/Pasted%20image%2020230722115521.png)

La décomposition complète peut être utilisé pour une [Matrice](Matrice.md) $A$ à [rang non plein](Matrice.md)  (contrairement à la décomposition réduite)

Définition de la décomposition SVD :

> Soit une matrice complexe $A$ de dimension $n \times m$ quelconque ($A$ ne doit pas être nécessairement de rang plein). Ce qu'on appel, décomposition en valeur singulière (SVD) est la factorisation de la matrice $A$ sous la forme :
> 
> $$A=U\Sigma V^*$$
>
> ![](attachments/Pasted%20image%2020230722120350.png)


*(démo que toutes matrice possède une décomposition SVD, slides 11_SVD p35)*

La décomposition n'est pas unique, les valeurs singulière sont déterminé de manière unique, par contre les vecteurs singulier sont déterminé de manière unique au signe près à condition que la [Matrice](Matrice.md) $A$ soit [carré](Matrice.md) et qu'elle a des valeurs singulière toutes distincte

### Approximation de [rang](Matrice.md) 

La [matrice](Matrice.md) $A$ peut être écrit sous la forme d'une somme :

$$A=\sum_{j=1}^r{\sigma_ju_jv_j^*}$$

Pour tous $k \le r$ qui définit le somme suivante :

$$A_k=\sum_{j=1}^k{\sigma_ju_jv_j^*}$$

alors :

$$||A-A_k||_2 = \sigma_{k+1}= \min_{rang(B)=k}{||A-B||_2}$$

Cela dit que l'approximation $A_k$ de $A$ est la meilleur possible pour un rang $k$ (dans le sens $||.||_2$)

*(demo slides 12_SVD p28)*