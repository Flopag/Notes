# TP 4 : Magnétostatique (champs)

## Théorie

Un [champ magnétique statique](../Notion/Champ%20d'induction%20magnétique.md) est généré par des charges en mouvement

Deux loi fondamentaux :
- [Gauss magnétique](../Notion/Loi%20de%20Gauss.md) : $\vec \nabla \bullet \vec B= 0$ ou $\oint_S{\vec B \bullet d\vec S}=0$
- [Ampère](../Notion/Théorème%20d'Ampère.md) : $\vec \nabla \times \vec H = \vec J$ ou $\oint_C{\vec H \bullet d\vec l} = \oint_S{\vec J\bullet d\vec S} = I_{intérieur}$
	- $\vec H$ est le [champ magnétique](../Notion/Champ%20magnétique.md)
	- $\vec J = \frac{I}{S}$ est la [densité de courant](../Notion/Densité%20de%20courant%20électrique.md)

Dans un [Matériau LHI](../Notion/Matériau%20LHI.md) :

$$\vec b = \mu \vec H$$

où $\mu$ est la **perméabilité du milieu**, il peut s'exprimer comme $\mu = \mu_r \mu_0$ avec $\mu_r$ la **perméabilité relative du milieu**

[Loi de Biot-Savart](../Notion/Loi%20de%20Biot-Savart.md) :

$$\vec B(\vec r) = \frac{\mu_0}{4\pi} \int{\frac{(Id\vec l \times \hat{\vec r}_{rel})}{r^2_{rel}}} \ [T]$$

$$\vec B(\vec r) = \frac{\mu_0}{4\pi} \int{\frac{(\vec J(\vec r) \times (\vec r - \vec r'))}{|\vec r - \vec r'|^3} \ dV'}$$

## Méthodes

### Établir l'expression du [Champ magnétique](../Notion/Champ%20magnétique.md)

#### Méthode 1 : par [Biot-Savart](../Notion/Loi%20de%20Biot-Savart.md)

Il faut simplement calculer chaque terme et faire l'intégration 

Astuces :
- Utiliser les symétries pour faire moins de calculs

#### Méthode 2 : par le [théorème d'Ampère](../Notion/Théorème%20d'Ampère.md) et [Gauss magnétique](../Notion/Loi%20de%20Gauss.md)

1. Trouver les variables du problème (à l'aide des symétries), par exemple : $\vec H(r,\theta,z) = \vec H(r) = H_r(r) \hat r+H_\theta(r) \hat \theta + H_z(r)\hat z$
2. Il faut utiliser les deux théorèmes dans plusieurs configurations pour avoir la valeur du [Champ magnétique](../Notion/Champ%20magnétique.md) dans toutes les directions (ex : $H_r(r), H_\theta(r), H_z(r)$)
3. Faire ça pour chaque région de l'espace

Exemple de configuration :
- Bord d'un cercle 
- Bord d'un carré 
- Surface d'un cylindre 
