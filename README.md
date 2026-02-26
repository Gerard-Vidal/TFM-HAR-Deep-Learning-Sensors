# Human Activity Recognition (HAR) using Deep Learning and Inertial Sensors 

This project addresses a critical challenge in Human Activity Recognition (HAR) for health monitoring: the **cross-user problem**. The goal is to overcome classic biometric overfitting and ensure the model can generalize correctly to predict the activity of completely unseen users.

##  Technical Approach & Methodology
A rigorous comparative analysis was conducted between classic Machine Learning approaches and Deep Learning architectures, using a public dataset (Zenodo) featuring 23 participants with diverse physical profiles.

* **Sensor Fusion (Early Fusion):** Integration of accelerometer and gyroscope data collected simultaneously from a smartphone and a smartwatch.
* **Model Evaluation:** Random Forest (Baseline), Convolutional Neural Networks (CNN), and the hybrid **DeepConvLSTM** architecture.
* **Robust Validation:** Strict application of the *Leave-One-Subject-Out (LOSO)* protocol to simulate a real-world *Plug & Play* deployment.

## Key Results
The **DeepConvLSTM** architecture proved to be the most robust model, clearly outperforming static models in *cross-user* scenarios:

* **80.82% Global Accuracy** for unseen users, outperforming Random Forest (78.90%) and standard CNN (75.75%).
* **Detection of Complex Transitions (Turning):** Combining temporal memory (LSTM) with a class-weighting strategy corrected the "blindness" of classic models, raising the Recall for the Turning class from 0.21 to 0.50.
* **Generalization Achieved:** The model learns universal biomechanical patterns instead of memorizing the user's unique movement "signature".

##  Future Work & Applications
This project paves the way for direct applications in daily life assistance and eldercare:
1. **Real-Time Deployment:** Porting the trained model to a mobile app to evaluate latency and energy consumption.
2. **Demographic Expansion:** Validating the model with data from individuals over 70 to certify its viability in geriatrics.
3. **Attention Mechanisms:** Exploring Transformer-based architectures to automatically weight the importance of each sensor depending on the activity.
4. **Domain Generalization:** Testing the model's robustness against hardware changes by applying it to other public datasets (WISDM, MotionSense).

##  Repository Structure
* `HAR_DeepLearning_Modeling.ipynb`: Main notebook containing Sensor Fusion processing, LOSO training loop, class balancing strategies, and evaluation.
* `Memoria_TFM_Gerard_Vidal.pdf`: Full technical documentation, theoretical framework, methodological justification, and exhaustive conclusions (Written in Catalan).
* `Presentacio_Resultats.pdf`: Visual synthesis of the challenges, the impact of recurrence on results, and final metrics (Written in Catalan).

##  Tech Stack
`Python` | `Pandas` | `Scikit-Learn` | `Deep Learning (CNN/LSTM)` | `Sensor Fusion` | `Time Series Analysis`
