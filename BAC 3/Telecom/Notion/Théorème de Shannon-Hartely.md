# Théorème de Shannon-Hartely

> Capacité d'un canal $C$ (condition pour avoir un taux d'erreur par bit $P_e \rightarrow 0$) :
> 
> $$C \ [b/s] = B \times log_2 \left( 1 + \frac{S}{N} \right)$$
> 
> où
> - $B$ est la largeur du canal en $Hz$
> - $\frac{S}{N}$ est le rapport signal à bruit (en Watt/Watt, pas en dB)

On ne peut pas faire un récepteur qui comprenne plus que cette capacité

A capacité maximale ($C = R_b =$ débit binaire), le rapport minimum absolu à garantir est $\frac{E_b}{n_0} = -1.59 \ [dB]$ avec $E_b$ l'énergie par bit
