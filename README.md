# SYN-LUNGS: Towards Simulating Lung Nodules with Anatomy-Informed Digital Twins for AI Training [![arXiv](https://img.shields.io/badge/arXiv-2502.21187-<color>.svg)](https://arxiv.org/abs/2502.21187)

**Abstract:** AI models for lung cancer screening struggle with data scarcity, limiting generalizability and clinical applicability. Generative models for image synthesis are constrained by training data variability. We introduce SYN-LUNGS, a framework for generating high-quality 3D CT images with detailed annotations. SYN-LUNGS integrates XCAT3 phantoms for digital twin generation, X-Lesions for nodule simulation (varying size, location, appearance), and DukeSim for CT image formation with vendor and parameter variability. The dataset includes **3,072** nodule images from **1,044** simulated CT scans, **512** lesions, and **174** digital twins. Effectiveness was shown for nodule detection, segmentation, cancer classification, and synthesis. Models trained on clinical + simulated data outperform clinical-only models, with **10%** improvement in detection, **2–9%** in segmentation, **2–9%** in classification and enhanced synthesis. By integrating anatomy-informed simulations, this work facilitates future AI model development such as for rare disease representation and model reliability.

**Citation**
```ruby
@article{tushar2025synlungs,
  title={SYN-LUNGS: Towards Simulating Lung Nodules with Anatomy-Informed Digital Twins for AI Training},
  author={Tushar, Fakrul Islam and others},
  journal={arXiv preprint arXiv:2502.21187},
  year={2025}
}
```
## Features
**Digital Human Twins:** Generated from XCAT3 phantoms, embedding anatomical, pathological, and demographic variations.
**Simulated Lung Nodules:** Controlled lesion characteristics in terms of size, shape, and texture using X-Lesions.
**Physics-Based CT Simulation:** Modeled using DukeSim for scanner-specific imaging variations.
**AI Model Training Enhancement:** Validated on multiple AI tasks including nodule detection, segmentation, classification, and synthesis.
**Statistical Labeling:** Malignancy assignment based on a logistic regression model trained on NLST dataset.


# Simulated and Clinical Dataset
## The SYN-LUNGS dataset consists of:
* 1,044 CT scans from 174 digital twins
* 512 simulated lung nodules with segmentation masks
* 3,072 nodule images across different scanners

**The dataset can be accessed at:** [CVIT Duke Resources](https://cvit.duke.edu/resources/)

## Clinical Dataset
* Duke Lung Cancer Screening Dataset : https://zenodo.org/records/13799069
* LUNA16: https://luna16.grand-challenge.org/
* MSD Task06: http://medicaldecathlon.com/


## Installation

Prerequisites. Ensure the following dependencies are installed:

* Python >= 3.8
* PyTorch >= 1.10
* MONAI
* SimpleITK
* NumPy
* SciPy
* Matplotlib
* scikit-learn
* nibabel




Coming soon!!!
1) Training scripts
2) Inference Scripts
3) Evaluation Scripts
4) Clinical and Simulated Datasets


## Task: Detection

The lung cancer (Nodule) detection task is defined as identifying lung nodules within 3D CT scans and localizing them using 3D bounding boxes. To achieve this, we utilized the [MONAI](https://github.com/Project-MONAI/tutorials/tree/main/detection) detection workflow to train and validate 3D detection models based on RetinaNet, enabling straightforward implementation of our benchmark models.The model trained utilizing the official LUNA16 10-fold cross-validation from the [MONAI tutorial documentation](https://github.com/Project-MONAI/tutorials/tree/main/detection).
#### Pre-Processing
All CT volumes were resampled to a standardized resolution of **0.7 × 0.7 × 1.25 mm (x, y, z)**. The intensity values of the images were clipped between **-1000 and 500 HU**, and each volume was normalized to have a mean of 0 and a standard deviation of 1. The models were trained using 3D patches of size **192 × 192 × 80 (x, y, z)** and a sliding window approach was applied during the prediction phase to cover the entire volume. All models were trained with identical hyperparameters for 300 epochs, and the optimal model was selected based on the lowest validation loss.
#### Evaluation Metrics
The performance of the models was evaluated using the Free-Response Receiver Operating Characteristic (FROC) analysis, which measures sensitivity at various false positive rates (FPRs). The primary performance metric was the average sensitivity at predefined FPRs: **1/8, 1/4, 1/2, 1, 2, 4, and 8** false positives per scan, as outlined in prior studies. Additionally, lesion-level performance was assessed using the Area Under the Receiver Operating Characteristic Curve (AUC) along with a 96% confidence interval (CI).


## Task: Segmenation

Utilized the Vists3D

## Task: Classification


## Task: Targeted Synthetsis


## License
This project is licensed under the MIT License.

## Contact
For inquiries, please reach out to Fakrul Islam Tushar at tushar.ece@duke.edu
