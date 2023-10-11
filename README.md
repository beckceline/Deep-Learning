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

Das Ergebnis des Trainings und der Evaluierung des neuronalen Netzwerk-Modells mit den angegebenen Werten ist wie folgt:

- Trainings-Ergebnisse:

Nach 10 Trainingsepochen beträgt der Verlust (Loss) etwa 0.0390.
Die Genauigkeit (Accuracy) auf den Trainingsdaten beträgt etwa 99.27%.

- Test-Ergebnisse:

Bei der Evaluierung auf den Testdaten beträgt der Verlust (Loss) etwa 0.0361.
Die Genauigkeit (Accuracy) auf den Testdaten beträgt etwa 99.03%.

Diese Ergebnisse deuten darauf hin, dass das Modell sehr gut auf den Trainingsdaten gelernt hat und auch auf den Testdaten gute Leistungen erzielt, wobei die Genauigkeit bei etwa 99% liegt. Dies zeigt, dass das Modell in der Lage ist, die gegebenen Daten gut zu klassifizieren.
