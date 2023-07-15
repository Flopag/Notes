# TP 3 : Classification

## Classification d'une [EDP](../Notion/EDP.md) d'ordre 2

EDP générale du deuxième ordre avec deux [Variable indépendante](Variable%20indépendante.md) :

$$a_{11} u_{xx}+2a_{12}u_{xy} + a_{22}u_{yy} + a_1u_x+a_2u_y+a_0u=0$$
**Théorème** : L'équation peut être réduit en une des trois formes canonique plus simple par une transformation linéaire des [Variable indépendante](Variable%20indépendante.md) :
- Forme **elliptique** si $a_{12}² < a_{11}a_{22}$ $\rightarrow$ $u_{xx}+u_{yy}+... = 0$ avec $...$ les termes d'ordre 1 et 0
	- [Equation de Laplace](Equation%20de%20Laplace.md)
- Forme **hyperbolique** si $a_{12}² > a_{11}a_{22}$ $\rightarrow$ $u_{xx}-u_{yy}+... = 0$
	- [Equation d'onde](Equation%20d'onde.md)
- Forme **parabolic** si $a_{12}² = a_{11}a_{22}$ $\rightarrow$ $u_{xx}+... = 0$
	- [Equation de diffusion](Equation%20de%20diffusion.md)

## Quelque expressions utile (à vérifier)

$$\vec \nabla \bullet (\vec \nabla f)=\Delta f$$

$$\vec \nabla \times (\vec \nabla f)=\vec 0$$

$$\vec \nabla \bullet (\vec \nabla \times \vec f) = 0$$

$$\vec \nabla \times (\vec \nabla \times \vec f)=\vec \nabla (\vec \nabla \bullet f)-\vec \nabla \bullet (\vec \nabla f)$$