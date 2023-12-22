# BrainTumorDetectionCNN
### Detecting Gliomas, Meningiomas, and Pituitary Brain Tumors Using Convolutional Neural Networks
Access the full colab notebook [here](https://colab.research.google.com/drive/1rvXt8XBbyUkSVo73d0YCBkaSmE9ebSRx?usp=sharing) for all code and in-depth explanations. 

## Table of Contents:
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
- Develop a convolutional neural network specialized in detecting glioma, pituitary, and meningioma brain tumors
- Utilize pre-trained models to increase recall in tumor classes
## Project Outcomes 
- Developed a simple CNN with a minimum 93% recall in all tumor classes and an average recall of 94% in tumor classes
- Applied transfer learning to EfficientNetB0 to achieve over 95% recall for all tumor classes and 96.4% average recall in the tumor classes

## Background Information
Advancements in medical image classification hold the potential to streamline the tumor detection process. While not unerring, technology-based classification offers a preliminary categorization of tumors, facilitating quicker decision-making for professionals.

The three tumor types we will focus on are gliomas, meningiomas, and pituitary tumors. 

Gliomas:
- Gliomas are tumors that arise from glial cells, which are supportive cells in the brain. Symptoms of gliomas vary depending on the location and size of the tumor. Treatment options include surgery, radiation therapy, and chemotherapy.

Meningiomas:
- Meningiomas are tumors that originate in the meninges, the layer of tissue covering the brain and spinal cord. These tumors are usually benign and slow-growing, but they can cause issues if they grow or press on nearby structures.

Pituitary Tumors:
- Pituitary tumors are growths that develop in the pituitary gland, a small gland at the base of the brain that regulates hormone production. Symptoms of pituitary tumors can include hormonal imbalances, changes in growth, and visual disturbances.

## Evaluation Metrics 
We will be looking at accuracy, precision, and recall. In our problem domain, we favor a classifier with high recall in the tumor classes. Why is this? Missing a true positive (a tumor case) carries more significant consequences than misclassifying a non tumor case as a tumor case. Prioritizing high recall in the tumor classes will allow us to capture as many true tumor cases as possible. While this approach may lead to lower precision in the tumor classes– the classifier may assign non-tumor cases to tumor classes more liberally– , we will be able to minimize the risk of overlooking true tumor cases.


