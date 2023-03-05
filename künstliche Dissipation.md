- Maßnahme gegen [[Odd-Even-Decoupling]]
- Künstliche Dissipation -> Filter für hohe Frequenzen
- Kopplungsterm auf [[Approximation der 1. Ableitung|Zentrales Schema]] angewandt
### Kompakte Schreibweise für erste Differenzen
$$
\begin{array}{l}
	\text{Vorwärts-Differenz}& \color{red} \triangleright (\phi)|_i & = \phi_{i+1} - \phi_i\\
	\text{Rückwärts-Differenz}& \color{green} \triangleleft  (\phi)|_i & = \phi_{i} - \phi_{i-1}\\
	\text{2. Differenz}& \color{red} \triangleright(\color{green} \triangleleft(\phi)|_i \color{red} ) |_i& = \color{green} \triangleleft(\phi)|_{i+1} \color{white} -\color{green} \triangleleft(\phi)|_i\\
	& &= \color{red} \triangleright \color{green} \triangleleft \color{white} u_i \approx \Delta x² (\frac{\partial² u}{\partial x²})
\end{array}
$$
### Vorgehen
#### 1. Hinzufügen der künstlichen Dissipation
$$\color{DodgerBlue} \text{Upwind Schema} \Longleftrightarrow \text{zentrales Schema + künstliche Viskosität} $$
Hilfsmittel: Lineare Burgersgleichung koppelt 1. räumliche und zeitliche Ableitungen mit der 2. räumlichen Ableitung (viskose rechte Seite).
$$
\begin{array}{l}
	\frac{u_{i}^{n+1}-u_{i}^n}{\Delta t}  + c \frac{u_{i+1}^n - u_{i-1}^n}{2\Delta x} &= &k^{(2)} \frac{|c|}{\Delta x} (\color{red} \triangleright \color{green} \triangleleft \color{white} u_i) &;\text{mit}\ k^{(2)} = \frac{1}{2}\\
	&= & \frac{1}{2} \frac{|c|}{\Delta x} 
		\begin{pmatrix}  
			u_{i+1}^n - 2u_i^n + u_{i+1}^n
		\end{pmatrix}
\end{array}
$$
Durch Fusion der beiden räumlichen Ableitungsterme enstehen einseitige 1. Differenzenterme, die je nach Strömungsrichtung dem Vorwärts- oder Rückwärtsschema entsprechen und immer stromauf gerichtet sind. Dies entspricht dem Upwind-Schema angewendet auf die Burgersgleichung (1-D viskose Str)
$$
\begin{array}{l}
	\text{für}\ c>0 & \frac{u_{i}^{n+1}-u_{i}^n}{\Delta t}  + c \frac{2u_{i}^n - 2u_{i-1}^n}{2\Delta x} &= 0 &\Longrightarrow \text{rückwärts 1.Ordnung} \\
	\\
	\text{für}\ c<0 & \frac{u_{i}^{n+1}-u_{i}^n}{\Delta t}  - c \frac{2u_{i+1}^n - 2u_{i}^n}{2\Delta x} &= 0 &\Longrightarrow \text{vorwärts 1.Ordnung}
\end{array}
$$
Vorwärtsschema nur durch unsaubere Umformung und cheaten bei Vorzeichen möglich.
Das enstandene Verfahren ist nur noch 1. Ordnung, jedoch stabiler wegen der einseitigen Differenz.

#### Steigern der Genauigkeit auf 2. Ordnung
__Beobachtung:__ gerade Ableitunsgterme wirken viskos
__Ziel:__ Terme wie 4. Ableitungen einbringen
__Vorgehen:__
- Bildung 4. zentraler Differenzen
$$
\begin{array}{l}
	\color{red} \triangleright \color{green} \triangleleft \color{red} \triangleright \color{green} \triangleleft \color{white} u_i &= &u_{i+2} - 4u_{i+1} + 6u_i - 4u_{i-1} + u_{i-2} \\
	&\approx &\Delta x⁴(\frac{\partial⁴ u}{\partial x⁴})_i
\end{array}
$$
- 4. Differenz anstatt 2. Differenz in Burgersgleichung nutzen
	--> Vorzeichen der rechten Seite umkeheren, wegen positiven Vorzeichen des zentralen Summanden der 4. Differenz
$$
\begin{array}{}
	\frac{u_{i}^{n+1}-u_{i}^n}{\Delta t}  + c \frac{u_{i+1}^n - u_{i-1}^n}{2\Delta x} &= &-k^{(4)} \frac{|c|}{\Delta x} \color{red} \triangleright \color{green} \triangleleft \color{red} \triangleright \color{green} \triangleleft \color{white}\ u_i &\ \text{mit}\ \frac{1}{32}\leq k^{(4)} \leq \frac{1}{128}
\end{array}
$$
Die viskose rechte Seite diseser Gleichung ist von 3. Ordnung.
Im Ergebnis ist diese Gleichung räumlich noch von 2. Ordnung (nach Fusion der räumlichen Terme).
Die Fourier-Analyse hiervon zeigt ein stabiler Verhalten.
__Problem:__ An Diskontnuitäten entstehen Oszillationen (nach Godunov sind nur Verfahren 1. Ordnung monoton)
__Lösung:__ [[Zentrales Schema mit Mischung von 2. und 4. Differenzen|Mischung von Verfahren 1. und 2. Ordnung]]. 