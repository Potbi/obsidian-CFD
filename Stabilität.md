Eigenschaft eines numerischen Verfahrens, die das Verhalten auf kleine Störungen beschreibt.

__instabil__: Anwachsen des Fehlers bei der Zeitintegration
__stabil__: Fehler bliebt begrenzt

#### vereinfachtes Stabilitätskriterium
Der Fehlerbetrag 
$$
|\epsilon|= |\text{exakte Lösung}\ -\ \text{approximierte Lösung}|
$$ 
Stabilität wird erreicht, wenn:
$$
max|\epsilon^{n+1}|\ \leq\ max|\epsilon^n|
$$
-->Der maximale Fehler des nächsten Zeitschritts muss mindestens so klein sein, wie der des aktuellen Zeitschritts.

