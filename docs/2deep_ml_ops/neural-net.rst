Neuronale Netze und Deep Learning – Theorie
----------------------------------------------------------

**Grundlagen:**

Was sind künstliche neuronale Netze? Wie unterscheiden sie sich von klassischen ML-Modellen?

- Künstliche neuronale Netze bestehen aus **Schichten von Neuronen**, die durch gewichtete Verbindungen miteinander verbunden sind.

- Aufbau eines neuronalen Netzes: **Eingabeschicht, versteckte Schichten, Aktivierungsfunktionen, Ausgangsschicht.**

- Jedes Neuron führt eine Berechnung basierend auf einer **Aktivierungsfunktion** durch und gibt das Ergebnis an die nächste Schicht weiter.

**Forwardpropagation (Vorwärtsdurchlauf):**

1. Die Eingabedaten werden in das Netzwerk eingespeist.

2. In jeder Schicht wird die gewichtete Summe der Eingänge berechnet:

   .. math::
      z = w_1 x_1 + w_2 x_2 + ... + w_n x_n + b

3. Diese gewichtete Summe wird durch eine **Aktivierungsfunktion** transformiert (z. B. ReLU, Sigmoid, Softmax), um **nicht-lineare Abhängigkeiten** abzubilden.

4. Die Ausgabe der einen Schicht wird als Eingabe an die nächste Schicht weitergegeben, bis die letzte Schicht erreicht ist.

5. Am Ende der Forward Propagation wird die Loss Function berechnet.


**Loss Functions (Verlustfunktionen) und ihre Rolle:**

- Eine **Loss Function** misst die Differenz zwischen der Vorhersage des Modells und dem tatsächlichen Wert.

- Sie gibt an, wie gut oder schlecht das Modell arbeitet.

- Wird während der Backpropagation genutzt, um die Gewichte des Netzwerks zu aktualisieren.

**Typische Loss Functions:**

1. **Mean Squared Error (MSE)** – Wird für **Regressionsprobleme** verwendet:

   .. math::
      MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2

   - Bestraft größere Fehler überproportional.

   - Gut für kontinuierliche Werte wie Preisprognosen.

2. **Cross-Entropy Loss** – Wird für **Klassifikationsprobleme** verwendet:

   .. math::
      L = -\sum y_i \log(\hat{y}_i)

   - Erhöht die Strafe, wenn das Modell sehr sicher, aber falsch ist.

   - Wird z. B. bei **Softmax-Klassifikationen** genutzt.

**Zusammenhang zwischen Loss Function und Gradient Descent:**

- Gradient Descent ist der Algorithmus, der die Gewichte des Modells so anpasst, dass die Loss Function minimiert wird.

- Die Ableitung der Loss Function bestimmt die Richtung, in die die Gewichte aktualisiert werden.

- **Formel für das Gewicht-Update:**

  .. math::
     w := w - \alpha \frac{\partial L}{\partial w}

  wobei \( \alpha \) die Lernrate ist.

- Dies passiert während der **Backwardpropagation (Rückwärtsdurchlauf):**

**Backwardpropagation (Rückwärtsdurchlauf):**

1. Der Fehler des Netzwerks wird berechnet, indem die Differenz zwischen der vorhergesagten und der tatsächlichen Ausgabe bestimmt wird, d.h. indem die Loss Function evaluiert wird.

2. Die Fehler werden von der letzten Schicht zurück durch das Netzwerk propagiert, um **die Gewichte der Neuronen zu aktualisieren**.

3. Die Berechnung erfolgt mit Hilfe der **Kettenregel der Ableitungen**, um die Gradienten für jedes Gewicht zu bestimmen:

..   .. math::
..      rac{\partial L}{\partial w} = rac{\partial L}{\partial y} \cdot rac{\partial y}{\partial z} \cdot rac{\partial z}{\partial w}

4. Durch die Anwendung des **Gradientenabstiegsverfahrens (Gradient Descent)** werden die Gewichte so angepasst, dass der Gesamtfehler des Netzwerks iterativ minimiert und somit das Modell optimiert wird.

**Optimierungstechniken:**

- **Stochastischer Gradientenabstieg (SGD):** Berechnet Gradienten basierend auf einer zufälligen Stichprobe aus den Trainingsdaten.

- **Adam-Optimizer:** Eine erweiterte Form des SGD, die adaptives Lernen ermöglicht und schneller konvergiert.

- **Momentum-Methoden:** Nutzen vergangene Gradienteninformationen, um stabilere Updates durchzuführen.

**Wichtige Aktivierungsfunktionen:**

- **ReLU (Rectified Linear Unit):** Häufig in CNNs verwendet, eliminiert negative Werte.

- **Sigmoid:** Wandelt Werte in einen Bereich zwischen 0 und 1 um, nützlich für Wahrscheinlichkeitsprognosen.

- **Softmax:** Wird in Klassifikationsproblemen für mehr als zwei Klassen genutzt.


**Fortgeschrittene Deep-Learning-Techniken:**

- Convolutional Neural Networks (CNNs) für **Bildverarbeitung**.

- Recurrent Neural Networks (RNNs) für **Sequenz- und Textverarbeitung**.

- Transformer-Modelle für **NLP (z. B. BERT, GPT).**
