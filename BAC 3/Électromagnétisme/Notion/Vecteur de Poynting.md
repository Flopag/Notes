# Vecteur de Poynting

Le vecteur de Poynting $\vec S$ représente la propagation :

$$\vec S(x,y,z,t) = \vec E(x,y,z,t)\times\vec H(x,y,z,t) \ \left[\frac{W}{m²}\right]$$

En utilisant des [Phaseur](Phaseur.md) :

$$<\vec S> (x,y,z) = \frac{1}{2}\Re\{\hat {\vec E}(x,y,z)\times \hat {\vec H}^*(x,y,z)\}$$

## Théorème de Poynting : Conservation de l'énergie

*(voir slides chap4-Maxwell p12)*

Théorème :

$$-\int_V{\left(\vec H\bullet \frac{\partial \vec B}{\partial t}+\vec E\bullet \frac{\partial \vec D}{\partial t}\right) \ dV}=\int_S{(\vec E\times\vec H)\bullet d\vec S}+\int_V{\vec J \bullet \vec E \ dV}$$

Interpretation :
- $\int_V{\left(\vec H\bullet \frac{\partial \vec B}{\partial t}+\vec E\bullet \frac{\partial \vec D}{\partial t}\right) \ dV}$ décrit le taux de variation par unité de temps de l'énergie emmagasinée par le champs électromagnétiques dans le volume $V$ (dans une [Matériau LHI](Matériau%20LHI.md))
- $\int_V{\vec J \bullet \vec E \ dV}$ décrit la puissance dissipé par effet Joule dans le volume $V$
