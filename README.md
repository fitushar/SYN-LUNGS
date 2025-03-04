# SYN-LUNGS
**SYN-LUNGS: Towards Simulating Lung Nodules with Anatomy-Informed Digital Twins for AI Training**

**Abstract:** AI models for lung cancer screening struggle with data scarcity, limiting generalizability and clinical applicability. Generative models for image synthesis are constrained by training data variability. We introduce SYN-LUNGS, a framework for generating high-quality 3D CT images with detailed annotations. SYN-LUNGS integrates XCAT3 phantoms for digital twin generation, X-Lesions for nodule simulation (varying size, location, appearance), and DukeSim for CT image formation with vendor and parameter variability. The dataset includes **3,072** nodule images from **1,044** simulated CT scans, **512** lesions, and **174** digital twins. Effectiveness was shown for nodule detection, segmentation, cancer classification, and synthesis. Models trained on clinical + simulated data outperform clinical-only models, with **10%** improvement in detection, **2–9%** in segmentation, **2–9%** in classification and enhanced synthesis. By integrating anatomy-informed simulations, this work facilitates future AI model development such as for rare disease representation and model reliability.



# Simulated and Clinical Dataset
* [1]SYN-LUNGS: Can be requested through, https://cvit.duke.edu/resources/
* [2] Duke Lung Cancer Screening Dataset : https://zenodo.org/records/13799069
* [3] LUNA16: https://luna16.grand-challenge.org/
* [4] MSD Task06: http://medicaldecathlon.com/

Coming soon!!!
1) Training scripts
2) Inference Scripts
3) Evaluation Scripts
4) Clinical and Simulated Datasets
