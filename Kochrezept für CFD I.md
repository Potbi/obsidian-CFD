Anwedung auf [[Aufstellung eines Finite Volumen Verfahrens|Finite Volumen Verfahren]] mit struktriertem Rechennetz

## Eindimensional
#### 1. Zeitschrittberechnung
- [[Hyperbolisches Gleichungssystem]] mit (streng) [[konservativ|konservativer]] und schwach/nicht konservativer Formulierung mit der Jacobimatrix $\overline{\overline A}$ .
$$
0 = \frac{\partial \vec W}{\partial t} + \frac{\partial \vec F}{\partial x} = \frac{\partial \vec W}{\partial t} + 
\overline {\overline A} \frac{\partial \vec W}{\partial x}
$$
- Lösen des [[Eigenwertproblem|Eigenwertproblems]] von $\overline{\overline A}$ :
$$
\begin{array}{l}
	\lambda(\overline{\overline A}) &= & u+a &\text{"nichtlinearer" Eigenwert, akustische Welle} \\
	& & u-a & \text{s.o.} \\
	& & u &\text{"linearer" Eigenwert, Entropiewelle} 
\end{array}
$$
- [[CFL-Bedingung]] mit größtem Eigenwert
	-> global oder lokal für jede Zelle möglich
$$
\Delta t \leq \frac{\Delta x}{\lambda_{i\, max}} \Longrightarrow \Delta t \leq \frac{\Delta x}{|u|+a}
$$
#### 2. [[künstliche Dissipation bei FV]]
- 2. und 4. Differenzen mit größtem Eigenwert skalieren und als Dissipativen Term hinzufügen
- auf Einhaltung der [[Teleskopeigenschaft]] achten
- [[Sensorfunktion]] mit repräsentativer Größe bilden


## Mehrdimensional
#### 1. Zeitschrittberechnung
- [[Hyperbolisches Gleichungssystem]] mit (streng) [[konservativ|konservativer]] und schwach/nicht konservativer Formulierung mit der Jacobimatrizen $\overline{\overline A}$ und $\overline{\overline B}$ . 
$$
0 = \frac{\partial \vec W}{\partial t} + \frac{\partial \vec F_x}{\partial x} + \frac{\vec F_y}{\partial y} = \frac{\partial \vec W}{\partial t} + \overline{\overline A}\frac{\partial \vec W}{\partial x} + \overline{\overline B} \frac{\partial \vec F_y}{\partial y}
$$
- Lösen des [[Eigenwertproblem|Eigenwertproblems]] von $\overline{\overline A}$  und $\overline{\overline B}$ :
	-> keine Entkoppelung über die Linkseigenvektoren $\overline{\overline M}^{-1}$ von $\overline{\overline A}$ möglich, da $\overline{\overline M}^{-1}$ aus $\overline{\overline A}$ gebildet wird und sich mit $\overline{\overline B}$  deshlab nicht zur Eigenwertmatrix $\overline{\overline \Lambda}$ zusammenfassen lässt. 
	-> Entkopplung nur durch quasi 1D-Betrachtung jeder Raumrichtung möglich
$$
\begin{array}{l}
	\lambda(\overline{\overline A}) &= & u+a &\text{"nichtlinearer" Eigenwert, akustische Welle} \\
	& & u-a & \text{s.o.} \\
	& & u &\text{"linearer" Eigenwert, Entropiewelle} \\
	& & u & \text{"Scherwelle" (nicht in 1D)} \\
	\\
	\lambda(\overline{\overline B}) &= & u+a &\text{"nichtlinearer" Eigenwert, akustische Welle} \\
	& & u-a & \text{s.o.} \\
	& & u &\text{"linearer" Eigenwert, Entropiewelle} \\
	& & u & \text{"Scherwelle" (nicht in 1D)}
\end{array}
$$
- [[CFL-Bedingung]] mit größtem Eigenwert
 -> global oder lokal für jede Zelle möglich
$$
\Delta t \leq \begin{bmatrix}\frac{|u|+a}{\Delta x}\  +\ \frac{|u|+a}{\Delta y} \end{bmatrix}^{-1} = \frac{\Delta y \Delta y}{\Delta y|u|+\Delta x|v| + a(\Delta x + \Delta y)}
$$
#### 2. [[künstliche Dissipation bei FV]]
Für jede Zellkoordinatenrichtung einzeln:
- 2. und 4. Differenzen mit größtem Eigenwert skalieren und als Dissipativen Term hinzufügen
- auf Einhaltung der [[Teleskopeigenschaft]] achten
- [[Sensorfunktion]] mit repräsentativer Größe bilden

Zusammenfassen der Operatoren:
$$
\vec D_{i,j} = D_{\xi}^{(2)}\vec W_{i,j}\ +\ D_{\eta}^{(2)}\vec W_{i,j}\ -\ D_{\xi}^{(4)}\vec W_{i,j}\ -\ D_{\eta}^{(4)}\vec W_{i,j}
$$
