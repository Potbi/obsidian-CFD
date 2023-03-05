Zeitliche Mittelung der Navier-Stokes-Gleichungen (RANS) und Dekomposition der Strömungsgrößen ($u = \overline u + \tilde u$) führt zu einem Tensor turbulenter Scheinspannungen $\bar{\bar{\tau_t}}$.
$$
\bar{\bar{\tau_x}} = \rho 
	\begin{pmatrix}
		-\overline{\tilde u²} &-\overline{\tilde u\tilde v} &-\overline{\tilde u\tilde w}\\
		-\overline{\tilde u\tilde v} &-\overline{\tilde v²} &-\overline{\tilde v\tilde w}\\
		-\overline{\tilde u\tilde w} &-\overline{\tilde v\tilde w} &-\overline{\tilde w²}\\
	\end{pmatrix}
$$
Dieser enthält 9 neue Unbekante, die RANS Navier-Stokes-Gleichungen sind damit nicht mehr geschlossen. Für die Lösung dieses Schließungsproblems gibt es verschiedene Ansätze:

#### Turbulenzmodelle
Gesetze zur Bestimmung von $\bar{\bar{\tau_t}}$ oder einzelner Komponenten desselben (z.B. Prandtelsche Mischungsweghypothese)

#### Algebraische Modelle
Viskose Spannungen werden in Relations zu lokalen mittleren Größen gesetzt (z.B. Prandtl, Baldwin-Lomax)

#### Differentialgleichungsmodelle
Gleichungen für Produktion und Transport turbulenter Größen (z.B. kinetische Energie) sowie Dissipationsrate $\epsilon$ (k-$\epsilon$, k-$\omega$, Spalart-Allmaras, ...)