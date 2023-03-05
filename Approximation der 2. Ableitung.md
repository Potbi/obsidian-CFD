$$
\begin{array}{}
	\frac{\partial² \phi}{\partial x²}\Bigl|_i & \approx &\frac{\phi_{i+1}-2\phi_i+\phi_{i-1}}{\Delta x²} &\text{zentral} \\
	&\approx &\frac{\phi_{i+2}-2\phi_{i+1}+\phi_{i}}{\Delta x²} &\text{vorwärts} \\
	&\approx &\frac{\phi_{i}-2\phi_{i-1}+\phi_{i-2}}{\Delta x²} &\text{rückwärts} \\
\end{array}
$$

#### Genauigkeit
Zur Feststellung der Genauigkeit der Schemata werden die Taylorentwicklungen für $\phi$ um $x_i$ für die Funktionswerte $\phi_{i+2},\ \phi_{i+1},\ \phi_i,\ \phi_{i-1},\ \phi_{i-2}$ eingesetzt. Da die Entwicklung hier nach dem 1. Term abgebrochen wird, legt der jeweils 2. Term die Ordnung des Fehlers fest. 

$$
\begin{array}{l}
	\text{zentral} &\frac{\phi_{i+1}-2\phi_i+\phi_{i-1}}{\Delta x²} &= &\frac{1}{\Delta x²} 
	\begin{pmatrix} \frac{\partial² \phi}{\partial x²}\Bigl|_i \ \Delta x² \ +\ \frac{1}{12}\frac{\partial⁴ \phi}{\partial x⁴}\Bigl|_i \ \Delta x⁴ \ +\ ... 
	\end{pmatrix} \\
	&&= & \frac{\partial² \phi}{\partial x²}\Bigl|_i\ +\ \color{red} \frac{1}{12} \phi_{xxxx}\bigl|_i\ \Delta x² \ +\ ... \ \ \mathcal{O}(\Delta x²)\\
	\\
	\text{vorwärts}  &\frac{\phi_{i+2}-2\phi_{i+1}+\phi_{i}}{\Delta x²} &= 
	&\frac{1}{\Delta x²}\begin{pmatrix} \frac{\partial² \phi}{\partial x²}\Bigl|_i\ \Delta x²\ +\ \frac{\partial³ \phi}{\partial x³}\Bigl|_i\ \Delta x³\ +\ ... \end{pmatrix} \\
	& &= &\frac{\partial² \phi}{\partial x²}\Bigl|_i\ +\ \color{green} \phi_{xxx}\bigl|_i\ \Delta x\ +\ ...\ \ \mathcal{O}(\Delta x) \\
	\\
	\text{rückwärts} &\frac{\phi_{i}-2\phi_{i-1}+\phi_{i-2}}{\Delta x²} & &\text{analog zu vorwärts}
\end{array}
$$

Der Abbruchfehler des zentralen Schemas ist $\color{red}\text{rot}$ eingefärbt und von der Ordnung $\mathcal{O}(\Delta x²)$. Deshalb ist das zentrale Schema ein Verfahren zweiter Ordnung und weißt dissipative Eigenschaften auf. Dies ist auf den Fehler zurückzuführen.

Der Abbruchfehler des vorwärts/rückwärts Schemas ist $\color{green}\text{grün}$ eingefärbt und von der Ordnung $\mathcal{O}(\Delta x)$. Deshalb sind diese Schemata Verfahren erster Ordnung und weißt dispersive Eigenschaften auf. Letzteres ist darauf zurückzuführen, dass auch Informationen der übernächsten Zelle berücksichtigt werden, obwohl physikalisch nur Interaktionnen mit der nächsten Zelle möglich sind.

Alle drei Verfahren erfüllen die [[Konsistenz|Konsistenzbedingung]].

#### [[Stabilität]]
vorwärts/rückwärts > zentral
[[Odd-Even-Decoupling]] is n Ding bei zentralen Schemata.


