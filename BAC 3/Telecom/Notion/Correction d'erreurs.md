# Correction d'erreurs

Recherche du nombre et de la position des erreurs afin de les corriger (FEC)

## Algorithme de correction

Prémisse :
- Un [mot de code](Codage%20par%20blocs.md) $\vec c$ invalide se note $\vec r$
- Pour le corriger, on doit choisir le [mot de code](Codage%20par%20blocs.md) valide, parmi les $2^k$ [mot de code](Codage%20par%20blocs.md) valide $\vec c_j$, qui a la plus grande probabilité d'avoir été à l'origine du mot reçu $\vec r$
- On choisit le vecteur $\vec c_i$ qui vérifie la relation :

$$Prob(\vec r|\vec c_i) = max_{\vec c_j}\{ Prob(\vec r| \vec c_j) \}$$

- Dans le cas le plus simple, le vecteur $\vec c_i$ est choisi tel que (algorithme de distance minimale ou du plus proche voisin) : $Prob(\vec r| \vec c_j) = d(\vec r, \vec c_j)$

Algorithme :
1. Calcul du [syndrome](Codage%20par%20blocs.md) $\vec s = \vec r H^T$ sur base du signal reçu $\vec r$
2. Détermination du vecteur d'erreur $\vec e_i$ correspondant
3. Estimation du mot de code réel au moyen de $\vec c = \vec r + \vec e_i$ (_j'ai recopié des slide mais je trouve $\vec c = \vec r - \vec e_i$, peut-être ne typo???_)

