$$
\begin{array}{}
	\frac{\partial \phi}{\partial x}\Bigl|_i & \approx &\frac{\phi_{i+1}-\phi_{i-1}}{2\Delta x} &\text{zentral} \\
	&\approx &\frac{\phi_{i+1}-\phi_{i}}{\Delta x} &\text{vorwärts} \\
	&\approx &\frac{\phi_{i}-\phi_{i-1}}{\Delta x} &\text{rückwärts} \\
\end{array}
$$

#### Genauigkeit
Zur Feststellung der Genauigkeit der Schemata werden die Taylorentwicklungen für $\phi$ um $x_i$ für die Funktionswerte $\phi_{i+1},\ \phi_i,\ \phi_{i-1}$ eingesetzt. Da die Entwicklung hier nach dem 1. Term abgebrochen wird, legt der jeweils 2. Term die Ordnung des Fehlers fest. 

$$
\begin{array}{l}
	\text{zentral} &\frac{\phi_{i+1}-\phi_{i-1}}{2\Delta x} &= &\frac{1}{2\Delta x} 
	\begin{pmatrix} 2\frac{\partial \phi}{\partial x}\Bigl|_i \ \Delta x \ +\ \frac{2}{6}\frac{\partial³ \phi}{\partial x³}\Bigl|_i \ \Delta x³ \ +\ ... 
	\end{pmatrix} \\
	&&= & \frac{\partial \phi}{\partial x}\Bigl|_i\ +\ \color{red} \frac{1}{6} \phi_{xxx}\bigl|_i\ \Delta x² \ +\ ... \ \ \mathcal{O}(\Delta x²)\\
	\\
	\text{vorwärts}  &\frac{\phi_{i+1}-\phi_{i}}{\Delta x} &= 
	&\frac{1}{\Delta x}\begin{pmatrix} \frac{\partial \phi}{\partial x}\Bigl|_i\ \Delta x\ +\ \frac{1}{2}\frac{\partial² \phi}{\partial x²}\Bigl|_i\ \Delta x²\ +\ ... \end{pmatrix} \\
	& &= &\frac{\partial \phi}{\partial x}\Bigl|_i\ +\ \color{green} \frac{1}{2}\phi_{xx}\bigl|_i\ \Delta x\ +\ ...\ \ \mathcal{O}(\Delta x) \\
	\\
	\text{rückwärts} &\frac{\phi_{i}-\phi_{i-1}}{\Delta x} & &\text{analog zu vorwärts}
\end{array}
$$

Der Abbruchfehler des zentralen Schemas ist $\color{red}\text{rot}$ eingefärbt und von der Ordnung $\mathcal{O}(\Delta x²)$. Deshalb ist das zentrale Schema ein Verfahren zweiter Ordnung.

Der Abbruchfehler des vorwärts/rückwärts Schemas ist $\color{green}\text{grün}$ eingefärbt und von der Ordnung $\mathcal{O}(\Delta x)$. Deshalb sind diese Schemata Verfahren erster Ordnung.

Alle drei Verfahren erfüllen die [[Konsistenz|Konsistenzbedingung]].

#### [[Stabilität]]

vorwärts/rückwärts > zentral 

Warum? Beim zentralen Schema ist [[Odd-Even-Decoupling]] möglich.

wieso, weshalb, warum, dazu müsste man hier Nachforschungen anstellen.