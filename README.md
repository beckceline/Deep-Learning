# Deep-Learning
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/beckceline/Deep-Learning/HEAD)

Wir werden einen Bank Authentifizierungs Datensatz aus dem USI Repository verwenden.

Der Datensatz beinhaltet 5 Spalten:

* variance of Wavelet Transformed image (continuous)
* skewness of Wavelet Transformed image (continuous)
* curtosis of Wavelet Transformed image (continuous)
* entropy of image (continuous)
* class (integer)
Hier gibt "class" an, ob eine Banknote authentifiziert wurde oder nicht.

### Daten einlesen
Zu Beginn des Projekts verwenden wir die Pandas-Bibliothek, um den Datensatz "bank_note_data.csv" zu laden und einen ersten Blick auf die Daten zu werfen.

### Explorative Datenanalyse (EDA)
In der EDA-Phase erstellen wir Visualisierungen, um ein besseres Verständnis der Daten zu erhalten. Wir verwenden Seaborn, um ein Countplot für die Klassen und ein Pairplot mit der "Class" als Farbvariable zu erstellen.

### Daten vorbereiten
Um unsere Daten für Deep Learning vorzubereiten, ist das Standardisieren der Features oft eine gute Praxis. Wir verwenden den StandardScaler aus Scikit-Learn, um die Features zu standardisieren. In diesem speziellen Fall haben wir festgestellt, dass dies nicht notwendig ist, daher gehen wir nur den Standardisierungsschritt durch, ohne die Daten tatsächlich zu verändern.

### Train-Test-Split
Wir teilen unsere Daten in Trainings- und Testsets auf, wobei die Features in X und die Labels in y aufgeteilt werden. Dies ist notwendig, um unser Modell zu trainieren und zu evaluieren.

### Deep Learning mit Tensorflow
Wir verwenden Tensorflow, um ein Deep Neural Network (DNN) zu erstellen. Dabei verwenden wir den DNNClassifier von Tensorflow Learn. Wir definieren die Struktur des Modells, einschließlich der Anzahl der versteckten Schichten und der Neuronen in jeder Schicht. Das Modell wird auf den Trainingsdaten trainiert.

### Vorhersage und Auswertung
In der Modellauswertung unseres Tensorflow-Projekts vergleichen wir die Leistung zweier unterschiedlicher Klassifikationsmodelle: eines Deep Neural Networks (DNN) und eines Random Forest Classifiers. Dies dient dazu, die Wirksamkeit von Deep Learning-Modellen im Vergleich zu traditionellen Machine Learning-Methoden zu untersuchen.

Beginnen wir mit dem DNN. Nachdem wir es auf den Trainingsdaten trainiert haben, verwenden wir es, um Vorhersagen für unser Testset (x_test) zu treffen. Um die Leistung des DNN-Modells zu bewerten, greifen wir auf die Confusion Matrix und den Classification Report zurück. Die Confusion Matrix zeigt die Anzahl der korrekten und inkorrekten Vorhersagen für jede Klasse an, während der Classification Report verschiedene Leistungskennzahlen wie Genauigkeit, Präzision, Recall und F1-Score für jede Klasse und insgesamt präsentiert. Aufgrund der mächtigen Modellkapazitäten eines DNNs können wir in der Regel eine hohe Genauigkeit und gute Leistungskennzahlen erwarten. Das DNN sollte in der Lage sein, authentifizierte und nicht authentifizierte Banknoten gut zu unterscheiden.

Im Gegensatz dazu verwenden wir den Random Forest Classifier als Referenzmodell. Wir trainieren diesen auf den Trainingsdaten und wenden ihn auf das Testset an. Auch hier evaluieren wir die Leistung mithilfe der Confusion Matrix und des Classification Reports. Obwohl Random Forests typischerweise gute Ergebnisse liefern, erwarten wir aufgrund ihrer begrenzten Modellkapazität, insbesondere im Vergleich zu DNNs, leicht niedrigere Genauigkeitswerte.

### Ergebnis
Schließlich vergleichen wir optional die Ergebnisse des DNNs und des Random Forest Classifiers. Wir erwarten, dass das DNN aufgrund seiner komplexen Architektur und seiner Fähigkeit, nichtlineare Beziehungen in den Daten zu erfassen, tendenziell bessere Ergebnisse liefert. Dies verdeutlicht die Leistungsfähigkeit von Deep Learning-Modellen bei der Bewältigung komplexer Klassifikationsaufgaben. Der Random Forest sollte jedoch auch gute Ergebnisse erzielen und könnte sich als robuste Alternative erweisen. Insgesamt ermöglicht dieser Vergleich eine Einschätzung, welches Modell besser für die spezifische Aufgabe geeignet ist.

Für das Deep Neural Network (DNN) kann man extrem genaue Vorhersagen erwarten, wie durch die Confusion Matrix und den Classification Report bestätigt:

Genauigkeit (Accuracy): 100%
Präzision (Precision): 100%
Recall: 100%
F1-Score: 100%
Für den Random Forest Classifier kann man ebenfalls gute Ergebnisse erwarten, wenn auch nicht ganz so präzise wie beim DNN:

Genauigkeit (Accuracy): 97.8%
Präzision (Precision): 97.3%
Recall: 97.2%
F1-Score: 97.2%
