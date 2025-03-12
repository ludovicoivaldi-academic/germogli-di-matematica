## Richiami

Ricordiamo che se $f: V \to V$ è un operatore lineare, presa $\mathcal{B}$ base qualsiasi di $V$, definiamo la traccia come:
$$
tr(f) = \sum_i a_{ii}
$$
dove $(a_{ij}) = M_\mathcal{B}^\mathcal{B}(f)$ è la matrice di $f$ nella base $\mathcal{B}$.

Ricordiamo la seguente proprietà:
$$
tr(AB) = tr(BA)
$$
da cui segue che 
$$
tr(ABC) = tc(CAB) = tr(BCA)
$$
con $A$, $B$ e $C$ matrici quadrate della stessa dimensione.
Usando la formula di cambio di base vediamo che **la traccia di $f$ non dipende dalla base scelta**.

## Definizione e proprietà

> [!success] Definizione
> Sia $\rho: G \to GL(V)$ rappresentazione lineare, definiamo
> $$
> \begin{array}{llcl}
>   \chi_\rho: &G &\to &\mathbb{C}\\
> 			 &g &\mapsto &\chi_\rho(g) \coloneqq tr(\rho_g)
> \end{array}
> $$
> detto **carattere della rappresentazione $\rho$**.

Vediamo subito alcune proprietà importanti:

> [!danger] Proposizione
> Sia $\chi$ carattere di una rappresentazione di grado $n$, valgono:
> 1. $\chi(1) = n$,
> 2. $\chi(g^{-1}) = \chi^\ast(g) = \overline{\chi}(g) \quad \forall g \in G$,
> 3. $\chi(aga^{-1}) = \chi(g) \quad \forall a, g \in G$ ($\chi$ è costante sulle classi di coniugio).
> 
> Dove $\chi^\ast(g) = tr(\rho_g^\ast)$ è la traccia dell'operatore aggiunto.

> [!note] Dimostrazione
> 

