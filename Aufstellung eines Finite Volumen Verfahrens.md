Kontrollvolumen muss diskretisiert werden.
	--> Rechennetz
	--> der einfachste Fall ist ein strukturiertes Netz 
![[Pasted image 20230228104101.png]]
#### Annahmen:
1. $\vec{W_{i,j}}$ im Zellmittelpunkt
2. $\vec{W_{i,j}}$ Konstant im Volumenelement $\Delta V_{i,j}$
3. $\bar{\bar{F_{1}}} = \frac{1}{2} (\bar{\bar{F}}_{i,j} + \bar{\bar{F}}_{i+1 ,j})$ usw.

#### Approximation des Oberflächenintegrals:
$$
\int_{S_{i,j}} \bar{\bar F} \cdot \vec n \,dS  \approx \sum_{k=1}^{4} \bar{\bar{F_k}} \cdot \vec{n_k} \, \Delta s_k
$$
#### Aufstellen der diskreten Gleichung für eine Zelle $\Delta V_{i,j}$
$$
\iint_{V_{i,j}} \frac{\partial}{\partial t} \vec W dV = - \int_{S_{i,j}} \bar{\bar{F}} \cdot \vec n \, dS
$$
$$
\Longrightarrow \frac{\partial}{\partial t} \vec {W_{i,j}} \, \Delta V_{i,j} = -(\sum_{k=1}^{4} \bar{\bar{F_k}} \cdot \vec{n_k} \, \Delta s_k)_{i,j}
$$
#### Berechnung von $\vec{W_{i,j}}$ zum Zeitpunkt $t+\delta t$
$$\vec{W_{i,j}} (t+ \delta t) = \vec{W_{i,j}}(t) - \frac{\delta t}{\Delta V_{i,j}} (\sum_{k=1}^{4} \bar{\bar{F_k}} \cdot \vec{n_k} \, \Delta s_k)_{i,j}$$ Anfangslösung --> schrittweise Integration --> stationärer Zustand

$$
\color{green}
\begin{array}{l}
	\text{Vorteile:}& \text{- keine Ableitungen gebildet}\\
	 &\text{- gültig für beliebige Rechennetze} \\
	 &\text{- keine Transformation auf kurvenlineare Koordinaten}\\
	\color{red}
	\text{Nachteile:}& \color{red} \text{- keine Konvergenz zum stationären Zustand}\\
	 &\color{red} \text{- Integration ist nicht stabil}
\end{array}
$$
#[[Stabilität]]
#[[Konvergenz]]
Für eine Stabilisierung kann [[künstliche Dissipation bei FV|künstliche Dissipation]] eingeführt werden .

$$
$$
