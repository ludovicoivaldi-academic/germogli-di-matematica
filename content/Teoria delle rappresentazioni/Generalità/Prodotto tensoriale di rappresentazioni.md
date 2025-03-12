## Richiami

Diamo alcuni richiami sul [prodotto tensoriale](https://www.wikiwand.com/en/articles/Tensor_product) di spazi vettoriali.

> [!success] Definizione
> Siano $V_1$ e $V_2$ due spazi vettoriali (sullo stesso campo), chiamiamo **prodotto tensoriale di $V_1$ e $V_2$** uno spazio vettoriale $W$ dotato di un'operazione di prodotto $(v_1, v_2) \mapsto v_1 \cdot v_2$ da $V_1 \times V_2$ in $W$ per cui valgano le seguenti proprietà:
> 1. L'operazione di prodotto è bilineare.
> 2. Se $(e_i)_{i \in I}$ è base di $V_1$ e $(f_j)_{j \in J}$ base di $V_2$ allora $(e_i \cdot f_j)_{i \in I, j \in J}$ è base di $W$.

^fcb7d2

Si dimostra che un tale spazio, che denotiamo con  $V_1 \otimes V_2$, esiste ed è unico a meno di isomorfismo.

> [!attention] Attenzione
> A differenza della somma diretta, il prodotto tensoriale è quindi definito a meno di isomorfismo. Esistono costruzioni più esplicite per ottenere un rappresentante.

Segue immediatamente da [[Prodotto tensoriale di rappresentazioni#^fcb7d2|(2.)]] che
$$ 
\dim(V_1 \otimes V_2) = \dim(V_1) \cdot \dim(V_2)
$$
> [!success] Definizione
> Siano $A = (a_{ij})$  e $B = (b_{kl})$ matrici a entrate nel campo $\mathbb{K}$ di dimensioni $m_1 \times n_1$ e $m_2 \times n_2$ rispettivamente. Possiamo definire il prodotto tensoriale tra matrici:
> $$
> A \otimes B = \begin{bmatrix}
> 			    a_{11}B &\cdots &a_{1n_1}B\\
> 			    \vdots &\ddots &\vdots\\
> 			    a_{m_11}B &\cdots &a_{m_1n_1}B
> 			  \end{bmatrix}
> $$
> ottenendo una matrice $(m_1 \cdot m_2) \times (n_1 \cdot n_2)$ .

> In generale se abbiamo due applicazioni lineari $f: V_1 \to W_1$ e $g: V_2 \to W_2$ tra spazi vettoriali tutti sullo stesso campo, esiste unica la mappa lineare $f \otimes g: V_1 \otimes V_2 \to W_1 \otimes W_2$ tale che:
> $$
> f \otimes g (v_1 \cdot v_2) = f(v_1) \cdot g(v_2) \qquad \forall v_1 \in V_1, v_2 \in V_2
> $$
> Infatti scelta una base $\mathcal{B}_1$ di $V_1$ e una base $\mathcal{B}_2$ di $V_2$, la mappa $f \otimes g$ è l'unica per cui vale
> $$
> M^{\mathcal{B}}_{\mathcal{B}}(f \otimes g) = M^{\mathcal{B}_1}_{\mathcal{B}_1}(f) \otimes M^{\mathcal{B}_2}_{\mathcal{B}_2}(g)
> $$ 
> dove $\mathcal{B}$ è la base di $V_1 \otimes V_2$ ottenuta dai prodotti degli elementi delle due basi.
> 
## Prodotto tensoriale di rappresentazioni

Siano $\rho^1: G \to GL(V_1)$ e $\rho^2: G \to GL(V_2)$ rappresentazioni lineare, possiamo definire la mappa $\rho: G \to GL(V_1 \otimes V_2)$ con $\rho_g \coloneqq \rho^1_g \otimes \rho^2_g$.

Questa è ben definita poiché scelte una base di $V_1$ e di $V_2$, possiamo la base di $V_1 \otimes V_2$ data dai prodotti degli elementi delle ultime e per ogni $g \in G$ vale:
$$ 
R_g = R^1_g \otimes R^2_g\quad, \quad \det(R_g) = \det(R^1_g)^{\dim(V_1)} \cdot \det(R^2_g)^{\dim(V_2)} \neq 0
$$
perciò $\rho_g$ è un elemento di $GL(V_1 \otimes V_2)$. \
Si verifica facilmente che 
$$
\begin{split} 
  R_g \cdot R_{g'} &= (R^1_g \otimes R^2_g) \cdot (R^1_{g'} \otimes R^2_{g'})\\
  &= (R^1_g \cdot R^1_{g'}) \otimes (R^2_g \cdot R^2_{g'})\\
  &= R^1_{gg'} \otimes R^2_{gg'}\\
  &= R_{gg'}
\end{split}
$$
quindi $\rho$ è omomorfismo di gruppi e quindi rappresentazione lineare, chiameremo **prodotto tensoriale delle rappresentazioni $\rho^1$ e $\rho^2$**.

## Quadrato simmetrico e quadrato alternante

> [!attention] Attenzione
> In generale non è vero che se due rappresentazioni sono irriducibili, allora il loro prodotto tensoriale è irriducibile. 

Prendiamo il caso particolare di un prodotto tensoriale con sé stesso.
Sia $\rho: G \to GL(V)$ rappresentazione. Fissata $(e_i)_{i \in [n]}$ base di $V$, possiamo definire un endomorfismo lineare $\theta: V \otimes V \to V \otimes V$ tale che:
$$
\theta(e_i \cdot e_j) = e_j \cdot e_i \qquad \forall i,j \in I
$$
Questo esiste ed è automorfismo perché manda una base in una base. È inoltre l'unica mappa lineare per cui $\theta(v \cdot w) = w \cdot v$ per ogni $v, w \in V$, quindi non dipende dalla scelta della base, e $\theta^2 = 1$. 

Abbiamo che $V \otimes V$ si decompone nella somma diretta
$$
V \otimes V = \text{Sym}^2(V) \oplus \text{Alt}^2(V)
$$
dove $\text{Sym}^2(V)$ è lo spazio degli autovettori di $\theta$ con autovalore $1$ mentre $\text{Alt}^2(V)$ è lo spazio degli autovettori di $\theta$ con autovalore $-1$.

Infatti il polinomio minimo di $\theta$ è 
$$
x^2 -1 = (x + 1)(x - 1)
$$
quindi $\theta$ è diagonalizzabile con $1$ e $-1$ unici autovalori. Volendo lavorare più esplicitamente $u \mapsto \frac{1}{2}(u + \theta(u)) \in \text{Sym}^2(V)$ e $u \mapsto \frac{1}{2}(u - \theta(u)) \in \text{Alt}^2(V)$ sono le proiezioni sui singoli spazi.

Si mostra facilmente che $(e_i \cdot e_j + e_j \cdot e_i)_{i \le j}$ e $(e_i \cdot e_j - e_j \cdot e_i)_{i \lt j}$ sono base di  $\text{Sym}^2(V)$ e $\text{Alt}^2(V)$ rispettivamente, da cui segue che
$$
\dim \text{Sym}^2(V) = \frac{n(n + 1)}{2}, \qquad \dim \text{Alt}^2(V) = \frac{n(n - 1)}{2}
$$

Infine se prendiamo la rappresentazione su $V \otimes V$ data dal prodotto tensoriale di $\rho$ con sé stessa, abbiamo
$$
\begin{array}{c l l r}
\rho_g \otimes \rho_g (e_i \cdot e_j + e_j \cdot e_i)\\
||\\
\rho_g(e_i) \cdot \rho_g(e_j) + \rho_g(e_j) \cdot \rho_g(e_i) &\in &\text{Sym}^2(V)\\ 
&&&\qquad \forall g \in G, \; i,j \in [n]\\
\rho_g \otimes \rho_g (e_i \cdot e_j - e_j \cdot e_i)\\
||\\
\rho_g(e_i) \cdot \rho_g(e_j) - \rho_g(e_j) \cdot \rho_g(e_i) &\in &\text{Alt}^2(V)
\end{array}
$$
Perciò $\text{Sym}^2(V)$ e $\text{Alt}^2(V)$ sono sottorappresentazioni di $V \otimes V$ dette **quadrato simmetrico** e **quadrato alternante** della rappresentazione $V$.

---

Leggi l'argomento successivo: [[Carattere di una rappresentazione]]
