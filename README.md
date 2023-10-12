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

5. Modellerstellung: Zu Beginn erstellen wir ein neuronales Netzwerk-Modell mit Keras. Das Modell ist sequenziell und besteht aus verschiedenen Schichten. Zuerst wird die Eingabeschicht definiert, die die korrekte Anzahl von Merkmalen aufweist. Anschließend folgen mehrere dichte Schichten, die jeweils mit einer ReLU-Aktivierungsfunktion ausgestattet sind. Die letzte Schicht hat zwei Ausgänge, was darauf hinweist, dass es sich um ein Klassifikationsproblem mit zwei Klassen handelt und eine Softmax-Aktivierung verwendet.

6. Kompilierung des Modells: Nach der Modellerstellung kompilieren wir usner Modell. Hierbei legen wir wichtige Einstellungen fest, darunter der Optimierungsalgorithmus (in diesem Fall 'adam'), die Verlustfunktion ('sparse_categorical_crossentropy') und die Metrik zur Überwachung der Genauigkeit des Modells ('accuracy'). Dieser Schritt legt die Grundlage für das Training.

7. Training des Modells: Unser Modell wird mit den Trainingsdaten für eine bestimmte Anzahl von Epochen (in diesem Fall 10) trainiert. Das Training erfolgt in Batches, wobei jeder Batch 32 Datenpunkte enthält. Während des Trainings werden die Verlustfunktion und die Genauigkeit für jede Epoche überwacht. Das Modell passt seine Gewichtungen an, um die Verlustfunktion zu minimieren und die Genauigkeit zu maximieren.


### Ergebnis

Das Modell wurde mit den Trainingsdaten trainiert, wobei insgesamt 10 Trainingsepochen durchgeführt wurden. Die Entwicklung von Loss und Accuracy über diese Epochen hinweg zeigt, wie effektiv das Modell trainiert wurde:

- Epoch 1/10: Loss: 0,6286, Accuracy: 78,02%
- Epoch 2/10: Loss: 0,5327, Accuracy: 90,21%
- Epoch 3/10: Loss: 0,4338, Accuracy: 91,56%
- Epoch 4/10: Loss: 0,3170, Accuracy: 94,90%
- Epoch 5/10: Loss: 0,2095, Accuracy: 96,35%
- Epoch 6/10: Loss: 0,1353, Accuracy: 97,40%
- Epoch 7/10: Loss: 0,0906, Accuracy: 98,12%
- Epoch 8/10: Loss: 0,0658, Accuracy: 98,33%
- Epoch 9/10: Loss: 0,0502, Accuracy: 98,33%
- Epoch 10/10: Loss: 0,0403, Accuracy: 99,17%

Nach dem Training wurde das Modell auf den Testdaten evaluiert, um seine Leistung auf nicht gesehenen Daten zu bewerten. Die Ergebnisse dieser Evaluation sind wie folgt:

- Loss auf Testdaten: 0,0320
- Genauigkeit auf Testdaten: 99,27%

Die Trainings- und Testergebnisse deuten darauf hin, dass das Modell sehr effektiv trainiert wurde. Der Loss auf den Testdaten liegt bei 0,0320, und die Genauigkeit beträgt beeindruckende 99,27%. Dies zeigt, dass das Modell die Trainingsdaten gut gelernt hat und auch auf unbekannte Testdaten sehr gut abschneidet.
