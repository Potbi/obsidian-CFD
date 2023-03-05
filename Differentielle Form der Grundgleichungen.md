Wird durch Anwendung des [[Gaußschen Integralsatzes]] auf die [[Integrale Form der Grundgleichungen|Integrale Form]] gebildet. Sie ist stark [[konservativ]], kann jedoch in eine [[schwach konservative Differentielle Form der Grundgleichungen|schwach konservative Form]] überführt werden.

## kompakte Schreibweise in 3D
$$
\begin{equation}
	0 = \frac{\partial \vec W}{\partial t}
	+ \frac{\partial \vec{F_x}}{\partial x}
	+ \frac{\partial \vec{F_y}}{\partial y}
	+ \frac{\partial \vec{F_z}}{\partial z}
\end{equation}
$$
$\vec W$ = Vektor der konservativen Variablen
$\vec F$ = Flussdichtevektoren

mit: 
$$
\begin{equation}
	\vec W =
	\begin{bmatrix}
	\rho \\
	\rho u \\
	\rho v\\
	\rho w\\
	\rho E
	\end{bmatrix}
\end{equation}
$$
$$
\begin{array}{l}
	\vec{F_x} = \vec{F_{Cx}} - \vec{F_{Vx}}     &\vec{F_{y}} = \vec{F_{Cy}} - \vec{F_{Vy}} 
	&\vec{F_{z}} = \vec{F_{Cz}} - \vec{F_{Vz}} \\
	\vec{F_{Cx}} = 
		\begin{bmatrix} 
			\rho u\\ \rho u² + p\\ \rho uv \\ \rho uw \\ \rho Hu
		\end{bmatrix}
	&\vec{F_{Cy}} = 
		\begin{bmatrix} 
			\rho v\\ \rho uv\\ \rho v² + p \\ \rho vw \\ \rho Hv
		\end{bmatrix}
	&\vec{F_{Cz}} = 
		\begin{bmatrix} 
			\rho w\\ \rho uw\\ \rho vw \\ \rho w² + p \\ \rho Hw
		\end{bmatrix} \\
	\vec{F_{Vx}} = 
		\begin{bmatrix} 
			0\\ \color{red}\sigma_x\\ \color{red}\tau_{xy}\\ \color{red}\tau_{xz}\\ u \sigma_x + v\tau_{xy} + w\tau_{xz} + k\frac{\partial T}{\partial x}
		\end{bmatrix}
	&\vec{F_{Vy}} = 
		\begin{bmatrix} 
			0\\ \color{red}\tau_{yx}\\ \color{red}\sigma_y\\ \color{red}\tau_{yz}\\ u \tau_{yx} + v\sigma_y + w\tau_{yz} + k\frac{\partial T}{\partial y}
		\end{bmatrix}
	& \vec{F_{Vx}} = 
		\begin{bmatrix} 
			0\\ \color{red}\tau_{zx}\\ \color{red}\tau_{zy}\\ \color{red}\sigma_z \\ u \tau_{zx} + v\tau_{zy} + w\sigma_z + k\frac{\partial T}{\partial z}
		\end{bmatrix}
\end{array}
$$

$\vec{F_{C}}$ = konvektiver Anteil des Flussdichtevektors
$\vec{F_{V}}$ = viskoser Anteil des Flussdichtevektors
In $\color{red}rot$ markiert ist der [[thermodynamische Beziehungen und Materialgesetze#der Spannungstensor|Spannungstensor]] $\bar{\bar{\tau}}$ .

Formelzeichen:
$$
\begin{array}{l} \\
	\rho &Dichte \\
	u,v,w &Geschwindigkeitskomponenten \\
	t & Zeit \\
	p & Druck \\
	\bar{\bar{\tau}} & viskoser\ Spannungstensor \\
	E & massenspezifische\ Gesamtenergie \\
	H & massenspezifische\ Gesamtenthalpie \\
	k & Wärmeleitkoeffizient\\
	T & Temperatur
\end{array}$$