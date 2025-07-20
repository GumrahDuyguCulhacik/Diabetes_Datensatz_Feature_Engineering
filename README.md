# Diabetes-Datensatz: Vorhersage mit Machine Learning
  # Projektziel
Ziel dieses Projekts ist die Entwicklung eines Machine-Learning-Modells zur Vorhersage von Diabetes basierend auf medizinischen Merkmalen. 
Vor der Modellierung wurden umfassende Schritte der explorativen Datenanalyse (EDA) und Merkmalsgenerierung (Feature Engineering) durchgeführt.
  # Datensatzinformationen
Quelle: National Institute of Diabetes and Digestive and Kidney Diseases (NIDDK), USA
Population: Frauen mit Pima-indigenem Hintergrund, 21 Jahre und älter, wohnhaft in Phoenix, Arizona
Größe: 768 Beobachtungen, 8 numerische erklärende Variablen
Zielvariable: Outcome
1: Positives Diabetes-Testergebnis
0: Negatives Diabetes-Testergebnis
 
  # Datenvorbereitung & Feature Engineering
1. Explorative Datenanalyse (EDA)
Untersuchung beschreibender Statistiken aller numerischen Variablen
Identifikation von fehlenden Werten
2. Umgang mit fehlenden Werten
Erkennung und Ersatz der fehlenden Werte anhand der Zielvariable Outcome
KNN-Imputation angewandt auf BloodPressure, Insulin und SkinThickness
3. Ausreißererkennung
Kombination aus LOF (Local Outlier Factor) und IQR-Methode
Schwellenwerte festgelegt
Ausreißer gemäß IQR mittels Winsorizing behandelt
4. Diskretisierung & Codierung
Numerische Merkmale gemäß WHO-Klassifikation in Kategorien gruppiert (Binning)
Anwendung von One-Hot-Encoding für kategorische Features
5. Erste Modellierung
Erste Modelltraining auf vorbereiteten Daten
6. Erweiterte Merkmalsgenerierung
Neue Features mittels Feature Creation produziert
Bewertung der Merkmale hinsichtlich ihrer Bedeutung für die Vorhersageleistung
7. Merkmalsreduktion
Selektive Feature-Beseitigung basierend auf Einfluss auf die Zielvariable Outcome
8. Finale Modellierung
Klassifikation mittels Random Forest Classifier
Berücksichtigung des unausgeglichenen Zielmerkmals
Modellgenauigkeit (Accuracy Score) erreicht: 78%

# Gesamtgenauigkeit (Accuracy): 78 %
Die allgemeine Modellgenauigkeit ist solide. 
Dennoch ist Vorsicht geboten, da die Zielvariable Outcome unausgewogen verteilt ist (mehr negative als positive Fälle).
  # Analytischer Kommentar
Für Klasse 0 (Nicht-Diabetiker) zeigt das Modell eine starke Leistung: sowohl Precision als auch Recall liegen über 80 %.
Die Klasse 1 (Diabetiker) wird dagegen weniger zuverlässig erkannt. 
Die Recall-Rate von 65 % bedeutet, dass ein Teil der tatsächlichen Diabetes-Fälle übersehen wurde.
Ein F1-Score von 0.68 zeigt, dass die Balance zwischen korrekten Vorhersagen und erkannter Wahrheit bei positiven Fällen verbessert werden könnte.
Das gewichtete Mittel aller Metriken liegt bei 0.78 und spiegelt die Gesamtleistung wider, ist jedoch durch die Klassenverteilung beeinflusst.

# Fazit
Ein AUC- Wert von 0.824 unterstreicht, dass das Modell nicht nur hohe Accuracy besitzt, sondern auch die Fähigkeit hat, gut zwichen gesunden und diabetischen
Fällen zu unterschieden, selbst bei einer unbalancierten Datwnsatzstruktur.
