# Cross-Model Deep Learning Frameworks for Improved Detection of Alzheimer’s Disease

**Rayan Beshawri, Mohammed Alyamani, Ahmed Alzahrani, Muhannad Alaqeel, Abdulaziz Dawood**  
**Under supervision of Dr. Hezam Al-Baqami**

## Abstract
The increasing prevalence of brain diseases, such as Alzheimer’s, necessitates more efficient diagnostic tools. Traditional brain imaging techniques, like Electroencephalogram (EEG) and Magnetic Resonance Imaging (MRI), require significant physician effort for accurate interpretation, often leading to diagnostic inconsistencies. This paper proposes a deep learning approach for improved brain disease diagnosis, utilizing a multi-modal strategy that combines 1D EEG time-series data and 2D scaleogram representations. We employed ChronoNet for 1D data and a fine-tuned ResNeSt26d model for 2D data, with an ensemble model to combine the outputs. Our results demonstrate that the ensemble approach significantly enhances classification accuracy, with the 1D model achieving an F1-score of 0.9496 and the 2D model showing complementary performance. This method offers promising potential for accelerating the diagnostic process and improving decision-making in clinical settings. Future work will focus on addressing demographic diversity, computational costs, and data complexity to optimize the model for broader applicability.

---

## Index Terms  
- Deep Learning  
- Alzheimer’s Disease  
- Multi-modal Learning  
- Convolutional Neural Networks  
- Time-series Analysis  
- Scaleograms  
- Ensemble Learning  

---

## I. Introduction  
Alzheimer’s Disease (AD) poses a significant global health challenge, contributing to over 15% of disability-adjusted life-years (DALYs) lost worldwide, surpassing cancer and cardiovascular diseases. Early and accurate diagnosis is critical but remains challenging due to the complexity and expertise required, often demanding years of specialized training for neurologists.  

This study addresses this gap by applying ensemble learning techniques to EEG data, aiming to develop a rapid and precise diagnostic system for AD. By focusing on EEG—a scalable and affordable modality—this work contributes to advancing accessible healthcare solutions for early Alzheimer’s detection, particularly in resource-limited settings.

---

## II. Problem Definition  
The diagnosis of Alzheimer’s disease remains a complex and time-intensive process, heavily reliant on the expertise of neurologists, often delaying intervention. Existing methods, such as MRI and PET imaging, though effective, are expensive, resource-intensive, and inaccessible in many regions. Conversely, EEG offers a cost-effective and non-invasive alternative but has seen limited research for Alzheimer’s diagnosis compared to imaging modalities.

This study addresses this critical gap by proposing a novel integration of advanced Artificial Intelligence (AI) and Machine Learning (ML) techniques with EEG data. The aim is to enhance diagnostic precision, reduce delays, and facilitate early intervention by leveraging the affordability and accessibility of EEG.

---

## III. Aims and Objectives  
The primary aims and objectives of this research are outlined as follows:  

1. **Enhance Diagnostic Efficiency**  
   - Goal: Develop and implement AI-based diagnostic models that reduce the average diagnostic time for Alzheimer’s disease from days to under 2 hours.  
   - Why: This will streamline the diagnostic process, allowing quicker identification and intervention, which is critical for early-stage treatment and improved patient outcomes.

2. **Improve Diagnostic Accuracy**  
   - Goal: Achieve a diagnostic accuracy rate of over 85% using EEG data, surpassing current diagnostic methods.  
   - Why: Accurate detection of subtle neurological changes will address the limitations of existing methods and facilitate early intervention.

3. **Optimize Cost-Effectiveness**  
   - Goal: Create a diagnostic solution that is more cost-effective than traditional imaging methods like MRI or PET.  
   - Why: Ensuring affordability will make advanced diagnostic tools accessible to resource-constrained healthcare settings, especially in low-income and rural areas.

4. **Leverage a Multi-Modality Approach**  
   - Goal: Integrate EEG data with other potential data sources, focusing on creating a robust and scalable diagnostic model.  
   - Why: A multi-modality approach will offer a comprehensive understanding of Alzheimer’s disease and improve detection sensitivity.

5. **Facilitate Decision-Making for Neurologists**  
   - Goal: Develop a decision-support system incorporating AI-based recommendations to assist neurologists in making faster and more accurate diagnostic decisions.  
   - Why: This will empower neurologists with actionable insights, improving diagnostic confidence and patient care.

---

## IV. Methods  
### A. Data Collection (Acquisition)  
1. **EEG Dataset**:  
   The EEG dataset was obtained from the OpenNeuroDatasets repository [28], consisting of 65 subjects: 36 diagnosed with Alzheimer’s Disease (AD) and 29 healthy controls. Recordings were collected under eyes-closed, resting-state conditions to minimize external interference. Each session lasted approximately 13 minutes.

### B. Data Preprocessing  
1. **EEG Data Preprocessing**:  
   EEG signals were preprocessed through a standardized pipeline to ensure high-quality input data for model training. The steps include:
   - Band-Pass Filtering: A Butterworth filter (0.5–45 Hz) was applied to remove low-frequency noise and high-frequency artifacts while retaining the brain activity spectrum relevant to the analysis.
   - Re-referencing: Signals were referenced using the average mastoid electrodes (A1-A2), standardizing recordings and reducing inter-subject variability.
   - Artifact Removal: Independent Component Analysis (ICA) was employed to eliminate artifacts caused by eye movements, muscle activity, and other physiological noise sources.
   - Segmentation: EEG signals were divided into fixed-length epochs for both 1D time-series and 2D scaleogram representations, balancing computational efficiency and feature resolution.
   - Continuous Wavelet Transform (CWT) for 2D Scaleogram Generation: For the 2D representation of EEG data, Continuous Wavelet Transform (CWT) was applied to convert the time-series signals into time-frequency scaleograms, providing detailed insights into the frequency content of the EEG signals across time.

### C. Model Selection and Training  
1. **ChronoNet for 1D EEG Data**:  
   ChronoNet, a deep learning architecture optimized for time-series analysis, was selected for 1D EEG signal classification. Its design includes:
   - Inception Modules: Sequential convolutional layers of varying kernel sizes extract multiscale temporal features from EEG signals.
   - GRU Layers: Gated Recurrent Units capture sequential dependencies and combine residual connections for efficient temporal context learning.
   - Dynamic Affine Layers: A fully connected layer dynamically initializes based on the input dimensions, enhancing adaptability.

2. **Scaleogram-Based Model for 2D EEG Data**:  
   A pre-trained ResNeSt26d model, fine-tuned for 2D scaleograms, was utilized. Scaleograms, generated using Continuous Wavelet Transform (CWT) with Morlet wavelets, provide a visual representation of frequency dynamics over time. Key components of the architecture include:
   - Pretrained Backbone: ResNeSt26d extracts hierarchical features from input scaleograms.
   - Channel Reduction: A convolutional layer reduces input dimensions to match the model’s requirements.
   - Custom Fully Connected Layers: Two fully connected layers refine the classification process, outputting probabilities for Alzheimer’s detection.

### D. Ensemble Learning  
The ensemble model combines the outputs of both the 1D and 2D models, integrating their complementary performance to enhance classification accuracy. This approach significantly improves the overall diagnostic performance, achieving an F1-score of 0.9496.

---

## VI. Results  
The ensemble approach demonstrated superior classification accuracy across both 1D and 2D data. Key metrics include:
- **1D Model**: F1-score of 0.9496  
- **2D Model**: Complementary performance enhancing diagnostic sensitivity.

Future work will focus on addressing demographic diversity, computational costs, and data complexity to optimize the model for broader applicability.

---

## References  
[1] - [28] (Include references cited within the document)
