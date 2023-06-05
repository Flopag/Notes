# Codage par blocs (dataword)

Les données binaires sont regroupées en **blocs** de $k$ bits qui sont des **mot de message** ou de **données** représenté par un vecteur :

$$\vec m =(m_, m_2, ..., m_k)$$

Il y a donc $2^k$ messages possible

Chaque **mot de données** est représenté par un **mot de code** (codeword) de longueur $n$ bits (avec $n>k$) représenté par le vecteur :

$$\vec c=(c_1, c_2, ..., c_n)$$

Le mot de code contient le message et les redondance. On a donc :
- $2^n$ mots de codes possibles
- $2^k$ mot de codes valides
- $2^n-2^k$ mots de code erronés

On peut donc caractériser le code bloc par $n$ et $k$. Notation : $code \ bloc \ (n,k)$

## Code block linéaire

Un code bloc linéaire est défini par l'équation matricielle :

$$\vec c = \vec m G$$

La matrice $G\in F_2^{k\times n}$ est appelée matrice génératrice. elle a la forme suivante :

$$
G = \left(\begin{matrix}
v_{11} & v_{12} & ... & v_{1n}\\
v_{21} & v_{22} & ... & v_{2n}\\
... & ... &  & ...\\
v_{k1} & v_{k2} & ... & v_{kn}\\
\end{matrix}\right)
$$

**Théorème** : Les $2^k$ mots de code valides d'un code bloc linéaire forment un sous espace vectoriel, noté $C$, de dimension $k$ de $F_2^n$

Toute combinaison linéaire de deux mots de code valides est un nouveau mot de code valide $\rightarrow$ la somme de mots de code valide est un nouveau mot de code valide : $\forall \vec c_1, \vec c_2 \in C, \ \ \ \ \vec c_1 + \vec c_2 \in C$

**Théorème** : La distance de Hamming d'un code linéaire est le minimum des poids des mots de code valides non identiquement nuls : $d_{min} = min_{\vec c_I \in C, \, \ \vec c_I \neq \vec 0} \{w(\vec c_I)\}$

Un code est dit **systématique** si une partie du mot codé coincide avec le message :

$$
G = [P|I_k] = \left(\begin{matrix}
p_{11} & p_{12} & ... & p_{1(n-k)} & 1 & 0 & ... & 0\\
p_{21} & p_{22} & ... & p_{2(n-k)}& 0 & 1 & ... & 0\\
... & ... &  & ...& 0 & 0 & ... & 0\\
p_{k1} & p_{k2} & ... & p_{k(n-k)}& 0 & 0 & ... & 1\\
\end{matrix}\right)
$$

Matrice de contrôle de parité :

$$H^T = \left[\frac{I_{n-k}}{P}\right] = \left(\begin{matrix}
1 & 0 & ... & 0\\
0 & 1 & ... & 0\\
... & ... &  & 0\\
0 & 0 & ... & 1\\
p_{11} & p_{12} & ... & p_{1(n-k)} \\
p_{21} & p_{22} & ... & p_{2(n-k)}\\
... & ... &  & ...\\
p_{k1} & p_{k2} & ... & p_{k(n-k)}\\
\end{matrix}\right)$$

**Théorème** : Le produit $\vec c H^T$, pour tout mot codé $\vec c \in C$ au moyen de la matrice génératrice $G$, est le vecteur nul : $\vec c H^T = \vec 0$ . (**cela permet de détecter si il y a une erreur!**)

Le syndrome est le vecteur sous la forme $\vec s = \vec r H^T = (\vec c + \vec e) H^T = \vec e H^T$ avec $\vec r$ le vecteur à la réception et $\vec e$ le vecteur d'erreur (le vecteur qui contient l'erreur fourni à $\vec c$)

## Hamming

### Poids de Hamming

Le poids de Hamming $w(\vec c)$ du vecteur $\vec c$ est le nombre de 1 qu'il contient

### Distance de hamming

La distance de Hamming $d(\vec c_1, \vec c_2)$ de deux vecteurs binaires $\vec c_1$, $\vec c_2$ de même taille (messages ou mots de code) est le nombre de bits qui diffèrent entre ces deux vecteurs

Elle détermine la capacité de contrôle d'erreurs d'un code. La distance de Hamming d'un code est la distance de Hamming minimum $d_{min}$ entre deux mots de ce code

Analyse de la distance de Hamming :
- $d = 1 \rightarrow$
	- Aucune capacité de contrôle d'erreur
	- Une seule erreur peut conduire à un autre mot valide du code

		![](attachments/Pasted%20image%2020230605100707.png)

- $d=2 \rightarrow$
	- Détection d'erreur isolées mais on ne sait pas nécessairement corriger cette erreur car plusieurs mots de code valide peuvent conduire à ce mot erroné
	- Deux erreurs pourraient conduire de nouveau à un mot de code valide

		![](attachments/Pasted%20image%2020230605100906.png)

- $d=3 \rightarrow$
	- Détection et correction d'erreur simple et double (en regardant le mot de code valide qui est à la bonne distance de Hamming)

		![](attachments/Pasted%20image%2020230605101133.png)


### Théorème de Hamming

On montre que poids et distance de Hamming sont liés par les relations :

$$ 
\left\{ 
\begin{array} &
	d(\vec c_1, \vec c_2) = w(\vec c_1 \oplus \vec c_2)\\
	w(\vec c) = d(\vec c, \vec 0)
\end{array}
\right.$$