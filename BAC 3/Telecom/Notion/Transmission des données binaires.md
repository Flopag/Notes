
# Transmission des données binaires

## Introduction

Il y a deux méthodes :
- La transmission en bande de base $W$ : méthode correspondant à l'émission directe sur le canal de transmission
- La transmission par modulation d'une porteuse : méthode utilisant un cosinus pour la transmission

Caractéristique importante :

- Emetteur :
	- Le débit en $[b/s]$
	- Les niveaux physiques associés à chaque bit (0 ou 1) ou groupe de bit
	- L'encombrement spectral
		- [Efficacité spectral](Efficacité%20spectral.md)
- Récepteur
	- [Bit error rate](Bit%20error%20rate.md)

## Construction d'un signal d'information numérique ([Codage](Codage.md)?)

Forme du signal d'information numérique :

$$g(t) = \sum_{k=-\infty}^{+\infty}{A_k\phi(t-kT)}$$

avec :
- $\phi()$, l'onde de mise en forme ($rect()$)
- $A_k$, la valeur de l'information (ex: +1, -1)

Remarques :
- On utilise une seule onde de mise en forme $\phi()$ pour toute les valeurs de $A_k$
- Pas de recouvrement temporel entre les différent $A_k$. Les signaux sont envoyé à tours de rôle
- $g(t)$ est un processus stochastique

![](attachments/Pasted%20image%2020230604094014.png)

## Détection de signaux binaires en présence de bruit gaussien

Erreurs de transmission dues à :
- du bruit
- présence de filtres
- non-linéarité du canal
- ...

![](attachments/Pasted%20image%2020230604102650.png)

### Conception d'un récepteur

A la réception, on dispose de $x(t)=n(t)+g(t)$ dont on sait que :
- L'information est numérique $\rightarrow$ l'information est constant par tranche temporelle de $T$
- Les symboles successifs sont non corrélés entre eux

![](attachments/Pasted%20image%2020230604112456.png)

Nature des signaux :
- $g(t)$ est un signal stochastique (car il contient l'information sous la forme des $A_k$)
- $n(t)$ est un signal stochastique
- $x(t)=n(t)+g(t)$ est un signal stochastique (tout comme $h(t)$)
- $y[T]$ est une variable aléatoire (et non stochastique!)

#### Filtrage

Au lieu de la valeur en fin d'intervalle, on peut utiliser toutes les valeurs de l'intervalle $[0,T]$ pour prendre la décision $\rightarrow$ on filtre l'information sur l'intervalle $[0, T]$

Comment trouver l'expression d'un filtre adéquat de réception $h(t)$?
1. Définition d'un critère numérique
	- $\eta = \frac{|g_h(T)|^2}{E\{n^2_h(t)\}}$ avec $|g_h(T)|^2$ la puissance du signal pour un bit et $E\{n^2_h(t)\}$ la puissance du bruit après filtrage
2. Trouver la réponse impulsionnelle de ce critère
3. minimiser/maximiser ce critère
4. Dériver pour avoir la forme optimal du filtre de réception
	- $h_{opt}(t) = kg(T-t) \ \ , si \ 0\leq t\leq T = 0 \ \ ,sinon$ 

#### Décision

La non-correlation entre symboles successifs fait que l'on peut ré-initialiser le récepteur d'un intervalle à l'autre $\rightarrow$ on échantillonne la sortie du filtre en fin d'intervalle $[0,T]$ et on décide séparément pour chaque échantillon sur base d'un critère qui maximise la performance ou minimise le taux d'erreur

Au moment de prendre une décision, on peut faire deux types d'erreur :
- erreur de type 1 : sélectionner 1 alors qu'on a transmis 0
- erreur de type 2 : sélectionner 0 alors qu'on a transmis 1.

On considère les signals [NRZ](Codage.md) reçu du type :

$$x(t) = 
\left\{ 
\begin{array} &
	g_0(t)+n,(t) = -V+n(t) & pour \ 0\\
	g_1(t)+n,(t) =+V+n(t) & pour \ 1
\end{array}
\right.$$

Critère de sélection ($\lambda$), on choisi :
- $-V$ si $y[T_b] < 0$
- $+V$ sinon

La [probabilité d'erreur moyenne](Bit%20error%20rate.md) : 

$$p_e = P_{e0} \ p(0) + P_{e1} \ p(1) = P_{e0} = P_{e1}$$

avec $P_{e0} = \frac{1}{2} \ erfc\left( \sqrt{\frac{E_b}{N_0}} \right)$ l'erreur si on envoie 0 et $P_{e1}$ l'erreur si on envoie 1

