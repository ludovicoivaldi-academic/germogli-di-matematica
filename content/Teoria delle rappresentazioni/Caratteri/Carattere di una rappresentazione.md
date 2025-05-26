---
tags:
  - teoria_rappresentazioni
  - caratteri
---

## Richiami

Ricordiamo che se $f: V \to V$ è un operatore lineare, presa $\mathcal{B}$ base qualsiasi di $V$, definiamo la traccia come:
$$
\mathrm{tr} (f) \coloneqq \sum_i a_{ii}
$$
dove $(a_{ij}) = M_\mathcal{B}^\mathcal{B}(f)$ è la matrice di $f$ nella base $\mathcal{B}$.

Ricordiamo la seguente proprietà:
$$
\mathrm{tr}(AB) = \mathrm{tr}(BA)
$$
da cui segue che 
$$
\mathrm{tr}(ABC) = \mathrm{tr}(CAB) = \mathrm{tr}(BCA)
$$
con $A$, $B$ e $C$ matrici quadrate della stessa dimensione.
Usando la formula di cambio di base e applicando la seconda proprietà vediamo che **la traccia di $f$ non dipende dalla base scelta**.

## Definizione e proprietà

> [!success] Definizione
> Sia $\rho: G \to \mathrm{GL}(V)$ rappresentazione lineare, definiamo
> $$
> \begin{array}{llcl}
>   \chi_\rho: &G &\to &\mathbb{C}\\
> 			 &g &\mapsto &\chi_\rho(g) \coloneqq \mathrm{tr}(\rho_g)
> \end{array}
> $$
> detto **carattere della rappresentazione $\rho$**.

Vediamo subito alcune proprietà importanti:

> [!danger] Proposizione
> Sia $\chi$ carattere di una rappresentazione di grado $n$, valgono:
> 1. $\chi(1) = n$,
> 2. $\chi(g^{-1}) = \chi(g)^\ast = \overline{\chi(g)} \quad \forall g \in G$,
> 3. $\chi(aga^{-1}) = \chi(g) \quad \forall a, g \in G$ ($\chi$ è costante sulle classi di coniugio).
> 
> ($^\ast$ e $\overline{}$ sono l'aggiunto e il coniugato, che in dimensione $1$ corrispondono)

> [!note]- Dimostrazione
> 1. $\chi(1) = \mathrm{tr}(\mathbb{1}_n) = \sum_{i = 1}^n 1 = n$
> 2. [[Sottorappresentazioni#Forme hermitiane|Abbiamo visto]] che possiamo dare un prodotto hermitiano a $V$ per cui $\rho_g$ è un operatore unitario, quindi l'inverso di $\rho_g$ è uguale all'aggiunto. Ora scelta una base unitaria di $V$ abbiamo che $R_g^\ast = \overline{R_g^t}$ e quindi 
>    $$
>    \chi(g^{-1}) = \mathrm{tr}(\rho_g^{-1}) = \mathrm{tr}(R_g^\ast) = \sum_{i = 1}^n \overline{r_{ii}(g)} = \overline{\chi(g)}
>  $$
> 3. Basta ricordare le proprietà della traccia:
>    $$ 
>    \chi(aga^{-1}) = \mathrm{tr}(\rho_a\rho_g\rho_a^{-1}) = \mathrm{tr}(\rho_g\cancel{\rho_a\rho_a^{-1}}) = \chi(g)
>  $$

> [!danger] Proposizione
> Siano $\rho^1: G \to \mathrm{GL}(V_1)$ e $\rho^2: G \to \mathrm{GL}(V_2)$ due rappresentazioni lineari di $G$, con $\chi_1, \chi_2$ i rispettivi caratteri. Allora:
> 1. Il carattere $\chi$ della somma diretta $V_1 \oplus V_2$ è uguale a $\chi_1 + \chi_2$.
> 2. Il carattere $\psi$ del prodotto tensoriale $V_1 \otimes V_2$ è uguale a $\chi_1 \cdot \chi_2$.

^919cf7

> [!note]- Dimostrazione
> Presa una base $(e_1, \dots, e_n)$ di $V_1$ e $(f_1, \dots, f_n)$ di $V_2$, per un elemento $g$ di $G$ abbiamo:
> 1. $(e_1, \dots, e_n, f_1, \dots, f_m)$ è base di $V_1 \oplus V_2$, e in queste tre basi vale:
>   $$
>  \mathrm{tr}(R_g) = \mathrm{tr}(\begin{pmatrix}R^1_g &0\\ 0 &R^2_g \end{pmatrix}) = \mathrm{tr}(R^1_g) + \mathrm{tr}(R^2_g)
>  $$
> 2. $(e_i \cdot f_j)_{i \in \{1, \dots, n\}}^{j \in \{1, \dots, m\}}$ è base di $V_1 \otimes V_2$, e in queste tre basi vale:
>    $$
>  \mathrm{tr}(R_g) = \mathrm{tr}(R^1_g \otimes R^2_g) = \mathrm{tr}(R^1_g) \cdot \mathrm{tr}(R^2_g)
>  $$
> 
> L'ultima uguaglianza si verifica facilmente dalla definizione di prodotto tensoriale di matrici.

In realtà nell'ultima proposizione non serve che la rappresentazione sia effettivamente somma diretta (prodotto tensoriale), ma è sufficiente che sia isomorfa a quest'ultima. Infatti **rappresentazioni isomorfe hanno lo stesso carattere**.

> [!danger] Proposizione
> Siano $\rho^1: G \to \mathrm{GL}(V_1)$ e $\rho^2: G \to \mathrm{GL}(V)$ rappresentazioni isomorfe, allora i caratteri $\chi_1$ e $\chi_2$ delle rappresentazioni sono uguali.

> [!note]- Dimostrazione
> Per definizione di rappresentazioni isomorfe esiste $f: V_1 \to V_2$ isomorfismo lineare tale che $f \circ \rho^1_g = \rho^2_g \circ f$ per ogni $g \in G$. Abbiamo quindi: 
> $$
> \chi_2(g) = \mathrm{tr}(\rho^2_g) = \mathrm{tr}(f \circ \rho^1_g \circ f^{-1}) = \mathrm{tr}(\rho^1_g) = \chi_1(g)
> $$

## Carattere del quadrato simmetrico e alternante

Riprendiamo la costruzione in [[Prodotto tensoriale di rappresentazioni#Quadrato simmetrico e quadrato alternante]] e dimostriamo quanto segue:

> [!danger] Proposizione
> Sia $\rho: G \to \mathrm{GL}(V)$ rappresentazione lineare di $G$ con carattere $\chi$. Siano $\chi_\sigma^2$ il carattere di  $\mathrm{Sym}^2(V)$ e $\chi_\alpha^2$ li carattere di $\mathrm{Alt}^2(V)$. 
> 
> Allora per ogni $g \in G$ abbiamo
> $$
> \begin{gather}
>   \chi_\sigma^2(g) = \frac{1}{2}(\chi(g)^2 + \chi(g^2))\\
>   \chi_\alpha^2(g) = \frac{1}{2}(\chi(g)^2 - \chi(g^2))
> \end{gather}
> $$

> [!note]- Dimostrazione
> Fissato $g \in G$, dato che $\rho_g$ è operatore unitario per qualche prodotto hermitiano, vale il teorema spettrale ed esiste una base di $V$ formata da autovettori (di $\rho$).
> 
> Prendiamo quindi $(e_1, \dots, e_n)$ base di $V$ per cui la matrice $R_g$ ha la forma
> $$
> R_g = \begin{pmatrix} \lambda_1 &0 &0\\ 0 &\ddots &0\\ 0 &0 &\lambda_n \end{pmatrix},
> $$
> è immediato che 
> $$
> \chi(g) = \sum_{i=1}^n \lambda_i, \quad \chi(g^2) = \sum_{i=1}^n \lambda_i^2.
> $$
>
> Sappiamo inoltre che $(e_i \cdot e_j + e_j \cdot e_i)_{i \le j}$ è base di $\mathrm{Sym}^2(V)$ e
> $$
> (\rho_g \otimes \rho_g)(e_i \cdot e_j + e_j \cdot e_i) = \lambda_i\lambda_j(e_i \cdot e_j + e_j \cdot e_i),
> $$
> quindi 
> $$
> \chi_\sigma^2(g) = \sum_{i \le j} \lambda_i\lambda_j = \sum_{i \lt j} \lambda_i\lambda_j + \sum_i \lambda_i^2 = \frac{1}{2}(\sum_i \lambda_i)^2 + \frac{1}{2}\sum_i \lambda_i^2
> $$
> da cui la prima identità. Ricordando che $V \otimes V = \mathrm{Sym}^2(V) \oplus \mathrm{Alt}^2(V)$ e (1.), (2.) di [[Carattere di una rappresentazione#^919cf7]], abbiamo
> $$
> \chi_{\alpha}^2(g) = \chi(g)^2 - \chi_{\sigma}^2(g) = \frac{1}{2}(\chi(g)^2 - \chi(g^2).
> $$

---

Leggi l'argomento successivo: [[Lemma di Shur]]










