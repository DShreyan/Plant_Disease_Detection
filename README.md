# Plant Leaf Disease Detection Using Preprocessed Data

## Abstract
The goal of this project is to identify plant diseases using preprocessed image data. Preprocessing steps include:
- Noise removal using the 'Vishushrink' wavelet approach.
- Image resizing to 256x256.
- Contrast enhancement using Contrast Limited Adaptive Histogram Equalization (CLAHE) in HSV color space.
- Background noise removal using U2-Net segmentation.

To address dataset imbalance, image augmentation techniques were employed. Ten distinct plant disease classes were considered, and features such as energy, correlation, and entropy were extracted. Several deep learning models were tested, with ResNet18 (with self-attention layers) achieving the best performance (accuracy: 99%).

## Index Terms
Wavelet ('Vishu shrink'), CLAHE, ResNet, VGG16, Self-attention layers.

---

## Introduction
Plant diseases significantly impact crop productivity, food security, and the economy. Traditional methods like visual inspection are time-consuming and prone to error, causing treatment delays and increasing the risk of disease spread. By leveraging machine learning and image processing, this project aims to provide early and accurate detection of plant diseases, enabling preventive measures and sustainable agricultural practices.

## Motivation
The project aims to reduce crop losses, encourage sustainable farming, and provide an accessible tool for monitoring crop health. Early disease detection can prevent the excessive use of pesticides and fertilizers, promoting organic farming and increasing crop yield.

## Objectives
- Develop a system for early and accurate detection of plant diseases using computer vision and deep learning.
- Enhance agricultural practices by reducing chemical interventions and improving crop yield.
- Create a user-friendly interface for farmers to upload plant images and receive diagnoses.

---

## Dataset Description
The dataset is sourced from Kaggle's Plant Village dataset, comprising:
- **Original Size**: 38 classes and 87,900 images (512x512 pixels).
- **Subset Used**: 10 classes with a total of 24,000 images.
  - Apple_healthy, Blueberry_healthy, Cherry_healthy (including sour), Apple_scab, Apple_black_rot, Apple_cedar_rust, Cherry_powder, Maize_cercospora_leaf_spot, Maize_common_rust, Maize_healthy.

The dataset was split into training, validation, and test sets. Balancing was achieved using image augmentation.

---

## Preprocessing Techniques
### Image Enhancement
1. **Noise Reduction**: 
   - Wavelet denoising using the 'bior6.8' wavelet.
   - Biorthogonal wavelets provide good localization in time and frequency domains.
2. **Color Conversion**:
   - RGB images converted to HSV format.
   - Contrast enhancement with CLAHE.
3. **Background Removal**:
   - U2-Net segmentation for accurate object isolation.

### Dataset Balancing
- Image augmentation was used to address dataset imbalance, generating a uniform distribution across classes.

---

## Models and Classifiers
### Deep Learning Architectures
1. **MobileNetV3 Small**: 
   - Achieved 85% accuracy.
2. **ResNet18 with Self-attention Layers**:
   - Modified architecture with self-attention layers.
   - Achieved 99% accuracy.
3. **VGG16 and Vision Transformers**: Tested as alternative models.

### Feature-Based Classification
Using GLCM (Gray-Level Co-occurrence Matrix), features such as contrast, energy, dissimilarity, homogeneity, and entropy were extracted and classified with:
- **SVC** (Radial Basis Kernel): 61.6% accuracy.
- **Random Forest**: 55.5% accuracy.
- **AdaBoost**: 55.7% accuracy.

---

## Evaluation Metrics
Accuracy was calculated using True Positives (TP), True Negatives (TN), False Positives (FP), and False Negatives (FN). The formula:

\[ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} \]

### Results
- **ResNet18 with Self-attention**: Best-performing model with 99% accuracy.
- **MobileNetV3 Small**: Achieved 85% accuracy.
- Feature-based SVC: 61.6% accuracy.

---

## Conclusion
This study demonstrates that preprocessing techniques significantly enhance model performance. Among tested architectures, ResNet18 with self-attention layers provided the best accuracy. The project highlights the importance of early plant disease detection to support sustainable agricultural practices and improve crop yield.

---

## Future Work
- Extend the system to support real-time disease detection.
- Optimize computational efficiency for deployment on mobile devices.
- Expand the dataset to include more plant species and diseases.

