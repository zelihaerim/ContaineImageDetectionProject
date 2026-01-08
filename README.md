# Automated Detection of Flaws on Ship Containers Using Digital Image Processing

This repository contains the complete implementation of the project **“Automated Detection of Flaws on Ship Containers Using Digital Image Processing Techniques”**, developed as part of the **CSE 464/564 – Digital Image Processing** course.

The project focuses on detecting surface and structural defects on ship containers using **classical digital image processing methods combined with machine learning**, emphasizing interpretability and robustness rather than black-box deep learning models.

---

## Project Overview

Ship containers are exposed to harsh environmental and mechanical conditions, which may cause defects such as corrosion, cracks, dents, holes, paint peeling, and scratches. Traditional inspection procedures rely on manual visual checks, which are time-consuming, subjective, and error-prone.

This project proposes an **automated inspection framework** that:
- Suppresses periodic container rib structures using **frequency-domain analysis**
- Enhances defect-related features using **spatial-domain edge detection**
- Extracts **robust statistical and geometric features**
- Classifies containers as **damaged** or **not damaged** using machine learning models

---

## Methodology Summary

The proposed pipeline consists of the following stages:

1. **Preprocessing**
   - Image resizing and grayscale conversion
   - Noise suppression using Gaussian and median filtering
   - Intensity normalization

2. **Spatial Domain Processing**
   - Sobel, Prewitt, Laplacian, and Canny edge detection

3. **Frequency Domain Processing**
   - Fast Fourier Transform (FFT)
   - Sinusoidal / notch-like frequency suppression
   - Local FFT analysis to handle perspective variations

4. **Feature Extraction**
   - Statistical features: mean, standard deviation, 95th percentile, maximum
   - Morphological and geometric features from binary defect masks

5. **Classification**
   - Multilayer Perceptron (MLP)
   - Random Forest (for feature importance and selection)

6. **Evaluation**
   - Validation-based model selection
   - Stratified 10-fold cross-validation
   - Accuracy and ROC-AUC metrics

---

## Experimental Results

- **Mean cross-validation accuracy:** ~96% (± <1%)
- **Mean ROC-AUC:** > 0.95
- **Validation accuracy:** > 94%
- **Test accuracy:** > 94%

The results demonstrate strong generalization and robustness of the proposed feature set across different data splits.

---

## Repository Structure

```text
.
├── image-processing-notebook-v3.ipynb   # Main Jupyter Notebook (full pipeline)
├── README.md                           # Project documentation (this file)
