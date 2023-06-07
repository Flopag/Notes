# Tp 9 : Codes correcteurs d'erreurs

## Théorie

### Codes blocs linéaire

Un code est systématique si le message se retrouve inchangé dans le mot de code correspondant

- Bit de parité :
	- $P=1$ si $m$ contient un nombre impaire de $1$
	- $P=0$ si $m$ contient un nombre paire de $1$
- Code bloc linéaire :

	$$\vec c = \vec m G$$

	avec 
	- $\vec m = (m_1, m_2, ..., m_k)$, le message
	- $\vec c = (c_1, c_2, ..., c_n)$, le mot de code

- Matrice génératrice d'un code systématique:

	 $$G = [P \ \ I_k] = \left(
	\begin{matrix}
		p_{11} & p_{12} & ... & p_{1(n-k)} & 1 & 0 & ... & 0 \\
		p_{21} & p_{2} & ... & p_{2(n-k)} & 0 & 1 & ... & 0 \\
		... & & & & & & ... & 0\\
		p_{k1} & p_{k2} & ... & p_{k(n-k)} & 0 & 0 & ... & 1 \\
	\end{matrix}
	\right)$$

- Matrice de contrôle de parité

	 $$H^T = \left(
	\begin{matrix}
		I_{n-k}\\
		P
	\end{matrix}
	\right)$$

- vecteur à la réception : 

	$$\vec r = \vec c + \overrightarrow{erreur}$$

- Vecteur syndrome d'erreur (si $\ne 0$), il y a une erreur) :

	$$\vec s = \vec r H^T = \vec e H^T $$

### Poids et distance de Hamming

- Poids de Hamming $w(\vec c)$ du vecteur $\vec c$ est le nombre de $1$ qu'il contient

- Distance de Hamming d'un code (bloc linéaire) : 

	$$d_{min} = \min_{\vec c_l \in C, \ \vec c_l \ne \vec 0}{w(\vec c_l)}$$

- Capacité de détection est le nombre maximum de bits erronés que l'on peut détecter :

	$$t_d = d_{min} - 1$$

- Capacité de correction est le nombre maximum de bits erronés que l'on peut corriger :

	$$t_c = \left\lfloor \frac{d_{min} - 1}{2} \right\rfloor$$

## Méthodes


### Calculer la matrice génératrice $G$ et la matrice $H$ de contrôle de parité.

1. Trouver tout les valeurs des bits de parité $P$ en fonction de $\vec m$ et construire $\vec c = (P | \vec m)$
2. Utiliser $\vec c = \vec m G$ pour établir $G$ (de dimension $k \times n$)
3. Utiliser :

	$$H^T = \left(
	\begin{matrix}
		I_{n-k}\\
		P
	\end{matrix}
	\right)$$

### Quelle est la distance de Hamming de ce code?

1. Calculer tout les poids de Hamming
2. La distance de Hamming est le minimum de ces poids ($\ne 0$)

### Combien peut-on détecter et/ou corriger d'erreurs?

1. Utiliser : $t_d = d_{min} - 1$ et $t_c = \left\lfloor \frac{d_{min} - 1}{2} \right\rfloor$

### Vérifier si un message s'est déroulée sans erreurs

1. Calculer le Vecteur syndrome d'erreur $\vec s$ et regarder si il est nul

### Retrouver un message avec erreurs

1. Construire le tableau de l'algorithme de correction de l'erreur ($k$ colonnes et 2 lignes)
	1. Remplir la première ligne de chaque valeur de $\vec c$ possible
	2. Remplir la deuxième ligne de vecteur syndrome $\vec s$ avec une erreur choisis arbitrairement (le but est de tester si l'erreur choisis est celle qui a été produite)
2. Trouver la bonne valeur de l'erreur (trouver une bonne réponse par syndrome)

technique : trouver l'erreur qui mène a chaque valeur de $c$ possible (en partant de $c$) puis prendre ceux qui ont le moins de 1
