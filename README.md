
# ECG Noise Artifact Classification Using DWT and Machine Learning

## Overview

This project focuses on classifying noise artifacts in electrocardiogram (ECG) signals using machine learning. It compares **Discrete Wavelet Transform (DWT)-based features** with conventional statistical features and evaluates three machine learning classifiers: Decision Tree, Random Forest, and Support Vector Machine (SVM).

The project also includes external validation experiments to investigate how well the trained models perform on unseen ECG data.

## Objectives

- Classify ECG segments into four categories: Clean ECG, Baseline Wander, EMG Artifact, and Motion Artifact.
- Extract and compare DWT-based and conventional statistical features.
- Evaluate Decision Tree, Random Forest, and SVM classifiers.
- Compare classification performance using accuracy, precision, recall, F1-score, and confusion matrices.
- Assess model generalization through external validation on unseen ECG data.

## Repository Contents

| Notebook | Description |
|---|---|
| `ECG_Noise_Classification_DWT_Project_1.ipynb` | Main ECG noise classification pipeline using DWT-based feature extraction and machine learning classifiers. |
| `ECG_Noise_Classification_DWT_Project_2.ipynb` | Main ECG noise classification pipeline using conventional statistical features for comparison with the DWT approach. |
| `ECG_External_Validation_1.ipynb` | External validation of DWT-based classification models on unseen ECG data. |
| `ECG_External_Validation_2.ipynb` | External validation of conventional-feature classification models on unseen ECG data. |

## Methodology

### 1. ECG Signal Preparation

ECG signals and noise recordings are used to prepare signal segments for classification. The experiments consider clean ECG signals and three types of noise artifacts.

### 2. Noise Addition

Noise is added to ECG signals at a target signal-to-noise ratio (SNR) of 6 dB in the described experimental setup.

### 3. Signal Segmentation

The experimental workflow uses 5-second ECG segments sampled at 360 Hz.

### 4. Feature Extraction

Two feature-extraction approaches are compared:

- **DWT-based features:** Discrete Wavelet Transform is used to extract wavelet-based characteristics from ECG signals.
- **Conventional statistical features:** Statistical characteristics of ECG segments are extracted to provide a baseline for comparison.

### 5. Machine Learning Classification

The following classifiers are evaluated:

- Decision Tree
- Random Forest
- Support Vector Machine (SVM) with an RBF kernel

### 6. Model Evaluation

Model performance is evaluated using classification metrics, including accuracy, precision, recall, F1-score, and confusion matrices.

### 7. External Validation

The external validation notebooks assess the trained models on separate ECG data that was not used in the main training and testing experiments. This helps examine model generalization to unseen recordings.

## Experimental Results

### Main Test-Set Performance

The recorded main experiment results show that DWT-based features outperform conventional statistical features for all three evaluated classifiers.

| Classifier | DWT Features | Conventional Features |
|---|---:|---:|
| Decision Tree | 70.21% | 44.52% |
| Random Forest | **77.74%** | 51.71% |
| SVM (RBF) | 72.60% | 55.82% |

The best recorded result was achieved by the Random Forest classifier using DWT-based features, with **77.74% accuracy** and a weighted F1-score of **77.69%**.

### External Validation Performance

The recorded external validation results are:

| Classifier | DWT Features | Conventional Features |
|---|---:|---:|
| Decision Tree | 45.22% | 35.11% |
| Random Forest | **55.75%** | 39.13% |
| SVM (RBF) | 40.17% | 31.86% |

External validation performance is lower than the main test-set performance. This indicates that classifying noise artifacts in unseen ECG recordings remains challenging and that further work is needed to improve generalization.

*Note: Verify these metrics against the final outputs of the uploaded notebooks before using them in a formal report or publication.*

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- WFDB
- PyWavelets
- SciPy
- Scikit-learn
- Joblib
- Jupyter Notebook
- Google Colab

## Datasets

The project uses publicly available ECG resources:

- [MIT-BIH Arrhythmia Database](https://physionet.org/content/mitdb/)
- [MIT-BIH Noise Stress Test Database](https://physionet.org/content/nstdb/)

Please refer to the notebooks for the specific ECG records, noise preparation procedures, and experimental implementation.

## How to Run

1. Open the required notebook in [Google Colab](https://colab.research.google.com/) or Jupyter Notebook.
2. Install any missing Python dependencies.
3. Obtain the required ECG data files from the relevant data sources.
4. Upload the data or configure the appropriate file paths.
5. If running outside Google Colab, update any Google Drive or Colab-specific code.
6. Run the notebook cells in order.
7. Review the classification metrics, model comparisons, and confusion matrices.

## Limitations

- Performance may vary across ECG recordings, noise types, and signal conditions.
- External validation scores are lower than the main test-set scores in the recorded experiments.
- Results depend on data preparation, feature extraction, noise level, and evaluation methodology.
- The current experiments do not establish clinical readiness or suitability for real-time clinical use.

## Future Scope

- Validate the models on additional ECG records and independent datasets.
- Investigate more robust signal preprocessing and feature-selection methods.
- Explore deep learning approaches for ECG noise artifact classification.
- Improve generalization across patients, recording devices, and acquisition conditions.
- Evaluate performance across different signal-to-noise ratios and noise conditions.
- Investigate deployment for research-oriented ECG signal quality assessment.

## Disclaimer

This project is intended for educational and research purposes only. It is not a medical device and must not be used as a substitute for professional medical assessment or diagnosis.

## Author

**Lakshita Jain**

- [GitHub](https://github.com/lakshitajain46)
- [LinkedIn](https://www.linkedin.com/in/lakshita-jain-143076368/)
