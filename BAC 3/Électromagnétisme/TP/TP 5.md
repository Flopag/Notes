# TP 5 : Magnétostatique (inductance)

## Théories

[Inductance](../Notion/Induction%20magnétique.md) :

$$L = \frac{\phi_s}{I}$$

[Loi de Lens](../Notion/Equation%20de%20Maxwell.md) :

$$V=-\frac{d\phi_s}{dt}$$

avec $\phi_s=\int_S{\vec B \bullet d\vec S}$

On sait que $B$ est proportionnel à $I$ et que $\phi_s$ est proportionnel à $B$, donc, $\phi_s$ est proportionnel à $I$

Energie magnétique :

$$W_M = \frac{1}{2}\int_V{\vec B \bullet \vec H \ dv}=\frac{1}{2}LI^2$$

$$L = \frac{2W_M}{I^2}$$

Si conducteur épais (ex: coaxial):
- La surface $S$ est mal définie
- $L_{tot} = \sum{L_i}$ ex : $L=L_{conducteur}+L_{pas \ conducteur}=\frac{2W_M}{I^2}+\frac{\phi_S}{I}$

## Méthodes

### Déterminer l'expression du [Champ magnétique](../Notion/Champ%20magnétique.md) dans tout les points de l'espace

Voir [TP 4](TP%204.md)

## Determiner l'expression de l'[inductance](../Notion/Induction%20magnétique.md)

On doit déterminer toutes les [inductances](../Notion/Induction%20magnétique.md) puis les sommer pour avoir l'[totale](../Notion/Induction%20magnétique.md). il y en a de plusieurs types :
- A l'intérieur d'une [Conducteur](../Notion/Conducteur.md), on calcule $W_M = \frac{1}{2}\int_V{\vec B \bullet \vec H \ dv}$ puis $L = \frac{2W_M}{I^2}$
- A l'extérieur d'un [Conducteur](../Notion/Conducteur.md), on calcule $\phi_s=\int_S{\vec B \bullet d\vec S}$ puis 