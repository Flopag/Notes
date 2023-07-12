# Conducteur

## conducteur parfait

Un conducteur parfait est un conducteur idéalisé dont les [Charge](Charge.md) sont :
- entièrement libres de se déplacer au travers du volume
- en quantité illimitée

Lorsqu'on lui soumet un [Champ électrique](Champ%20électrique.md) extérieur $\vec E_{app}$ , un autre [Champ électrique](Champ%20électrique.md) $\vec E_{ind}$ (produit par l'entrainement vers la surface des [Charge](Charge.md)) va s'opposer pour conduire à un équilibre (le [Champ électrique](Champ%20électrique.md) est nul à l'intérieur du conducteur). On a donc un équilibre quand $\vec E_{app} = -\vec E_{ind}$

Les [lignes de champs](Champ%20électrique.md) sont perpendiculaire à la surface, parce que, dans le cas contraire, une composante tangentielle donnerait lieu à un [Courant](Courant.md) de surface

![](attachments/Pasted%20image%2020230712165328.png)

![](attachments/Pasted%20image%2020230712165344.png)

### Application : cage de Faraday

Une cage de Faraday est un volume quelconque entouré d'un autre volume composé d'un conducteur parfait. On sait que le [Champ électrique](Champ%20électrique.md) dans un conducteur parfait est nul, on a donc tous le volume contenu dans le conducteur parfait qui à un [Champ électrique](Champ%20électrique.md) nul (puisque le [rotationnel du champ électrique](Champ%20électrique.md) est nul)

![](attachments/Pasted%20image%2020230712165404.png)

## Conducteur diélectrique

Un conducteur diélectrique est un conducteur dont les [Charge](Charge.md) de volume sont qualifiées comme étant liées. Les [Charge](Charge.md) ne peuvent donc pas se déplacer mais seulement pivoter (peut donc être polarisé)

/ ! \ diélectrique (polarisable) $\neq$ isolant (faible conductivité)

### Mécanique de polarisation

Il y a plusieurs méthodes :

- **Polarisation électronique** : induction de dipole électrique locaux par déplacement et/ou déformation du nuage électronique
- **Polarisation atomique/ionique** : déplacement d'atomes ou d'ions dans des molécules ou dans un réseau cristallin
- **Polarisation d'orientation** : orientation de molécules polaires

### [Champ électrique](Champ%20électrique.md) au sein du matériau

Un matériau diélectrique est composé d'un grand nombre de [simple dipôle](Dipôle.md) qui ont chacun un moment dipolaire $\vec p$

On définit le **vecteur de polarisation** $\vec P$ qui est le moment dipolaire électrique par unité de volume (contient tout les moment dipolaire d'un volume) :

$$\vec P = \lim_{\Delta V\rightarrow 0}{\sum_{i\in\alpha}{\frac{\vec p_i}{\Delta V}}}$$

![](attachments/Pasted%20image%2020230712172659.png)

Le [Potentiel électrique](Potentiel%20électrique.md) est obtenu par le [Principe de superposition](Principe%20de%20superposition.md) :

$$V_i = \frac{1}{4\pi\varepsilon_0} \int_s{\frac{\vec P(\vec r')\bullet (\vec r - \vec r')}{|\vec r - \vec r'|³}dV'}$$

On peut séparer les [Charge](Charge.md) en deux types :
- Charge de volume avec $\rho_{liées}=-\vec \nabla \bullet \vec P$ une densité volumique de charges liées
- Charge de surface avec $\sigma_{liées} = \vec P \bullet \hat n$ une densité surfacique de charges liées

Chaque [Dipôle](Dipôle.md) porte une charge nette nul, on a donc une charge liée totale également nul

![](attachments/Pasted%20image%2020230712172717.png)

On a donc une autre expression du [Potentiel électrique](Potentiel%20électrique.md) :

$$V = \frac{1}{4\pi\varepsilon_0} \int_V{\frac{\rho_{liées}(\vec r')}{|\vec r - \vec r'|³}dV'} + \frac{1}{4\pi\varepsilon_0} \int_S{\frac{\sigma_{liées}(\vec r')}{|\vec r - \vec r'|³} dS'}$$

Demo dans les slides pages 32/33 et dans les notes cours 1

