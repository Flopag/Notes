# Modulation/Démodulation

## Modulation analogique

On veut transmettre un signal :

$$s(t) = A(t) \ cos{(2\pi f(t) t + \phi (t))}$$
Il y a trois modulation possible :
- [Modulation d'Amplitude](Modulation%20d'Amplitude.md) $\rightarrow$ faire varier $A(t)$
	- Variantes :
		- [Modulation DSB-SC](Modulation%20DSB-SC.md)
		- [Modulation QAM](Modulation%20QAM.md)
		- [Modulation SSB](Modulation%20SSB.md)
		- [Modulation VSB](Modulation%20VSB.md)
- [Modulation de Fréquence](Modulation%20de%20Fréquence.md) $\rightarrow$ faire varier $f(t)$
- [Modulation de Phase](Modulation%20de%20Phase.md) $\rightarrow$ faire varier $\phi(t)$

![](attachments/Pasted%20image%2020230602095439.png)

## "Modulation" (codage)

C'est pas vraiment de la modulation mais plus du codage

### Analogique

Ils ne sont plus vraiment d'actualité

![](attachments/Pasted%20image%2020230603114749.png)

**(b) Pulse Amplitude "Modulation" (PAM)** :

On envoie des pulsations rectangulaire de longueur $\tau'$ fixe tout les $T_s$ fixe d'une hauteur voulue. C'est la hauteur de la pulsation qui donne l'information

**(c) Pulse Duration "Modulation" (PDM)** :

On envoie des pulsations rectangulaire de longueur $\tau'$ variable tout les $T_s$ fixe d'une hauteur fixe. C'est $\tau'$ qui donne l'information

**(d) Pulse Position "Modulation" (PPM)** :

On envoie des pulsations rectangulaire de longueur $\tau'$ fixe tout les $T_s$ variable d'une hauteur fixe. C'est $T_s$ qui donne l'information

### Numérique

**Pulse Code "Modulation" (PCM)** :

On regarde périodiquement la valeur de $m(t)$ puis on lui applique plusieurs étapes :

1. En arrondi vers la valeur la plus proche appartenant au Numéro d'ordre pour obtenir $m[nT_s]$
2. Regarder à quel numéro d'ordre correspond  $m[nT_s]$
3. Regarder à quel code PCM (les bits) correspond le numéro d'ordre

![](attachments/Pasted%20image%2020230603145137.png)
