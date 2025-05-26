---
tags:
  - teoria_rappresentazioni
  - caratteri
draft: "false"
---
> [!danger] Lemma (di Schur)
> Siano $\rho^{1}: G \to \mathrm{GL}(V_1)$ e $\rho^{2}: G \to \mathrm{GL}(V_{2})$ due rappresentazioni **irriducibili** del gruppo $G$, e sia $f: V_{1} \to V_{2}$ una mappa lineare per cui vale $f \circ \rho^{1}_{g} = \rho^{2}_{g} \circ f$ per ogni $g \in G$. Allora:
> 1. Se $\rho^{1}$ e $\rho^{2}$ non sono isomorfi, abbiamo $f = 0$.
> 2. Se $V_{1} = V_{2}$ e $\rho^{1} = \rho^{2}$, $f$ è omotetia (di centro $0$).

> [!note] Dimostrazione
> (1.) Sia $W_{1}$ il nucleo di $f$. Preso $v \in W$ abbiamo $f(\rho^{1}(v)) = \rho^{2}(f(v)) = 0$, quindi $W$ è un sottospazio stabile tramite $G$ in $V_{1}$ irriducibile. Abbiamo due casi:
> 	- Se $W = V_{1}$ allora $f = 0$ e vale la tesi.
> 	- Se $W = 0$ allora $f$ è iniettivo. Osserviamo che vale $\dim(\mathrm{Im} f) = \dim V_{1} \gt 0$. Ora preso $w = f(v)$ per qualche $v \in V_{1}$ abbiamo $\rho^{2}(w) = f(\rho^{1}(v)) \in \mathrm{Im} f$. Quindi l'immagine di $f$ è un sottospazio stabile non zero di $V_{2}$,  per irriducibilità della rappresentazione $\mathrm{Im}f = V_{2}$. Dunque **la mappa $f$ è un isomorfismo di rappresentazioni**.
> 
> (2.) 
> $\square$


