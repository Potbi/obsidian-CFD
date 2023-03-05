Eine streng [[konservativ]]e Form

Hergeleitet aus
- Massenerhaltung
- Impulserhaltung
- Energieerhaltung

## Gleichungen
für 2D
#### Ausführliche Schreibweise:
[[Kontinuitätsgleichung]]
$$
\begin{equation}
	0= \iint_{V}^{}\frac{\partial \rho}{\partial t} dV 
	+ \int_{S} \rho(\vec{q}\cdot \vec{n})dS
\end{equation}
$$
[[Impulserhaltungsgleichung]]
$$
\begin{equation}
	0= \iint_{V} \frac{\partial \rho \vec q}{\partial t} dV 
	+ \int_{S} \rho \vec q(\vec{q}\cdot \vec{n})dS
	+ \int_{S} p \vec n dS
	- \int_{S} \bar{\bar{\tau}} \cdot \vec n dS
\end{equation}
$$
[[Energieerhaltungsgleichung]]
$$
\begin{equation}
	0= \iint_{V}^{}\frac{\partial (\rho E)}{\partial t} dV
	+ \int_{S} \rho H (\vec q \cdot \vec n)dS
	- \int_{S} (\bar{\bar{\tau}} \cdot \vec n)\vec q dS
	+ \int_{S} \vec K \cdot \vec n dS
\end{equation}
$$

#### Kompakte Schreibweise:
$$
\begin{equation}
	0 =\iint_{V} \frac{\partial}{\partial t} \vec W dV
	+ \int_{S} \bar{\bar{F}} \cdot \vec n dS
\end{equation}
$$
$\vec W$ = Vektor der Konservativen Variablen
$\bar{\bar{F}}$ = Flussdichtetensor

$$
\begin{equation}
	\vec W =
	\begin{bmatrix}
	\rho \\
	\rho u \\
	\rho v\\
	\rho E
	\end{bmatrix}
\end{equation}
$$
Der Flussdichtetensor wird in den konvektiven Teil $\bar{\bar{F_C}}$ 
$$
\begin{equation}
	\bar{\bar{F_C}} =
	\begin{bmatrix}
		\begin{array}{l}
			\rho \vec q\\
			\rho u \vec q +p \vec{i_x} \\
			\rho v \vec q + p \vec{i_y}\\
		\rho H \vec q
		\end{array}
	\end{bmatrix}
\end{equation}
$$

und den viskosen Teil $\bar{\bar{F_V}}$ aufgeteilt. $\vec i$ ist der Einheitsvektor.
$$
\begin{equation}
	\bar{\bar{F_V}} =
	\begin{bmatrix}
		\begin{array}{l}
			0 &\vec{i_x} &+ &0 &\vec{i_y} \\
			\sigma_x  &\vec{i_x} &+ &\tau_{xy} &\vec{i_y} \\
			\tau_{xy} &\vec{i_x} &+ &\sigma_y &\vec{i_y}\\
			(u \sigma_x + v \tau_{xy} + k \frac{\partial T}{\partial x}) &\vec{i_x} &+ &(u \tau_{xy} + v \sigma_y + k \frac{\partial T}{\partial y}) &\vec{i_y}
		\end{array}
	\end{bmatrix}
\end{equation}
$$
