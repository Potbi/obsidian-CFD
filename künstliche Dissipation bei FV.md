Die Auswertung der [[künstliche Dissipation|küstlichen Dissipation]] in den Zellmittelpunkten verletzt die [[Teleskopeigenschaft]] und damit die [[konservativ|Konservativität]], da die Differenzen sich immer auf die Mittelpunkte beziehen und die Flüsse über die Ränder nicht berücksichtigen. 
Als Abhilfe wird die künstliche Dissipation als Differnez der Werte an den Zellwände aufgestellt.
![[Pasted image 20230305153754.png]]
Dies wird zusammengefasst zu einer Dissipationsfunktion $\vec D(\vec W_i)$ zusammengefasst und der diskreten Schreibiweise hinzugefügt.
$$
\begin{array}{l}
	&\vec D^{(2)}(\vec W_i) &= &\epsilon^{(2)}\overline \lambda_{i+\frac{1}{2}}(\vec W_{i+1}-\vec W_i)-\epsilon^{(2)}\overline \lambda_{i-\frac{1}{2}}(\vec W_{i}-\vec W_{i-1}) \\
	& &= &\triangleright (\epsilon^{(2)}\overline \lambda_i)\triangleleft \vec W_i \\
	\Longrightarrow &\frac{d}{dt}\vec W_i &= &-\frac{1}{V_i}[\vec F_{i+\frac{1}{2}}^{s}-\vec F_{i+\frac{1}{2}}^{s}] + \frac{1}{V_i} \vec D^{(2)}(\vec W_i)
\end{array} 
$$
Für  die 4. Differenzen ist das Vorgehen analog. 
$$
\begin{array}{l}
	&\vec D^{(2)}(\vec W_i) &= &\triangleright(\epsilon^{(4)}\overline \lambda)\triangleleft \triangleright \triangleleft \vec W_i \\
	\Longrightarrow &\frac{d}{dt}\vec W_i &= &-\frac{1}{V_i}[\vec F_{i+\frac{1}{2}}^{s}-\vec F_{i+\frac{1}{2}}^{s}] + \frac{1}{V_i} [\vec D^{(2)}(\vec W_i)-\vec D^{(4)}(\vec W_i)]
\end{array}
$$
Welche Variable für die [[Sensorfunktion]] genutzt werden soll, hängt von ihrer Repräsentativität für die relevanten Störungen ab.