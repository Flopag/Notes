# TP 1 : Introduction et électrostatique (intro)

## Rappel Théorique

Différents types de coordonnées :

|Cartésienne|Cylindrique|Sphérique|
|-|-|-|
|$\hat x, \hat y, \hat z$ | $\hat r, \hat \theta, \hat z$| $\hat r, \hat \theta, \hat \varphi$
|$x$|$r \ cos\theta$|$r \ sin \theta \ cos \varphi$
|$y$|$r \ sin\theta$|
|$z$|$z$|$r \ cos\theta$
|$dx, dy, dz$|$dr, rd\theta$|$dr,rd\theta,r \ sin\theta \ d\varphi$
| $\vec\nabla V$ |  | 
|$\vec \nabla \bullet \vec V$||
|$\vec \nabla \times \vec V$||

[Théorème de divergence](../Notion/Théorème%20de%20la%20divergence%20de%20Gauss.md) :

$$\int_V{\vec \nabla \bullet \vec E \ dV} = \oint_S{\vec E \bullet d\vec S}$$

[Théorème de Stokes](../Notion/Théorème%20de%20Stokes.md) :

$$\int_S{\vec \nabla \times \vec E \ d\vec S} = \int_l{\vec E \bullet d\vec l}$$

Électrostatique :
- $\frac{d}{dt} = 0$
- $\vec B = 0$
- $\vec H = 0$
- $i=0$

$$\vec E = -\vec\nabla V$$

Dans le vide :

$$\vec E = \frac{1}{4\pi\varepsilon_0} \frac{q}{r²} \hat r$$

$$V = \frac{q}{4\pi\varepsilon_0r}+(K =0)$$

[Principe de superposition](../Notion/Principe%20de%20superposition.md) : les $\vec E$ et $V$ se somment

Dans un [Matériau LHI](../Notion/Matériau%20LHI.md) :
- $\vec P = \varepsilon_0\chi_e\vec E$
- $\vec P \bullet \hat n = \sigma_{liées}$
- $\vec \nabla \bullet \vec P = \rho_{liées}$
- $\vec D = \varepsilon \vec E$

Loi fondamentales :
- $\vec \nabla \times \vec E = \vec 0$
- $\vec \nabla \bullet \vec D = \rho_{libre}$

[Loi de poisson](../Notion/Potentiel%20électrique.md) :

$$\nabla²V=\frac{\rho_{libre}}{\varepsilon_0}$$

### Bonus

$$||\vec r|| = \sqrt{\vec r²}$$

$$(1+x)^n=1+nx \ \ \ si \ x \ très \ petit$$

$$\varepsilon = \varepsilon_0 \ \ \ si \ dans \ le \ vide$$

## Méthodes

### Calculer un [Champ électrique](../Notion/Champ%20électrique.md)

Plusieurs méthodes possible :
- Directement : Utilisation de la formule dans le vide et du principe de superposition
- Indirectement avec $V$ : $\vec E = -\vec\nabla V$

### Calculer un [Potentiel électrique](../Notion/Potentiel%20électrique.md)

Plusieurs méthodes possible :
- Directement : Utilisation de la formule dans le vide et du principe de superposition
- Indirectement avec $\vec E$ : $\vec E = -\vec\nabla V$

### Calculer une [Densité de charge](../Notion/Densité%20de%20charge.md)

- $\vec \nabla \bullet \vec D = \rho_{libre}$ avec $\vec D = \varepsilon \vec E$