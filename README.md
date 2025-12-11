# Combined Swin_UNETR, contrastive learning and classification models for inflitration segmentation in UPennGBM database

## Objective: 
To develop and validate a deep learning model capable of segmenting the tumor core with high precision and, fundamentally, predicting areas of tumor infiltration in peritumoral edema using only preoperative multimodal MRI images, in order to generate a recurrence probability map that can guide treatment from its initial phase.

## Methodology: 
A novel strategy was designed based on the combination of two processing pipelines, both built on a SwinUNETR architecture, a projection head for contrastive learning, and a supervised classifier. The first pipeline was trained with 361 cases from the UPenn-GBM database for robust segmentation of the tumor core and overall edema. The second pipeline was fine-tuned using 30 cases with specific infiltrative and vasogenic edema labels, derived from the location of postoperative recurrences, to specialize in the distinction of these critical subclasses. The probability maps from both pipelines were merged to generate a final segmentation that integrates the tumor core, infiltrative edema, and vasogenic edema. The performance of the combined model was evaluated in six test cases using voxel-wise and cube-wise metrics, including the Dice coefficient, sensitivity, precision, and AUC-ROC.

## How to use

- Clone repository
- Download models
- Install requirements
- Use *combined_models.ipynb* to reproduce the results
- Copy in tne root directory a Dataset folder with the following structure:

Dataset/test_6

    ├───recurrence
    │   └───images
    │       ├───UPENN-GBM-00036_21
    │       ├───UPENN-GBM-00042_11
    │       ├───UPENN-GBM-00045_21
    │       └───UPENN-GBM-00051_21
    └───test
        ├───images
        │   ├───images_DSC
        │   │   ├───UPENN-GBM-00036_11
        │   │   ├───UPENN-GBM-00042_11
        │   │   ├───UPENN-GBM-00045_11
        │   │   └───UPENN-GBM-00051_11
        │   ├───images_DTI
        │   │   ├───UPENN-GBM-00036_11
        │   │   ├───UPENN-GBM-00042_11
        │   │   ├───UPENN-GBM-00045_11
        │   │   └───UPENN-GBM-00051_11
        │   └───images_structural
        │       ├───UPENN-GBM-00036_11
        │       ├───UPENN-GBM-00042_11
        │       ├───UPENN-GBM-00045_11
        │       └───UPENN-GBM-00051_11
        └───labels
