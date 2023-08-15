# Matériaux magnétique

## Types de matériaux magnétique

Le magnétisme des matériaux est associé au mouvement des électrons à l'échelle atomique. Deux mécanismes peuvent le générer :
- Le mouvement orbital des électrons
- Le spin de chaque électron

Il y a deux types de matériaux :
- Matériaux à réponse linéaire : 
	- **diamagnétique** : aimantation qui s'oppose au [Champ d'induction magnétique](Champ%20d'induction%20magnétique.md) appliqué [(](Matériau%20LHI.md) $\chi_m < 0$ [)](Matériau%20LHI.md)
	- **paramagnétique** : aimantation qui parallèle au [Champ d'induction magnétique](Champ%20d'induction%20magnétique.md) appliqué [(](Matériau%20LHI.md) $\chi_m > 0$ [)](Matériau%20LHI.md)
- Matériaux à réponse non-linéaire : 
	- **ferromagnétique** : moment magnétique atomique permanent qui peut être aligner par un [Champ d'induction magnétique](Champ%20d'induction%20magnétique.md) appliqué
		- Une haute température tend à réduire le l'aimantation
		- Ferromagnétique doux : faible champ coercitif $H_c$
			- Un ferromagnétique doux a une réponse magnétique forte pour un champ externe faible (car $µ_r ≫ 1$). Par conséquent, le matériau peut canaliser les lignes de flux.
		- Ferromagnétique dure : fort champ coercitif $H_c$
			- Très bon aimant permanant

![](attachments/Pasted%20image%2020230715164124.png)

Un **matériau uniformément aimanté** dont la [distribution volumique du courant](Vecteur%20potentiel.md) $\vec J_{liées}$ est nul et la [distribution surfacique du courant](Vecteur%20potentiel.md) $\vec K_{liées}$ est non nul

*(Demo slides chapitre 3 p24)*

![](attachments/Pasted%20image%2020230716152006.png)

## Aimantation des matériaux magnétique

![](attachments/Pasted%20image%2020230716160252.png)

### Cycle d'hystérésis

On a le [Champ d'induction magnétique](Champ%20d'induction%20magnétique.md) en fonction du [Champ magnétique](Champ%20magnétique.md) (non-linéaire) :

$$\vec B(\vec H(I))$$

1. On part de $I = 0$ et on augmente le courant à une valeur $I = I_{sat}$, telle que le matériau est complètement aimanté. Ce point correspond à $H = H_{sat}$.
2. On diminue ensuite $I$ jusqu'à zéro
	- $B$ ne suit pas $H$ car il y a un retard
3. On inverse à présent $I$ ($I < 0$) pour annuler $B$
4. Le courant I passe à présent à $I = −I_{sat}$. On a $H = −H_{sat}$.
5. Le courant $I$ est augmenté de $−I_{sat}$ à $I_{sat}$ 

![](attachments/Pasted%20image%2020230716161320.png)

avec :
- $B_r$ le point où on a l'état de rémanence
- $H_c$ est le champ coercitif

On peut voir que le processus est irréversible

L'énergie dissipé par unité de volume et par cycle est l'aire intérieur de la courbe :

$$\frac E V = \oint_{cycle}{H \ dB}$$