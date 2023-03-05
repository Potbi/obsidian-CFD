__Ziel:__ Verwendung des Schemas 2. Ordnung global und, wo notwendig, das Schema 1. Ordnung. Z.B. an Stößen und Nichtlinearitäten.

Abschalten der 4. Differenzen mit $\epsilon$:
$$
\epsilon_i^{(4)} = max(0, k^{(4)}- \gamma_i k^{(2)}) = max(0, k^{(4)} - \epsilon_i^{(2)})
$$
Unter Verwendung der [[Sensorfunktion]] $\gamma$.

In der Burgersgleichung ergibt sich:
$$
	\frac{u_{i}^{n+1}-u_{i}^n}{\Delta t}  + c \frac{u_{i+1}^n - u_{i-1}^n}{2\Delta x} = \frac{|c|}{\Delta x} (\epsilon_i^{(2)}\color{red} \triangleright \color{green} \triangleleft \color{white} u_i - \epsilon_i^{(4)} \color{red} \triangleright \color{green} \triangleleft \color{red} \triangleright \color{green} \triangleleft \color{white}\ u_i)
$$
Der Ausdruck in der Klammer ist die [[künstliche Dissipation]]. An perfekt "glatten" Stellen nimmt $\epsilon_i^{(4)}$ den Wert $k^{(4)}$ an und die 4. Differenz ist "aktiviert". An "unglatten" Stellen hingegen wird die 4. Differenz durch $\epsilon_i^{(4)} = 0$ "abgeschaltet" und nur die 2. Differenz wird verwendet. Auch Zustände dazwischen sind möglich.