# Gestion d'erreurs

Hypothèses :
- Les codage sont fait par [blocs de données](Codage%20par%20blocs.md)
- On veut détecter/corriger les erreurs aléatoires isolées

Sur base des **bits redondants**, le récepteur sera en mesure de [détecter](Détection%20d'erreurs.md)/[corriger](Correction%20d'erreurs.md) certaines erreurs. La redondance introduite par le code est mesurée par son taux de redondance : $\frac{n-k}{n}$ avec $n$, la taille du [mot de code](Codage%20par%20blocs.md) et $k$, la taille du [message](Codage%20par%20blocs.md) (plus le taux est important, plus la redondance est élevé)

La **capacité de détection** d'un code (nombre maximum de bits erronés que l'on peut détecter) est fournie par : $t_d = d_{min} - 1$ avec $d_{min}$, la [distance de hamming](Codage%20par%20blocs.md) minimum entre deux mot de code valide

La capacité de correction d'un code (nombre maximum de bits erronés que l'on peut corriger) est fournie par : $t_c = \left\lfloor \frac{d_{min}-1}{2} \right\rfloor$ avec $d_{min}$, la [distance de hamming](Codage%20par%20blocs.md) minimum entre deux mot de code valide

## Type de code de gestion d'erreur

### Code à repetition

Propriétés :
- Correction des erreurs simple (Pas de correction pour les erreurs plus haute)
- Détection des erreurs double

![](attachments/Pasted%20image%2020230605090917.png)

### Code à parité

Dans un code à parité, nous ajoutons chaque bloc de $k$ bits d'un message $m$, avec un bit supplémentaire de parité :
- Pour une parité paire (on veut un nombre paire de bit = 1), le bit additionnel vaut $q = \sum_{i=1}^k{m_i(mod \ 2)}$ 
- Pour une parité impaire (on veut un nombre impaire de bit = 1), le bit additionnel vaut $1-q$

Propriétés :
- Le bit additionnel assure qu'il y aura un nombre pair/impaire de 1 dans le mot de code
- Détecte les erreurs simple (1 bit bit changé) mais ne peut pas les corriger (car il ne peut pas la localiser)
- Utile si la probabilité d'avoir 2 erreurs est négligeable
- Facile a implémenter

exemple de codage paire :

![](attachments/Pasted%20image%2020230605091821.png)

![](attachments/Pasted%20image%2020230605091854.png)

### Code cyclique

On appelle code cyclique un code linéaire $(n, k)$ tel que toute permutation cyclique des bits sur un mot codé génère un autre mot codé

### Codes de Hamming

Les codes de Hamming constituent un sous-ensemble des codes en blocs pour lesquels $(n,k) = (2^r-1,2^r-1-r)$ pour $r=2,3,...$