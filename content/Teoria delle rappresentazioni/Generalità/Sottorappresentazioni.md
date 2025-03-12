---
tags:
  - teoria_rappresentazioni
  - generalità
---
## Sottospazi stabili

Se prendiamo una rappresentazione lineare $\rho: G \to GL(V)$, possiamo definire un'azione sull'insieme $X$ dei sottospazi vettoriali di $V$ come segue:
$$
\begin{array}{r c l c l}
G &\times &X &\to &X\\
(g &, &W) &\mapsto &\rho_g W 
\end{array}
$$
abbiamo infatti 
$$
\begin{split}
&1W = \rho_1 W = Id_V W = W\\ 
&(gh)W = \rho_{gh}W = \rho_g \rho_h W = g(hW) \quad  \forall g, h, \in G
\end{split}
$$
Ci interessiamo ai sottospazi in cui lo stabilizzatore è tutto il gruppo $G$.

> [!success] Definizione
> Sia $\rho: G \to GL(V)$ rappresentazione lineare e $W$ sottospazio di $V$.
> 
> Diciamo che $W$ è **stabile per $G$** (o $G$-invariante) se è stabile per l'azione sopra definita, i.e. $\rho_g W \subset W \  \forall g \in G$.

In questi sottospazi è ben definita, per ogni $g$ elemento di $G$, la restrizione $\rho_g \vert_W^W \in GL(W)$; vale inoltre che $\rho_{(gg')} \vert_W^W = \rho_g \vert_W^W \cdot \rho_{g'} \vert_W^W$, il che giustifica la prossima definizione:

> [!success] Definizione
> Sia $\rho: G \to GL(V)$ rappresentazione e $W$ sottospazio stabile per $G$, chiamiamo $\rho^W: G \to GL(W)$ la rappresentazione data da $\rho^W(g) \coloneqq \rho_g \vert_W^W$ , detta **sottorappresentazione di $V$**.

## Forme hermitiane

Presa una rappresentazione lineare, vorremmo costruire un prodotto hermitiano sullo spazio di rappresentazione per cui gli automorfismi della rappresentazione si "comportano bene", per esempio sono sempre diagonalizzabili, preservano l'ortogonalità e le distanze.
Enunciamo quindi il nostro primo teorema:

> [!danger] Teorema
> Sia $\rho: G \to GL(V)$ rappresentazione lineare, esiste un prodotto hermitiano $h: V \times V \to \mathbb{C}$ per cui tutti i $\rho_g$ sono operatori unitari.

> [!note]- Dimostrazione
> Sia $\mathcal{B}$ base di $V$, lo spazio ammette un prodotto hermitiano $\mathsf{h}$, per esempio quello dato dal prodotto hermitiano canonico tra le coordinate dei vettori nella base $\mathcal{B}$. Definiamo la funzione:
> $$
> h(v, w) \coloneqq \sum_{g \in G} \mathsf{h}(\rho_g(v), \rho_g(w))
> $$
> Si mostra facilmente che $h$ è un prodotto hermitiano su $V$ e preso $g$ elemento di $G$, vale $h(\rho_g(v), \rho_g(w)) = \sum_{t \in G} \mathsf{h}(\rho_{gt}(v), \rho_{gt}(w)) = h(v, w)$ dato che la moltiplicazione per $g$ permuta gli elementi di $G$.
> 
> $\square$

Segue un teorema molto importante che ci permetterà di "fattorizzare" le rappresentazioni:

> [!danger] Teorema
> Sia $\rho: G \to GL(V)$ rappresentazione e $W$ sottospazio di $V$ stabile per $G$, allora esiste sempre un sottospazio $W^0$ stabile per $G$ e complementare a $W$ ($W \cap W^0 = \{0\}$ e $W + W^0 = V$).

^04c035

> [!note]- Dimostrazione
> Basta prendere $W^0 = W^\perp$ complemento ortogonale a $W$ rispetto al prodotto hermitiano del teorema precedente. Dato che gli operatori unitari mandano elementi ortogonali in elementi ortogonali segue immediatamente che $W^0$ è anch'esso stabile per $G$.
> 
> $\square$
## Somma diretta di rappresentazioni

Siano $\rho: G \to GL(V)$ e $\psi: G \to GL(W)$ due rappresentazioni lineari, posso costruire una nuova rappresentazione $\rho \oplus \psi$ di $G$ sullo spazio $V \oplus W$ della somma diretta tra $V$ e $W$ nel seguente modo:
$$
(\rho \oplus \psi)_g(v, w) \coloneqq (\rho_g(v), \psi_g(w)) \quad g \in G, v \in V, w \in W
$$
e dirò che $V \oplus W$ è **somma diretta** delle rappresentazioni $V$ e $W$.

Notiamo che se identifichiamo $V$ e $W$ con $V \times \{0\}$ e $\{0\} \times W$ rispettivamente, sono entrambi sottospazi stabili per $G$ e $\rho = (\rho \oplus \psi)_{\vert_V}, \ \psi = (\rho \oplus \psi)_{\vert_W}$.

Viceversa se abbiamo $\rho: G \to GL(V)$ rappresentazione e $W, W^0$ sottospazi in somma diretta con $V$ entrambi stabili per $G$. Allora ogni vettore $v$ di $V$ e per ogni $g$ in $G$ abbiamo  ^75f939
$$
\rho_g(v) = \rho^W_g(w) + \rho^{W^0}_g(w^0)
$$
dove $v = w + w^0, \ w \in W, w^0 \in W^0$.\
Cioè $\rho$ è isomorfo alla rappresentazione $\rho^W \oplus \rho^{W^0}$ (l'isomorfismo è quello classico $(w, w^0) \mapsto w + w^0$). Anche in questo caso per semplicità diremo che $V$ è somma diretta delle rappresentazioni $W$ e $W^0$ e scriveremo $V = W \oplus W^0$.

## Rappresentazioni irriducibili

Se chiamiamo $V = W \oplus W^0$ **fattorizzazione** di $V$, è abbastanza intuitivo cosa significhi che una rappresentazione è irriducibile, diamo comunque una definizione formale:

> [!success] Definizione
> Una rappresentazione $\rho: G \to GL(V)$ si dice **irriducibile** se gli unici sottospazi stabili per $G$ sono quelli banali, o equivalentemente le uniche fattorizzazioni sono $V = V \times \{0\}$ e $V = \{0\} \times V$.

Vediamo subito un teorema che ne giustifica l'importanza:

> [!danger] Teorema (di Maschke)
> Ogni rappresentazione è somma diretta di rappresentazioni irriducibili.

> [!note]- Dimostrazione
> La dimostrazione si può fare per induzione sul grado della rappresentazione.
> 
> Sia $\rho: G \to GL(V)$ rappresentazione, abbiamo due casi:
> - $V$ è irriducibile
> - $V$ ammette un sottospazio stabile $W$ non banale:
>    in tal caso esiste per [[Sottorappresentazioni#^04c035]] un sottospazio $W^0$ stabile per $G$ e complementare a $W$.
>    Per quanto visto ([[Sottorappresentazioni#^75f939]]) $V$ è somma diretta delle rappresentazioni $W$ e $W^0$, che avranno dimensione inferiore a quella di $V$ e per ipotesi induttiva saranno a loro volta somma diretta di rappresentazioni irriducibili.
> 
> $\square$

Come conseguenza di questo teorema potremo limitarci per la maggior parte a studiare soltanto le rappresentazioni irriducibili e poi estendere i risultati per somma diretta.

> [!attention] Attenzione
> In generale una fattorizzazione **non è unica**, infatti se abbiamo $\rho: G \to GL(V)$ con $\rho_g = Id_V$ per ogni $g \in G$ tutti i sottospazi sono stabili e abbiamo tanti modi di mettere in somma diretta la rappresentazione quanti sono i modi di mettere in somma diretta $V$.
> 
> Basta prendere $V$ di dimensione 2 per avere infinite coppie di sottospazi in somma diretta (ogni coppia di rette non coincidenti passanti per l'origine).

---

Leggi l'argomento successivo: [[Prodotto tensoriale di rappresentazioni]].
