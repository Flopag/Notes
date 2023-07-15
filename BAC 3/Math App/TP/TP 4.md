# TP 4 : Von Neumann

## [Von Neumann](../Notion/Méthodes%20numérique.md)

1. Transformer l'équation analytique en numérique
	- $u(x,t)=u_j^n$
	- $u_x = \frac{u^n_{j+1}-u_j^n}{\Delta x}$
	- $u_t=\frac{u_j^{n+1}-u_j^n}{\Delta t}$
	- $u_{xx} = \frac{u_{j+1}^n-2u_j^n+u_{j-1}^n}{(\Delta x)²}$
2. Introduction du mode d'erreur
	- $u_j^n=\bar u_j^n+\varepsilon_j^n$
		- $u_j^n$ la solution approximé
		- $\bar u_j^n$ la solution exacte
		- $\varepsilon_j^n=\varepsilon(x,t)=\hat\varepsilon e^{-ik_j\Delta x}$ l'erreur (à vérif si juste parce que copier d'une source non fiable)
3. Critère de stabilité
	- $||\xi|| \le 1$
		- $\xi = \frac{\varepsilon_{n+1}}{\varepsilon_n}$ le facteur d'amplification