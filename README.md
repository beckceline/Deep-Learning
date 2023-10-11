# Deep-Learning
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/beckceline/Deep-Learning/HEAD)

Wir werden einen Bank Authentifizierungs Datensatz aus dem USI Repository verwenden.

Der Datensatz beinhaltet 5 Spalten:

* variance of Wavelet Transformed image (continuous)
* skewness of Wavelet Transformed image (continuous)
* curtosis of Wavelet Transformed image (continuous)
* entropy of image (continuous)
* class (integer): hier gibt "class" an, ob eine Banknote authentifiziert wurde oder nicht.

### Schritte

1. Daten einlesen: Zu Beginn des Projekts verwenden wir die Pandas-Bibliothek, um den Datensatz "bank_note_data.csv" zu laden und einen ersten Blick auf die Daten zu werfen.

2. Explorative Datenanalyse: Wir erstellen Visualisierungen, um ein besseres Verständnis der Daten zu erhalten. Dazu verwenden wir Seaborn, um ein Countplot für die Klassen und ein Pairplot mit der "Class" als Farbvariable zu erstellen.

3. Daten vorbereiten: Um unsere Daten für Deep Learning vorzubereiten, ist das Standardisieren der Features oft eine gute Praxis. Wir verwenden den StandardScaler aus Scikit-Learn, um die Features zu standardisieren. In diesem speziellen Fall haben wir festgestellt, dass dies nicht notwendig ist, daher gehen wir nur den Standardisierungsschritt durch, ohne die Daten tatsächlich zu verändern.

4. Train-Test-Split: Wir teilen unsere Daten in Trainings- und Testsets auf, wobei die Features in X und die Labels in y aufgeteilt werden. Dies ist notwendig, um unser Modell zu trainieren und zu evaluieren.

5. Deep Learning mit Tensorflow: Wir verwenden Tensorflow, um ein Deep Neural Network (DNN) zu erstellen. Dabei verwenden wir den DNNClassifier von Tensorflow Learn. Wir definieren die Struktur des Modells, einschließlich der Anzahl der versteckten Schichten und der Neuronen in jeder Schicht. Das Modell wird auf den Trainingsdaten trainiert.

6. Vorhersage und Auswertung: In der Modellauswertung unseres Tensorflow-Projekts vergleichen wir die Leistung zweier unterschiedlicher Klassifikationsmodelle: eines Deep Neural Networks (DNN) und eines Random Forest Classifiers. Dies dient dazu, die Wirksamkeit von Deep Learning-Modellen im Vergleich zu traditionellen Machine Learning-Methoden zu untersuchen.

Nachdem wir das DNN auf den Trainingsdaten trainiert haben, verwenden wir es, um Vorhersagen für unser Testset (x_test) zu treffen. Um die Leistung des DNN-Modells zu bewerten, greifen wir auf die Confusion Matrix und den Classification Report zurück. Aufgrund der mächtigen Modellkapazitäten eines DNNs können wir in der Regel eine hohe Genauigkeit und gute Leistungskennzahlen erwarten. Das DNN sollte in der Lage sein, authentifizierte und nicht authentifizierte Banknoten gut zu unterscheiden.

Im Gegensatz dazu verwenden wir den Random Forest Classifier als Referenzmodell. Wir trainieren diesen auf den Trainingsdaten und wenden ihn auf das Testset an. Auch hier evaluieren wir die Leistung mithilfe der Confusion Matrix und des Classification Reports. Obwohl Random Forests typischerweise gute Ergebnisse liefern, erwarten wir aufgrund ihrer begrenzten Modellkapazität, insbesondere im Vergleich zu DNNs, leicht niedrigere Genauigkeitswerte.

### Ergebnis

Für das Deep Neural Network (DNN) kann man extrem genaue Vorhersagen erwarten, wie durch die Confusion Matrix und den Classification Report bestätigt:

| Genauigkeit (Accuracy) | Präzision (Precision) | Recall | F1-Score |
|----------|----------|
| 100% | 100% | 100% | 100% |

Für den Random Forest Classifier kann man ebenfalls gute Ergebnisse erwarten, wenn auch nicht ganz so präzise wie beim DNN:

| Genauigkeit (Accuracy) | Präzision (Precision) | Recall | F1-Score |
|----------|----------|
| 97.8% | 97.3% | 97.2% | 97.2% |

