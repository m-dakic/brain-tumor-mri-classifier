# Brain Tumor MRI Classification using ResNet-18

An Learning framework utilizing Transfer Learning and Fine-Tuning to classify brain MRI slices into four distinct states with a high test accuracy.

## 📊 Dataset Source & Licensing
The data utilized in this project is a curated aggregation of brain tumor MRI slices, providing a balanced distribution across malignant, benign, and healthy tissue structures.
* **Dataset Link:** [Brain Tumor MRI Dataset (Kaggle)](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)
* **Licensing & Data Usage:** This dataset is distributed under the **CC BY 4.0 (Creative Commons Attribution 4.0 International)** license. It permits open sharing, adaptation, and commercial utilization, provided appropriate credit and attribution are given to the original creators.

## ⚙️ Dependencies & Installation
To set up this project locally, clone the repository and install the verified software environment:

```bash
# Clone the repository
git clone [https://github.com/m-dakic/brain-tumor-mri-classifier.git](https://github.com/m-dakic/brain-tumor-mri-classifier.git)

# Move into the project directory
cd brain-tumor-mri-classifier

# Install all required framework packages
pip install -r requirements.txt

## 📊 Dataset & Categories
The model is evaluated on 1,600 completely unseen test images across four balanced classes:
* **Glioma**
* **Meningioma**
* **Pituitary**
* **No Tumor**

## 🏗️ Model Architecture & Workflow
1. **Foundational Backbone:** ResNet-18 pre-trained on ImageNet.
2. **Phase 1 - Baseline:** Classifier head training with a frozen feature extractor.
3. **Phase 2 - Fine-Tuning:** Full network optimization using a low-velocity learning rate.
4. **Explainable AI (XAI):** Visual auditing using Grad-CAM and Integrated Gradients.

## 📈 Final Performance Summary
* **Healthy Tissue Detection:** Perfect recall for the `notumor` class.
* **Pituitary Performance:** Robust feature matching yielding a 97.63% F1-score.

### 🔬 Forensic Error Profiling & Clinical Risk Assessment
A detailed audit of the misclassified glioma cases reveals distinct diagnostic boundaries:
* **High-Severity Misses:** Glioma cases falsely marked as `notumor`. These represent critical False Negatives that would delay urgent patient care.
* **Cross-Tumor Swaps:** Glioma cases mistaken for `meningioma`. While the patient remains tracked within the healthcare system, the distinct difference in tumor aggressiveness means this mix-up risks suboptimal treatment.

## 💡 Deployment Strategy
Given these specific failure modes, this model is not designed to function as an autonomous diagnostic tool. Instead, it holds exceptional utility as an automated, high-speed **second-opinion triage assistant** to support radiologists—drastically reducing manual screening times while relying on human expertise to catch complex tissue boundaries.
