# Human Activity Recognition (HAR) amb Deep Learning i Sensors Inercials 🚶‍♂️📱⌚

Aquest projecte aborda un repte crític en l'àmbit del reconeixement d'activitat humana (HAR) per a la monitorització de la salut: el **problema *cross-user***. L'objectiu és superar el clàssic *overfitting* biomètric i assegurar que el model sigui capaç de generalitzar correctament i predir l'activitat en usuaris completament nous.

## 🧠 Enfocament Tècnic i Metodologia
S'ha realitzat una anàlisi rigorosa comparant aproximacions clàssiques de Machine Learning amb arquitectures de Deep Learning, utilitzant un dataset públic (Zenodo) amb 23 participants de complexions físiques diverses.

* **Sensor Fusion (Early Fusion):** Integració de dades d'acceleròmetre i giroscopi procedents simultàniament d'un telèfon i un rellotge intel·ligent.
* **Avaluació de Models:** Random Forest (Baseline), Convolutional Neural Networks (CNN) i l'arquitectura híbrida **DeepConvLSTM**.
* **Validació Robusta:** Aplicació estricta del protocol *Leave-One-Subject-Out (LOSO)* per simular un entorn d'implementació real *Plug & Play*.



## 📊 Resultats Destacats
L'arquitectura **DeepConvLSTM** s'ha consolidat com el model més robust, superant clarament els models estàtics en escenaris *cross-user*:

* **80.82% d'Exactitud Global (Accuracy)** per a usuaris nous, superant el Random Forest (78.90%) i la CNN estàndard (75.75%).
* **Detecció de Transicions Complexes (Turning):** La combinació de la memòria temporal (LSTM) amb una estratègia de pesos manuals (*class-weighting*) ha corregit la "ceguesa" dels models clàssics, elevant el Recall de la classe Girar de 0.21 a 0.50.
* **Generalització Assolida:** El model aprèn patrons biomecànics universals en lloc de memoritzar la "signatura" de moviment de l'usuari.

## 🚀 Línies de Treball Futur
El projecte obre la porta a diverses aplicacions directes en l'assistència a la vida quotidiana:
1. **Temps Real:** Desplegament del model en una aplicació mòbil per avaluar latència i consum energètic.
2. **Amplicació Demogràfica:** Validació amb dades de persones majors de 70 anys per certificar la viabilitat en geriatria.
3. **Mecanismes d'Atenció (Transformers):** Exploració de noves arquitectures per ponderar la importància de cada sensor segons l'activitat.
4. **Generalització de Domini (Cross-Dataset):** Avaluar la resistència del model davant canvis de hardware aplicant-lo directament a altres datasets (WISDM, MotionSense).

## 📂 Estructura del Repositori
* `HAR_DeepLearning_Modeling.ipynb`: Notebook principal amb el processament de *Sensor Fusion*, bucle d'entrenament LOSO, estratègies de balanceig i avaluació.
* `Memoria_TFM_Gerard_Vidal.pdf`: Documentació tècnica, marc teòric, justificació metodològica i conclusions exhaustives.
* `Presentacio_Resultats.pdf`: Síntesi visual dels reptes, l'impacte de la recurrència en els resultats i les mètriques finals.

## 🛠️ Stack Tecnològic
`Python` | `Pandas` | `Scikit-Learn` | `Deep Learning (CNN/LSTM)` | `Sensor Fusion` | `Time Series Analysis`
