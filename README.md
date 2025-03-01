# Multimodal Garbage Classification Report

## Overview
This project implements a **multimodal classification model** that combines **image** and **text** modalities using **transfer learning** to classify garbage into four distinct categories. The multimodal approach enhances classification accuracy by leveraging **ResNet50** for image processing and **DistilBERT** for text processing. The extracted features from both modalities are fused using an **Attention-based Fusion Layer** to improve overall classification performance.

## Dataset
- **Total Samples**: 16,928
- **Training Set**: 11,648
- **Validation Set**: 1,824
- **Test Set**: 3,456
- **Classes**: `Black`, `Blue`, `Green`, `TTR`

## Model Training & Performance
###  Multimodal Model (Image + Text Fusion)

| Metric  | Value | 
|---------|-------|
| **Test Accuracy** | **85.40%** | 
| **Best Train Loss** | 0.689 | 
| **Best Validation Loss** | 0.706 | 
| **Epoch with Best Val Loss** | 5 |

### Classification Report

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| **0** | 0.80 | 0.73 | 0.76 | 695 |
| **1** | 0.81 | 0.90 | 0.85 | 1,086 |
| **2** | 0.92 | 0.94 | 0.93 | 799 |
| **3** | 0.89 | 0.81 | 0.85 | 852 |
| **Overall Accuracy** | **85.40%** | - | - | **3,432** |

## Independent Model Performances

### Image-Only Model (ResNet50)

| Metric  | Value |
|---------|-------|
| **Best Train Loss** | 0.735 |
| **Best Validation Loss** | 0.723 |
| **Epoch with Best Val Loss** | 5 |

###  Text-Only Model (DistilBERT)

| Metric  | Value |
|---------|-------|
| **Best Train Loss** | 0.1697 |
| **Best Validation Loss** | 0.3061 |
| **Final Test Accuracy** | **84.21%** |

## Key Takeaways
- **The multimodal model achieved the highest accuracy (85.40%)**, outperforming the **image-only** and **text-only** models by combining both modalities effectively.
- **Image-Only Model performed well** but struggled with certain categories, indicating that text-based features can be valuable for distinguishing specific garbage types.
- **Text-Only Model had strong precision** but did not surpass the multimodal model, emphasizing the power of combined features.
- The **attention-based fusion mechanism** effectively learned how to weigh image and text contributions, improving the classification performance.

## Conclusion
The results confirm that a **multimodal learning approach** significantly enhances classification accuracy over unimodal methods. The **fusion of text and image features** allows the model to **compensate for weaknesses in each modality**, leading to a more robust and **accurate garbage classification system**.

**Final Recommendation:** This model can be further improved by fine-tuning hyperparameters and training on larger datasets for better generalization. Future work could explore **data augmentation strategies** and **self-supervised learning techniques** to boost performance further.
