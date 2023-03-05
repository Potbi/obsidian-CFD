Die CFL-Bedingung beschreibt das Verhältnis zwischen der räumlichen und zeitlichen Diskretisierung, um eine [[Stabilität|stabile]] Strömungssimulation aufzustellen. Die CFL-Bedingung ist notwendig, aber nicht hinreichend.

#### Die Zeitschrittbegrenzung
$$
\Delta t \leq \frac{\Delta x}{|c|}
$$
Mit $c$ als die Ausbreitungsgeschwindigkeit der Störung. 
Diese ist äquivalent zu den [[Eigenwertproblem|Eigenwerten]] der Jacobimatrizen der [[schwach konservative Differentielle Form der Grundgleichungen|schwach konservativen Form]]. Für die Begrenzung des Zeitschrittes wird dann der betragsmäßig maximale Eigenwert verwendet.

Bei globalen Zeitschrittverfahren wird der Zeitschritt durch die kleinste Zelle im Netz begrenzt und bei lokalen Zeitschrittverfahren wird $\Delta t$ für jede Zelle neu berechnet und ist damit weniger ressourcenintensiv.

#### Herleitung
Für Störungsausbreitung mit konstanter Geschwindigkeit c:
$$
0 = \frac{\partial u}{\partial t} \pm c \frac{\partial u}{\partial x}
$$

[[Charakteristiken|Charakteristik]] der DGL
$$
\begin{array}{l}
	&0 &= \frac{\partial u}{\partial t} \pm c \frac{\partial u}{\partial x}\\
	&du &= \frac{\partial u}{\partial t} dt + c \frac{\partial u}{\partial x} dx \ \text{(vollständiges Differential)}\\
	\Longrightarrow & 
		\begin{bmatrix}
			0 \\
			du
		\end{bmatrix}
		&=
		\begin{bmatrix}
			1 & \pm c\\
			dt &dx
		\end{bmatrix} \cdot
		\begin{bmatrix}
			\frac{\partial u}{\partial t} \\
			\frac{\partial u}{\partial x}
		\end{bmatrix}
\end{array}
$$
#[[vollständiges Differential]]
Als Bedingung einer Charakteristik muss die Determinante $0$ sein.
$$
\Biggl| \begin{bmatrix}
	1 &\pm c \\
	dt &dx
\end{bmatrix}\Biggr|
\stackrel{!}{=} 0 = dx\ \mp c\ dt
$$
$$
\Longrightarrow \frac{dt}{dx} = \pm \frac{1}{c}
$$
Dies sind die Steigungen der Charakteristiken in einem $x,t$ System.

Beobachtungen: 
- Einfluss & Abhängigkeitsgebiet sind begrenzt durch $\frac{dt}{dx} = \frac{1}{c}$ und wird bestimmt durch physikalische und mathematische Gesetze zur Störungsausbreitung
- $\frac{dx}{dt} = \dot{x} = c$ ist die Ausbreitungsgechwindigkeit einer Störung

Aus der Darstellung geht der Einfluss der Ausbreitugsgeschindigkeit auf das Abhängigkeitsgebiet hervor. In einem [[Stabilität|stabilen]] Verfahren muss das $\color{yellow}\text{numerische Abhängigkeitsgebiet}$ immer größer sein als das $\color{green}\text{physikalische}$ --> die Steigung muss kleiner sein. Werden weniger $\color{red}\text{relevante Informationen}$ berücksichtigt als das $\color{green}\text{physikalische Abhängkeitsgebiet}$ erfordert, ist das Verfahren immer [[Stabilität|instabil]] ($\color{DodgerBlue}\text{siehe blaues Gebiet}$)
Diese Bedingung ist hinreichend, aber nicht notwendig!
![[Pasted image 20230302115303.png]]

Dies führt zu der Zeitschrittbegrenzung:
$$
\begin{array}{}
	\begin{subarray}{} \text{Abhängigkeitsbereich}\\ \text{der num. Rechnung} \end{subarray} &\geq & \begin{subarray}{} \text{physikalisch/mathematischer}\\ \text{Abhängigkeitsbereich} \end{subarray}\\
	(\frac{\Delta x}{\Delta t})_{num} &\geq &(\frac{dx}{dt})_{phys} = c\\
	\\
	\Delta t \geq \frac{\Delta x}{|c|} & & \text{CFL-Bedingung}
\end{array}
$$

