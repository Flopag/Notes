# TP 9 : Equation de transport non linéaire (suite)

## Théorie

Rankine-Hugoniot :

$$s(t) = \frac{A(u^+)-A(u^-)}{u^+-u^-}$$

où :
- $s(t)$ est la vitesse 
- $A(u) = \frac{1}{2}u^2$ est le flux
- $u^+$ est la valeur qui vient des + vers la zone (vient de la droite)
- $u^-$ est la valeur qui vient des - vers la zone (vient de la gauche)

La solution de Rankine-Hugoniot est accepté si le critère d'entropie est respecté :

$$a(u^-)\ge S(t)\ge a(u^+)$$

où $a(u) = u$ (/ ! \\ à vérifier)

Ligne caractéristique d'une onde de choc est donné par (/ ! \\ à vérifier) :

$$x_s(t)=S(t)\ t + nombre_1 \ \ \ \ , \forall t>nombre_2$$

où $nombre_1$ et $nombre_2$ doivent être trouvé en fonction du contexte (pour rentrer dans le problème)

## Méthodes

Voir [TP 2](TP%202.md)

## Résolution si les lignes caractéristique se croisent

Pareil que [TP 2](TP%202.md) jusque au point 6

7. Trouver les différente zone  pour chaque type de ligne caractéristique (on peut s'aider d'un schéma pour avoir plus simple)
	1. Dessiner un schéma avec toutes les lignes caractéristique (axe horizontal = $x(t)$ et axe vertical = $t$)
	2. Remarquer des zones avec un seul type de ligne et d'autre avec plusieurs types de lignes
	3. Les lignes peuvent etre caractérisé par une combinaison de : $x \le nombre$, $x \ge nombre$ , $t \le x$ ou $t \ge x$
	4. $t\le x$ correspond en dessous de la frontière 
	5. $t \ge x$ correspond au dessus de la frontière
8. Isoler $x_0$ dans chacun de ces zones, les zones de croisement ont plusieurs solution de $x_0$
9. Exprimer $u$ dans les zones sans croisement en remplacent simplement par l'expression de $x_0$ trouver au point 8
10. Determiner $x_s$ pour la zone de croisement en considèrant que c'est un choc (utilisation de Rankine-Hugoniot)
11. Rajouter les expressions trouver en 10 dans $u$ (en réfléchissant quand est-ce qu'on est dans quel zone, comme au point 7)