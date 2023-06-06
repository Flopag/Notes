# Antennes

## Gain d'antenne

>Le gain d'une antenne est le ratio, généralement exprimé en décibels, entre la puissance nécessaire à l'entrée d'une antenne de référence sans perte à la puissance effective fournie à l'antenne considéré de manière à ce qu'elle fournisse le même champ électrique ou la même puissance dans une direction donnée

La puissance Isotrope Rayonnée Equivalente (**PIRE**) est le produit de la puissance d'émission d'une antenne par le gain dans la direction d'observation #Important 

$$PIRE = Puissance \times Gain = P \times G$$

## Aire effective

L'aire effective d'une antenne est définie comme le rapport entre la puissance disponible à ses bornes au [Vecteur de Poynting](Vecteur%20de%20Poynting.md) incident :

$$A_{eff} = \frac{P}{S}$$

L'aire effective est liée à son gain par la relation :

$$A_{eff, E/R} = G_{E/R} \frac{\lambda^2}{4\pi}$$

Relation de Friis :

$$\epsilon = 32,5 + 20 log \ f_{[MHz]} + 20 log \ d_{[km]} - G_{E[dB]} - G_{R[dB]} \ [dB]$$

## Antenne simple (cable)

Il peut être représenter par un **Doublet de hertz** qui est un morceau infinitésimale d'un cable

$$||\hat S_{av}|| = \frac{||\hat E_\theta||^2}{120 \pi}$$

Puissance de rayonnement d'une antenne simple :

$$P_{rad} = 80 \pi^2 \left( \frac{dl}{\lambda}\right)^2 \frac{|I|^2}{2}$$

![](attachments/Pasted%20image%2020230606141613.png)

