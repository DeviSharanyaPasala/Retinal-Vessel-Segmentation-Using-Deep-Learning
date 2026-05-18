# Retinal Vessel Segmentation

Comparing deep learning architectures for segmenting blood vessels in retinal fundus images. Accurate vessel maps are useful for early screening of conditions like diabetic retinopathy, where changes in vessel structure are key clinical indicators.

Eight architectures were trained and evaluated on the same DRIVE dataset with the same preprocessing pipeline and train/test splits to keep the comparison fair.

## Models

U-Net, U-Net++, Attention U-Net, ResU-Net, SegNet, FCN-ResNet50, DeepLabV3-ResNet50, LR-ASPP MobileNetV3

## Dataset

DRIVE (Digital Retinal Images for Vessel Extraction). 40 color fundus images with expert-annotated vessel masks. Standard benchmark for retinal segmentation.

Source: https://www.kaggle.com/datasets/andrewmvd/drive-digital-retinal-images-for-vessel-extraction

## Results

| Model | Dice | IoU | Accuracy |
|-------|------|-----|----------|
| U-Net | 0.8851 | 0.8108 | 0.8700 |
| SegNet | 0.8189 | 0.6933 | 0.6958 |
| U-Net++ | 0.8150 | 0.6877 | 0.6877 |
| FCN-ResNet50 | 0.3095 | 0.1833 | 0.3735 |
| DeepLabV3-ResNet50 | 0.2000 | 0.1115 | 0.3889 |
| LR-ASPP MobileNetV3 | 0.0411 | 0.0212 | 0.3245 |
| Attention U-Net | 0.0199 | 0.0101 | 0.3191 |
| ResU-Net | 0.0012 | 0.0006 | 0.3127 |

U-Net came out clearly on top with Dice 0.8851 and IoU 0.8108. SegNet and U-Net++ were reasonable second and third. The attention and residual variants underperformed here, likely due to the small dataset size and limited training epochs — these architectures tend to need more data and longer training to converge.

## How to run

```bash
pip install -r requirements.txt
jupyter notebook Retinal_Images_for_Vessel_Extraction.ipynb
```

## Stack

Python, PyTorch, OpenCV, NumPy, Matplotlib, Pandas
