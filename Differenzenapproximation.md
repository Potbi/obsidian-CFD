Da keine stetige Funktion der gesuchten Variablen bekannt sind, müssen die Ableitungen numerisch approximiert werden.

![[Pasted image 20230302145945.png]]


## [[Approximation der 1. Ableitung]]

Gesucht: Approximation des Anstieges der Funktion $\phi$ in Abhängigkeit von x $(\frac{\partial \phi}{\partial x})$
Im allgemeinen sind drei Herangehensweisen üblich:
$$
\begin{array}{}
	\frac{\partial \phi}{\partial x}\bigl|_i & \approx &\frac{\phi_{i+1}-\phi_{i-1}}{2\Delta x} &\text{zentral} \\
	&\approx &\frac{\phi_{i+1}-\phi_{i}}{\Delta x} &\text{vorwärts} \\
	&\approx &\frac{\phi_{i}-\phi_{i-1}}{\Delta x} &\text{rückwärts} \\



\end{array}
$$

## [[Approximation der 2. Ableitung]]

Gesucht: Approximation der Krümmung der Funktion $\phi$ in Abhängigkeit von x $(\frac{\partial² \phi}{\partial x²})$
Im allgemeinen sind drei HErangehensweisen üblich:
$$
\begin{array}{}
	\frac{\partial² \phi}{\partial x²}\bigl|_i & \approx &\frac{\phi_{i+1}-2\phi_i+\phi_{i-1}}{\Delta x²} &\text{zentral} \\
	&\approx &\frac{\phi_{i+2}-2\phi_{i+1}+\phi_{i}}{\Delta x²} &\text{vorwärts} \\
	&\approx &\frac{\phi_{i}-2\phi_{i-1}+\phi_{i-2}}{\Delta x²} &\text{rückwärts} \\
\end{array}
$$

## zentrales Schema mit [[künstliche Dissipation]]

1.Ordnung rückwärts --> Upwind-Schema
$$
0 = \frac{u_i^{n+1}-u_i^n}{\Delta t} + c\ \frac{2u_i^n-2u_{i-1}^n}{2\Delta x}
$$
2.Ordnung vorwärts --> Burgersgleichung 
$$
0 = \frac{u_i^{n+1}-u_i^n}{\Delta t} - c\ \frac{2u_{i+1}^n-2u_{i}^n}{2\Delta x}
$$

