# TP 3 : Electrostatique (image et diélectrique)

## théorie

Quelque résultats intéressant trouvé dans les anciens TP :
- [Charge](../Notion/Charge.md) seule : 
	- $V=\frac{q}{4\pi \varepsilon_0 r}+K$
	- $\vec E = \frac{q}{4\pi \varepsilon_0 r^2}\hat r$
- Charge linéique $\rho_L$ :
	- $V=\frac{\rho_L}{2\pi \varepsilon_0}\ln\left(\frac{1}{r}\right) + K$
	- $\vec E = \frac{\rho_L}{2\pi \varepsilon_0 r}\hat r$
- ligne bifilaire $\rho_L$ et $-\rho_L$ :
	- $V=\frac{\rho_L}{2\pi \varepsilon_0}\ln\left(\frac{r_-}{r_+}\right)$
	- $\vec E = \frac{\rho_L}{2\pi \varepsilon_0}\left(\frac{\hat r_+}{r_+} - \frac{\hat r_-}{r_-}\right)$

Si on applique [Champ électrique](../Notion/Champ%20électrique.md) dans un [matériau diélectrique](../Notion/Conducteur.md), il y a création de [Dipôle](../Notion/Dipôle.md) et donc de [charge liées](../Notion/Conducteur.md)

Propriété du [vecteur de polarisation](../Notion/Conducteur.md) $\vec P$ :

$$\left\{\begin{matrix}

\rho_{liées} = -\vec \nabla \bullet \vec P\\
\sigma_{liées} = \hat n \bullet \vec P

\end{matrix}\right.$$

/ ! \\ $\vec E$ tient compte des [Charge](../Notion/Charge.md) libres et liées et $\vec D=\varepsilon_0 \vec E + \vec P$ tient compte des charge libres uniformément

$$\vec \nabla \bullet \vec D = \rho_{libre}$$

Dans un milieu LHI :

$$\vec P = \varepsilon_0 \chi_e \vec E \rightarrow \vec D = \varepsilon \vec E$$

## Méthodes

### Méthode des images

Placer une charge/ligne conductrice affin de faire des calculs mais sans changer les données.

### trouver une solution unique

Il faut trouver une solution qui satisfait l'[équation de Laplace](../Notion/Potentiel%20électrique.md) et les condition limites dans le domaine