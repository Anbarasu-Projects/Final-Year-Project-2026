# Final Year Project 2026

## Deep Learning Breast Cancer Detection Across Sites: A Cross-Dataset Evaluation of CNN Lesion Classifiers on CBIS-DDSM and MIAS

This repository contains the implementation developed for my Final Year Project.

The project investigates the performance and generalisation of deep learning models for breast cancer detection using mammography images. Models are developed and evaluated using the CBIS-DDSM dataset and then tested on the independent MIAS dataset to examine cross-dataset generalisation and domain shift.

The project also evaluates explainability using Grad-CAM and investigates several approaches for reducing performance degradation across datasets.

## Main Notebook

The complete implementation is contained in:
`FYP_mammography_cross_dataset_GitHub.ipynb`

The notebook includes:
- Dataset preparation and preprocessing
- Patient-level train, validation and test splitting
- Whole-image and region-of-interest (ROI) pipelines
- Transfer learning models
- Classical machine-learning baselines
- Hyperparameter experiments
- Threshold optimisation
- Statistical evaluation
- Grad-CAM explainability
- External evaluation using MIAS
- Domain-shift analysis
- Test-time adaptation experiments
- Domain-adversarial training experiments

## Datasets

### CBIS-DDSM

CBIS-DDSM is used for model development, validation and internal testing.

The project uses mammography images together with pathology labels, lesion information and BI-RADS assessments.

### MIAS

The Mammographic Image Analysis Society (MIAS) dataset is used as an independent external dataset for evaluating cross-dataset generalisation.

MIAS is not used for model selection or hyperparameter tuning.

## Technologies
The project was implemented using:
- Python
- TensorFlow / Keras
- scikit-learn
- OpenCV
- scikit-image
- SciPy
- pandas
- NumPy
- Matplotlib
- Google Colab
Training and experiments were performed using a GPU-enabled Google Colab environment.

## Model Development
The project compares several modelling approaches, including:
- Convolutional neural network baseline
- Transfer learning
- ResNet50
- EfficientNetB0
- DenseNet121
- HOG-based classical machine-learning baseline
- Pixel-based baseline

Training follows a two-stage transfer-learning process consisting of:

1. Training the classification head while keeping the pretrained backbone frozen.
2. Fine-tuning selected backbone layers using a lower learning rate.

## Evaluation
The evaluation includes:
- ROC-AUC
- PR-AUC
- Sensitivity
- Specificity
- Accuracy
- Bootstrap confidence intervals
- Permutation testing
- McNemar testing
- Split-to-split robustness analysis
The selected model is also evaluated on MIAS to measure the performance change when moving from one dataset to another.

## Explainability
Grad-CAM is used to inspect the regions influencing model predictions.
The project also evaluates whether the coordinate systems of the available lesion annotations and generated Grad-CAM heatmaps are suitable for quantitative localisation analysis.

## Cross-Dataset Evaluation
The project investigates domain shift between CBIS-DDSM and MIAS at several levels, including:
- Pixel-intensity distributions
- Deep feature representations
- Prediction distributions
Several adaptation approaches are investigated, including:
- Histogram matching
- CLAHE
- Per-image standardisation
- Domain-adversarial training

## Running the Project
The easiest way to run the project is using Google Colab.
1. Download `FYP_mammography_cross_dataset_GitHub.ipynb`.
2. Upload the notebook to Google Colab.
3. Configure access to the required datasets.
4. Run the notebook cells in order.

Some experiments require a GPU runtime.

## Dataset links
- https://www.kaggle.com/datasets/awsaf49/cbis-ddsm-breast-cancer-image-dataset
- https://www.kaggle.com/datasets/kmader/mias-mammography
