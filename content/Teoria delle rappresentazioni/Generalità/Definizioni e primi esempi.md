---
tags:
  - teoria_rappresentazioni
  - generalità
---
## Definizioni

> [!success] Definizione
> Sia $G$ gruppo  e $V$ spazio vettoriale complesso, una **rappresentazione lineare** di $G$ è un omomorfismo di gruppi
> $$
> \rho: G \to GL(V)
> $$
> dove con $GL(V)$ si indica il gruppo degli automorfismi di $V$.
> Lo spazio $V$ è detto **spazio di rappresentazione di $G$**.

Quando $\rho$ è data, talvolta per semplicità diciamo che $V$ è **rappresentazione di $G$**.

Per alleggerire la notazione in seguito indicheremo l'elemento $\rho(g) \in GL(V)$ con $\rho_g$, in modo da poter scrivere per esempio $\rho_g(v)$ al posto di $\rho(g)(v)$.

> [!attention] Attenzione
> Se non diversamente specificato supponiamo sempre $G$ gruppo finito e $V$ di dimensione finita.

> [!success] Definizione
> Sia $\rho: G \to GL(V)$ una rappresentazione, diciamo che il **grado** di tale rappresentazione è $n = \dim V$.

### Rappresentazioni isomorfe

Se abbiamo $f: V \to V'$ isomorfismo di spazi vettoriali, vogliamo dire che una mappa lineare $T: V \to V$ corrisponde, a meno di passare per $f$, ad una mappa $T': V' \to V'$. Quindi se "confondiamo" gli elementi $v$ di $V$ con quelli dell'immagine $f(v)$ in $V'$, le mappe $T$ e $T'$ sono identiche, in altre parole il seguente diagramma commuta:
$$
\begin{CD}
V @>T>> V \\
@VfVV @VfVV \\
V' @>T'>> V'
\end{CD}
$$
Usiamo questo concetto per dare una definizione di isomorfismo tra rappresentazioni.

> [!success] Definizione
> Due rappresentazioni $\rho: G \to GL(V)$ e $\rho': G \to GL(V')$ si dicono **isomorfe** se esiste un isomorfismo lineare $f: V \to V'$ e vale:
> $$
> f \circ \rho_g = \rho'_g \circ f \quad \forall g \in G
> $$
## Osservazioni

> [!tip] Osservazione
> Sia $\rho: G \to GL(V)$ rappresentazione di grado $n$.
> 
> Fissata $\mathcal{B} = (e_1, \dots, e_n)$ base di $V$, per ogni elemento $g$ del gruppo possiamo identificare la mappa lineare $\rho_g$ con la matrice $R_g = M_\mathcal{B}^\mathcal{B}(\rho_g)$ la cui colonna i-esima sono le coordinate di $e_i$ nella base $\mathcal{B}$.
>
> Notiamo che vale $det(R_g) \neq 0,\, R_{gg'} = R_g \cdot R_{g'} \quad \forall g, g' \in G$.

> [!tip] Osservazione
> Data una coppia di indici $(i,j) \in \{1, \dots, n\}^2$, possiamo definire la mappa $r_{ij}: G \to \mathbb{C}$ dove $r_{ij}(g)$ corrisponde all'entrata ij-esima della matrice $R_g$.

Questo ci tornerà utile in seguito per scrivere alcune funzioni ed enunciare alcuni risultati in modo più esplicito.

## Esempi

> [!example] Esempio
> Se $\rho: G \to GL(V)$ ha grado $1$, possiamo identificare $GL(V)$ con $\mathbb{C}^\times$ gruppo degli elementi invertibili di $\mathbb{C}$.
>
>Notiamo inoltre che se $G$ ha ordine n, preso un elemento $g$ di $G$ , vale:
>$$
>(\rho_g)^n = \rho_{g^n} = \rho_1 = 1 
>$$
>Quindi $\rho_g$ è una radice n-esima dell'unità.
> 
> Nel caso particolare in cui $\rho(g) = 1$ per ogni $g \in G$, diremo che la rappresentazione è **banale**.

> [!example] Esempio
> Sia $G$ gruppo, prendiamo come spazio vettoriale l'[algebra gruppo](https://mathworld.wolfram.com/GroupAlgebra.html) $\mathbb{C}[G] = \{ \sum_{i=1}^n \lambda_i g_i \ | \ \lambda_i \in \mathbb{C}, \ g_i \in G\}$ e definiamo la mappa
> $$
> \begin{array}{l l c r l c l}
>   \rho: &G &\to &GL(\mathbb{C}[G])\\
>   &g &\mapsto &\rho_g: &\mathbb{C}[G] &\to &\mathbb{C}[G]\\
>   & & & &\sum_{i=1}^n \lambda_i g_i &\mapsto &\sum_{i=1}^n \lambda_i (gg_i) 
> \end{array}
> $$
> Si mostra facilmente che quest'ultima è una rappresentazione lineare di $G$, detta **rappresentazione regolare**.
> 
> Notiamo che il grado della rappresentazione corrisponde con l'ordine del gruppo, dato che gli elementi di $G$ formano una base.

---

Leggi l'argomento successivo: [[Sottorappresentazioni]].



