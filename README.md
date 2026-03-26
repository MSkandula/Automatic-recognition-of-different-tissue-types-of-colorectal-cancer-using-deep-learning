**Automatic Tissue Classification in Colorectal Cancer using Deep Learning**

**Built during Bachelor's at GITAM University Hyderabad**

**Overview**

* Colorectal cancer diagnosis relies heavily on manual histopathological analysis, which is time-consuming, expertise-driven, and subject to variability
* This project develops an end-to-end deep learning pipeline to classify histopathology images into 8 tissue types
* The project compares a **custom CNN** and a **VGG16-based transfer learning model** to evaluate performance on medical imaging data
* Focus is not just on accuracy, but on understanding **model behavior and generalization**

**Problem Statement**

Manual tissue classification is:

* Slow and labor-intensive
* Dependent on expert knowledge
* Prone to inconsistency

The goal of this project is to:

* Automate tissue classification using deep learning
* Achieve high accuracy and reliability
* Compare custom architectures vs transfer learning approaches

**Dataset**

* Source: TensorFlow Datasets (colorectal_histology)
* Total samples: 5000
* Image resolution: 150 x 150
* Number of classes: 8

Classes:

* Tumor
* Debris
* Stroma
* Lymphocytes
* Complex
* Mucosa
* Adipose
* Empty

**Approach**

**1. Data Pipeline**

* Loaded dataset using TensorFlow Datasets
* Applied normalization and scaling
* Implemented data augmentation:

  * Rotation
  * Zoom
  * Shift
  * Horizontal flip

**2. Model 1 - Custom CNN**

* Convolutional layers (32 → 256 filters)

* Batch Normalization

* MaxPooling layers

* Dropout for regularization

* Optimized using Adam optimizer

* Designed specifically for learning histopathological texture and structure

**3. Model 2 - Transfer Learning (VGG16)**

* Pretrained VGG16 (ImageNet)
* Training strategy:

  * Phase 1: Freeze convolutional base
  * Phase 2: Fine-tune entire network
* Custom dense classification head

**Results**

* Custom CNN:

  * Accuracy: 0.94
  * Macro F1 Score: 0.94
  * Weighted F1 Score: 0.94

* VGG16 Transfer Learning:

  * Accuracy: 0.89
  * Macro F1 Score: 0.89
  * Weighted F1 Score: 0.89

* The custom CNN achieved higher accuracy and more balanced class-wise performance

**Training Behavior**

Custom CNN:

* Smooth convergence
* Stable validation accuracy (~0.91–0.92)
* Minimal overfitting

VGG16:

* Slower convergence
* Higher validation fluctuations
* Overfitting observed in later epochs

**Class-wise Performance Insights**

Custom CNN:

* Strong and consistent recall across all classes
* High performance on:

  * Tumor
  * Lymphocytes
  * Adipose

VGG16:

* Performance drop in:

  * Debris
  * Stroma
  * Complex

* Indicates that pretrained ImageNet features do not fully align with histopathology patterns

**Confusion Matrix Analysis**

Custom CNN:

* Strong diagonal dominance
* Minimal misclassification
* Better class separation

VGG16:

* Confusion observed between:

  * Debris and Stroma
  * Complex and other tissues

**Key Insights**

* Transfer learning did not outperform the custom CNN in this case
* Domain-specific feature learning can be more effective than generic pretrained features
* Smaller, well-designed models can generalize better on specialized datasets
* Transfer learning is not universally optimal, especially in medical imaging

 **Skills Demonstrated**

* Deep Learning model design
* Transfer learning and fine-tuning
* Data augmentation techniques
* Model evaluation (confusion matrix, classification report)
* End-to-end machine learning pipeline development

 **Tech Stack**

* TensorFlow / Keras
* TensorFlow Datasets
* NumPy
* Matplotlib
* Scikit-learn



## **Academic Context**

* This project was developed during my Bachelor's at GITAM University Hyderabad
* Focused on applying deep learning to real-world medical imaging problems

**Author**

* Mahesh Sai Kandula



That’s the difference between a “project” and something that gets you interviews.
