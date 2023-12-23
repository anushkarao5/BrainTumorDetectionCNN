# BrainTumorDetectionCNN
### Detecting Gliomas, Meningiomas, and Pituitary Brain Tumors Using Convolutional Neural Networks
Access the full colab notebook [here](https://colab.research.google.com/drive/1Pt5eP8k2_BcnuVyksN1Qu_O1P0XF4yb3?usp=sharing) for all code and in-depth explanations. 

## Table of Contents
- [Project Objective](#project-objective)
- [Project Outcomes](#project-outcomes)
- [Background Information](#background-information)
- [Understanding the Data](#understanding-the-data)
- [Evaluation Metrics](#evaluation-metrics)
- [Model Types](#model-types)
- [Model Performance](#model-performance)
- [Conclusions](#conclusions)
  
## Project Objective
The objectives of this project are to:
- Develop a convolutional neural network specialized in detecting gliomas, meningiomas, and pituitary brain tumors
- Utilize pre-trained models to increase recall in tumor classes
## Project Outcomes 
- Developed a simple CNN with a minimum of 93% recall in all tumor classes and an average recall of 94% in tumor classes
- Applied transfer learning to EfficientNetB0 to achieve over 95% recall in all tumor classes and 96.4% average recall in the tumor classes

## Background Information
Advancements in medical image classification hold the potential to streamline the tumor detection process. While not unerring, technology-based classification offers a preliminary categorization of tumors, facilitating quicker decision-making for professionals.

<p align="center">
  <img src="Images/brain_tumor_background_image.jpeg" alt="Image Alt Text" width="500px" height="auto">
</p>
<p align="center">
  <a href="https://awaregleneaglesglobalhospitallbnagar.com/health-plus-blog/what-are-the-common-sign-and-symptoms-of-a-brain-tumour/">Image Credits</a>
</p>

The three tumor types we will focus on detecting are gliomas, meningiomas, and pituitary tumors. 

Gliomas:

- Gliomas are tumors that arise from glial cells, which are supportive cells in the brain. Symptoms of gliomas vary depending on the location and size of the tumor. Treatment options include surgery, radiation therapy, and chemotherapy.

Meningiomas:

- Meningiomas are tumors that originate in the meninges, the layer of tissue covering the brain and spinal cord. These tumors are usually benign and slow-growing, but they can cause issues if they grow or press on nearby structures.
  
Pituitary Tumors:

- Pituitary tumors are growths that develop in the pituitary gland, a small gland at the base of the brain that regulates hormone production. Symptoms of pituitary tumors can include hormonal imbalances, changes in growth, and visual disturbances.


## Understanding the Data
- This data was taken from [Kaggle’s Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset?rvi=1). 
- The dataset consists of a training and testing folder. 
  - There are 5712 images in the training set and 1311 images in the test set. 
- I further split the test set into a testing set and a validation set.
  
Here is the distribution of images per class:

<p align="center">
  <img src="Images/DataDistribution.png" alt="Image Alt Text" width="700px" height="auto">
</p>

As we can see, there are significantly more no tumor cases than tumor cases, especially in the validation and testing sets.  Since the models have more instances of no tumor cases to learn from, we expect that they will be best able to detect no tumor cases. 
However, there is a similar amount of images across the tumor classes. We expect the models to detect tumor cases across all cases similarly because the distribution of tumor cases is similar.

## Evaluation Metrics 
We will evaluate the performance of our model using accuracy, precision, and recall. **In our problem domain, we favor a classifier with high recall in the tumor classes.** Why is this? Missing a true positive (a tumor case) carries more significant consequences than misclassifying a non-tumor case as a tumor case. Prioritizing high recall in the tumor classes will allow us to capture as many true tumor cases as possible. While this approach may lead to lower precision in the tumor classes– the classifier may assign non-tumor cases to tumor classes more liberally–, we will be able to minimize the risk of overlooking true tumor cases.

## Model Types
We will explore 4 CNN types.
1) A basic three-layered CNN with global max pooling
2) Pretrained ResNet50
3) Pretrained InceptionNet
4) Pretrained EfficientNet
## Model Performance
To evaluate model performance, let us see how well each classifier is able to recognize each type of tumor. 

**Gliomas**
<p align="center">
  <img src="Images/PvRGlioma.png" alt="Image Alt Text" width="700px" height="auto">
</p>

Click [here](https://docs.google.com/document/d/1rzPfFhG4TEHhzyGpa0jx905BPoGSowLiE98WUArPvhM/edit?usp=sharing) to learn more about the basic CNN model for classification (conv2D layers, pooling, dense layers, and softmax activiations).

Click [here](https://docs.google.com/document/d/1tONf-wTolvjdriQJEn178vQQC4XlJ6PoGlZtUC6LbvA/edit?usp=sharing) to learn more about the pre-trained models.

