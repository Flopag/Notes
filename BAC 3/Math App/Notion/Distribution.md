# Distribution

Une distribution est une règle qui associe un nombre a une fonction

![](attachments/Pasted%20image%2020230720110935.png)

> Une distribution $f$ est une règle de $D\rightarrow \Re$ ([l'ensemble des fonctions test](Fonction%20test.md) vers l'ensemble des réel) qui doit être linéaire et continue

La notation utilisé pour la distribution est $(f,\phi)$ (la valeur réel que donne $f$ appliqué à une [fonction test](Fonction%20test.md) $\phi$)

Il y a une autre manière de noter une distribution :

$$\phi \mapsto (f,\phi)$$

## Dérivée

La dérivé d'une distribution $f$ est définie de sorte qu'elle existe toujours :

$$\int_{-\infty}^{+\infty}{f'(x)\phi(x) \ dx} = -\int_{-\infty}^{+\infty}{f(x)\phi '(x) \ dx}$$

puisque $\phi(x) = 0$ pour les grandes valeur de $|x|$

La dérivé d'une distribution $f$, pour chaque [Fonction test](Fonction%20test.md) $\phi$, est :

$$(f',\phi)=-(f,\phi ')$$

## Linéarité

La distribution est linéaire si :

$$(f,a\phi+b\psi)=a(f,\phi)+b(f,\psi)$$

## Continuité

Si $\{\phi_n\}$ désigne une suite de [Fonction test](Fonction%20test.md) qui converge uniformément vers une [Fonction test](Fonction%20test.md) $\phi$ alors, la distribution est continue si :

$$(f,\phi_n)\rightarrow (f,\phi) \ \ \ as \ \ n\rightarrow \infty$$