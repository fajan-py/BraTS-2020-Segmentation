# Brain MRI Segmentation using Attention UNet
## This is a GIF. Click on it!(In case it is not played for you)
![](https://github.com/fajan-py/BraTS-2020-Segmentation/blob/main/segmentation_pred_final.gif)


## Overview

This project focuses on **brain tumor segmentation** using multi-modal MRI scans from the **BraTS 2020 dataset**. It employs an **Attention UNet** model for enhanced region-specific focus, combined with **TorchIO** for advanced preprocessing and realistic augmentation. The complete pipeline covers data loading, preprocessing, model training, evaluation, and visualization.

## Dataset

- **Source**: [BraTS 2020 Challenge](https://www.med.upenn.edu/cbica/brats2020/)
- **Modalities**:
  - FLAIR
  - T1
  - T1ce (contrast-enhanced)
  - T2
- **Segmentation Classes**:
  - Background
  - GD-enhancing tumor (ET)
  - Peritumoral edema (ED)
  - Necrotic and non-enhancing tumor core (NCR/NET)

## Model Architecture

- **Training details**:
  - Model: `3D Attention UNet` 
  - Loss Function: `Dice Loss`
  - Optimizer: `Adam`
  - Performance Metrics: `Dice Score`

## Implementation Details

- **Libraries Used**:
  - `PyTorch`
  - `TorchIO`
  - `MONAI`
  - `Plotly`, `Matplotlib`
- **Training Process**:
  - Multi-modal MRI loading with TorchIO subjects
  - Extensive preprocessing (e.g., resampling, normalization)
  - Data augmentation with realistic artifacts (e.g., ghosting, motion)
  - Training with a custom loop and learning rate scheduling
  - Evaluation with Dice Loss and Dice Score metrics

## Accomplishments

- **Multi-modal MRI Integration**: Combined four MRI modalities into a single input tensor, enhancing feature learning.
- **Advanced Augmentation**: Simulated real-world MRI artifacts for better generalization.
- **Attention UNet Deployment**: Improved segmentation accuracy by dynamically attending to relevant regions.
- **Training Efficiency**: Achieved **training Dice Loss of 0.3** after 28 epochs through rigorous hyperparameter tuning.
- **Rich Visualization**: Built interactive 3D visualizations and 2D slice comparisons for better insight.

## Limitations

- **Imbalanced Classes**: Uneven distribution of classes, affecting class-wise Dice scores.
- **Resource Constraints**: Limited computational resources restricted training to 28 epochs, potentially preventing further loss reduction.
Also, due to limited resources, downsampling the brain MRIs and the resulting data loss were inevitable, which affected the final model's performance.


## How to Use

1. Install dependencies:
   ```bash
   pip install torch torchvision torchio monai plotly matplotlib torchmetrics
   ```
2. Clone the repository and load the BraTS 2020 dataset.
3. Run the notebook step-by-step for training and evaluation.
4. Visualize results in both 2D and 3D.
   
**Quick tip**: This code is written for use in a Kaggle notebook. To ensure better performance and avoid issues related to file paths and preprocessing, I recommend running this code on Kaggle.

## Medical & Radiological Relevance

- **Tumor Localization**: Helps radiologists identify precise tumor regions.
- **Treatment Planning**: Supports surgery/radiotherapy decisions by delineating tumor boundaries.
- **Deep Learning in Radiology**: Showcases the power of deep learning for medical image analysis.

## Results & Illustrations
![](https://github.com/fajan-py/BraTS-2020-Segmentation/blob/main/Screen%20Shot%201403-12-02%20at%2001.44.56.png)
![](https://github.com/fajan-py/BraTS-2020-Segmentation/blob/main/Screen%20Shot%201403-12-02%20at%2001.45.png)
![](https://github.com/fajan-py/BraTS-2020-Segmentation/blob/main/Screen%20Shot%201403-12-06%20at%2019.14.36.png)

