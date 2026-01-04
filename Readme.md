# Retinal Vessel Segmentation Using Deep Learning

---

## Table of Contents

- [Overview](#overview)
- [Project Objective](#project-objective)
- [Dataset](#dataset)
- [Models Implemented](#models-implemented)
- [Evaluation Metrics](#evaluation-metrics)
- [Methodology](#methodology)
- [Results Summary](#results-summary)
- [Visual Results](#visual-results)
- [Technical Summary](#technical-summary)
- [Why This Project Matters](#why-this-project-matters)
- [How to Run the Project](#how-to-run-the-project)
- [Key Features](#key-features)
- [Future Improvements](#future-improvements)
- [Implementation Links](#implementation-links)
- [Author](#author)
- [License](#license)

---

## Overview

This project focuses on **retinal blood vessel segmentation** using deep learning models applied to fundus images. Retinal vessel extraction is an important step in the analysis of eye diseases such as **diabetic retinopathy**, where vascular abnormalities are key clinical indicators.

The project compares multiple deep learning segmentation architectures under a **single, standardized training and evaluation pipeline** to understand how different model designs perform on the same dataset.

---

## Project Objective

The main objectives of this project are to:

- Perform pixel-level segmentation of retinal blood vessels
- Compare multiple deep learning architectures fairly
- Evaluate performance using medically relevant segmentation metrics
- Analyze both quantitative results and visual outputs

---

## Dataset

This project uses the **DRIVE (Digital Retinal Images for Vessel Extraction)** dataset.

Dataset characteristics:
- Color fundus images
- Expert-annotated vessel masks
- Small, high-quality benchmark dataset

Dataset sources:
- https://www.kaggle.com/datasets/andrewmvd/drive-digital-retinal-images-for-vessel-extraction

Due to dataset size and structure, careful preprocessing and augmentation are applied to improve generalization.

### Dataset (Visual Example)

Below is an example of a retinal fundus image and its corresponding ground truth vessel mask.

<img width="2000" height="800" alt="dataset_sample" src="https://github.com/user-attachments/assets/69df8342-733d-4852-b047-84c2cc01b9bc" />


---

## Models Implemented

The following segmentation architectures were implemented and evaluated:

- U-Net  
- FCN–ResNet50  
- U-Net++  
- Attention U-Net  
- ResU-Net  
- SegNet  
- DeepLabV3–ResNet50  
- LR-ASPP (MobileNetV3)

These models represent a range of design choices, including skip connections, attention mechanisms, residual blocks, and lightweight backbones.

---

## Evaluation Metrics

Model performance was evaluated using:

- Pixel Accuracy  
- Dice Coefficient  
- Intersection over Union (IoU)  

These metrics are commonly used in medical image segmentation to assess overlap quality and boundary accuracy.

---

## Methodology

1. Image resizing and normalization  
2. Data augmentation using flips and rotations  
3. Binary segmentation using encoder–decoder networks  
4. Training with a unified loss function and optimizer  
5. Evaluation on a held-out test set  

All models were trained using the same preprocessing steps and evaluation protocol to ensure a fair comparison.

The figure below shows an example of image preprocessing and augmentation applied during training.

[Preprocessing Example] <img width="2000" height="800" alt="preprocessing_example" src="https://github.com/user-attachments/assets/1e469b73-8a69-409c-aa4c-6e51de51c784" />

---

## Results Summary

Among all evaluated models:

- **U-Net achieved the best overall performance**
- Dice coefficient: **0.846**
- Intersection over Union (IoU): **0.734**

U-Net produced clean and continuous vessel maps, capturing both major vessels and fine branches more consistently than other architectures.

---

## Visual Results

Example visual outputs generated during evaluation:

- Input fundus image
- Ground truth vessel mask
- Predicted vessel segmentation

Recommended images to include in this repository:
- `results/sample_prediction.png`
- `results/model_comparison.png`
- `results/segmentation_examples.png`

---

## Project Workflow (GIF)

High-level workflow of the project:

- Dataset loading and preprocessing  
- Model training  
- Segmentation output generation  
- Metric evaluation  


---

## Technical Summary

- **Task:** Binary pixel-wise segmentation  
- **Data Type:** Retinal fundus images  
- **Learning Type:** Supervised learning  
- **Models:** CNN-based encoder–decoder architectures  
- **Loss Function:** Binary Cross-Entropy  
- **Optimizer:** Adam  
- **Framework:** PyTorch  
- **Evaluation Focus:** Dice and IoU metrics  

This section highlights the technical design of the project in a concise format.

---

## Why This Project Matters

- Retinal vessel segmentation supports early screening of eye diseases  
- Demonstrates practical use of deep learning in healthcare  
- Highlights the importance of architecture choice in medical imaging  
- Shows reproducible and structured experimentation  

---

## How to Run the Project

1. Clone the repository:

       git clone https://github.com/DeviSharanyaPasala/Retinal-Vessel-Segmentation.git

2. Navigate to the project directory:

       cd Retinal-Vessel-Segmentation

3. Install dependencies:

       pip install -r requirements.txt

4. Run the notebook or script:

       jupyter notebook retinal_vessel_segmentation.ipynb

---

## Key Features

- Multiple segmentation models implemented
- Unified training and evaluation pipeline
- Strong baseline performance with U-Net
- Both quantitative and qualitative analysis
- Clear and reproducible workflow

---

## Future Improvements

- Train on additional datasets such as STARE or CHASEDB1  
- Explore transformer-based segmentation models  
- Add cross-dataset generalization experiments  
- Integrate vessel segmentation into a full DR screening pipeline  

---

## Implementation Links

- Google Colab Notebook:  
  https://colab.research.google.com/drive/1FcdhDwJ5wnePTTHAIxgbrIEDtqvkBoji

- Dataset Source:  
  https://www.kaggle.com/datasets/andrewmvd/drive-digital-retinal-images-for-vessel-extraction

---

## Author

**Devi Sharanya Pasala**  
Graduate student in Information Science with a focus on Data Analytics and Artificial Intelligence.

- GitHub: https://github.com/DeviSharanyaPasala  
- LinkedIn: https://www.linkedin.com/in/devi-sharanya/

---

## License

This project is intended for academic and learning purposes.
