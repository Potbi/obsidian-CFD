## Thermo
### thermische Zustandgleichung
thermisch ideales Gas
$$
p = \rho R T
$$

### kalorische Zustandsgleichung
kalorisch ideales Gas
$$
e = c_v T
$$

### Perfektes Gas
$$
\begin{array}{l}
	R &= c_p -c_v \\
	\kappa &= \frac{c_p}{c_v} \\
	c_p &= \frac{\kappa}{\kappa -1} R
\end{array}
$$
### zweiter Hauptsatz der Thermoynamik
$$
\Delta S \ge 0
$$

## Materialgesetze
### molekulare Spannungshypthese nach Stokes
Spannungstensordefinition nach Stokes
$$
\begin{array}{l}
&\bar{\bar{\tau}} = f(\bar{\bar{D}})
&\text{mit}
&\bar{\bar{D}} = 
	\begin{pmatrix}
		u_x & \frac{1}{2}(u_y + v_x) & \frac{1}{2}(u_z + w_x) \\
		\frac{1}{2}(u_y + v_x) &v_y & \frac{1}{2}(v_z + w_y) \\
		\frac{1}{2}(u_z + w_x) &\frac{1}{2}(v_z + w_y) &w_z
	\end{pmatrix} \\
	& & &\bar{\bar{D}} \ \widehat = \text{ Deformationsgeschwindigkeitstensor} \\
	& &u_x \widehat = \frac{\partial u}{\partial x} &\text{Die Komponenten sind partielle Ableitungen}
\end{array}
$$

Für Newtonsche Fluide gilt:
$$
\bar{\bar{\tau}} = 2\mu \bar{\bar{D}} + (\mu_d - \frac{3}{2}\mu) \nabla \cdot \vec q \,\bar{\bar{E}}
$$
mit den Formelzeichen:
$$
\begin{array}{l}
	\mu  &\text{dynamische Scherzähigkeit} \\
	\mu_d  &\text{Druckzähigkeit}\ (\approx 0) \\
	\bar{\bar{E}}  &\text{Einheitsmatrix}
\end{array}
$$

### der Spannungstensor
$$
\bar{\bar{\tau}} = 
	\begin{pmatrix}
	\sigma_x & \tau_{xy} &\tau_{xz} \\
	\tau_{yx} &\sigma_y &\tau_{yz} \\
	\tau_{zx} &\tau_{yz} &\sigma_z
	\end{pmatrix}
$$
