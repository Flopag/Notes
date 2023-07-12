# Système d'EDP du première ordre

## Caractérisation

On considère une [EDP](EDP.md) du première ordre généralisé et constitué de $N$ [Variable dépendante](Variable%20dépendante.md) :

$$\textbf u_t+\textbf A(x,t,\textbf u)\textbf u_x = \textbf h(x,t,\textbf u )$$

avec $\textbf u$, le vecteur contenant les [Variable dépendante](Variable%20dépendante.md)

Le cette [EDP](EDP.md) peut être transformé en système de la forme :

$$\partial_t u_i+\sum_{j=1}^{N}{A_{ij}\partial_xu_j}-h_i=0$$

On cherche une combinaison linéaire de ces équations. Pour ce faire, on multiplie chaque équation par $\sigma_i$ (à déterminer) et puis on les somme :

$$\sum_{i=1}^N{\left[\sigma_i\left(\partial_t u_i+\sum_{j=1}^{N}{A_{ij}\partial_xu_j}-h_i\right)\right]}=0$$

On simplifie le système en utilisant le delta de Kroenecker :

$$\sum_{j=1}^N{\left[\left(\sum_{i=1}^N{\sigma_i\delta_{ij}}\right)\partial_t+\left(\sum_{i=1}^N{\sigma_i A_{ij}}\right)\partial_x\right] u_j} = \sum_{i=1}^N{\sigma_ih_i}$$

Les termes dans les crochets correspondent à des dérivées directionnelles (gradient projeté sur une direction)

On cherche une condition dans lequel toutes ces dérivées directionnelles pourraient avoir la même direction. Alors, toutes les inconnues seraient dérivée par apport à la même variable. On passerait donc d'une [EDP](EDP.md) a une EDO (équation différentiel ordinaire)

Les termes dans les crochets deviennent :

$$\sigma_j(\partial_t+l \ \partial_x) = \sigma_j\sqrt{1+l²} \ \partial_s$$

Avec $l$ la pente de la [courbe caractéristique](Equation%20de%20transport.md)

On veut avoir les termes dans les crochets qui ont la même pente $l$ (pour chaque $j$) :

$$\frac{\left(\sum_{i=1}^N{\sigma_i A_{ij}}\right)}{\left(\sum_{i=1}^N{\sigma_i\delta_{ij}}\right)} = l \rightarrow \left(\sum_{i=1}^N{\sigma_i A_{ij}}\right) - l \ \left(\sum_{i=1}^N{\sigma_i\delta_{ij}}\right) = 0$$

Mise sous forme matriciel :

$$(\textbf A^T - l \ \textbf I)\pmb\sigma = 0$$

Qui revient a rechercher les valeurs propres de la matrice $\pmb A^T$

Enfin, on peut caractériser le système en fonction des valeurs propres et des vecteurs propres de $\pmb A$ :
- Si toutes les valeurs propres de $\pmb A$ sont réels et les vecteurs propre indépendant $\rightarrow$ système **hyperbolique**
- Si toutes les valeurs propres de $\pmb A$ sont complexes et les vecteurs propre indépendant $\rightarrow$ système **elliptique**
- Si toutes les vecteurs propres de $\pmb A$ ne sont pas indépendant $\rightarrow$ système **parabolique**

## Système d'EDP du première ordre à partir d'une [EDP quasi-linéaire](EDP.md)

Il suffit de crée de nouvelles [Variable dépendante](Variable%20dépendante.md)

Exemple :

On a une [EDP quasi-linéaire du deuxième ordre](EDP.md) :

$$u_xu_{xx}+u_y³u_{xy}+(tan \ u)u_{yy}=f(u, u_x, u_y)$$

On définit :
- $p=u_x$
- $q=u_y$

On obtient :

$$
\left\{\begin{array}a

p \ p_x+q³ \frac{(p_y + q_x)}{2}+(tan \ u)q_y=f(u, p, q)\\
q_x-p_y=0\\
u_x-p=0

\end{array}
\right.
$$

*La deuxième équation correspond à l'égalité des dérivées croisées*