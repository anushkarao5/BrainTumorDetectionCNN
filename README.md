# BrainTumorDetectionCNN
### Detecting Gliomas, Meningiomas, and Pituitary Brain Tumors Using Convolutional Neural Networks
Access the full colab notebook [here](https://colab.research.google.com/drive/1Pt5eP8k2_BcnuVyksN1Qu_O1P0XF4yb3?usp=sharing) for all code and in-depth explanations. 

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
- Developed a simple CNN with a minimum of 93% recall in all tumor classes and an average recall of 94% in tumor classes
- Applied transfer learning to EfficientNetB0 to achieve over 95% recall in all tumor classes and 96.4% average recall in the tumor classes

## Background Information
Advancements in medical image classification hold the potential to streamline the tumor detection process. While not unerring, technology-based classification offers a preliminary categorization of tumors, facilitating quicker decision-making for professionals.

The three tumor types we will focus on detecting are gliomas, meningiomas, and pituitary tumors. 

Gliomas:
- Gliomas are tumors that arise from glial cells, which are supportive cells in the brain. Symptoms of gliomas vary depending on the location and size of the tumor. Treatment options include surgery, radiation therapy, and chemotherapy.

Meningiomas:
- Meningiomas are tumors that originate in the meninges, the layer of tissue covering the brain and spinal cord. These tumors are usually benign and slow-growing, but they can cause issues if they grow or press on nearby structures.

Pituitary Tumors:
- Pituitary tumors are growths that develop in the pituitary gland, a small gland at the base of the brain that regulates hormone production. Symptoms of pituitary tumors can include hormonal imbalances, changes in growth, and visual disturbances.

## Evaluation Metrics 
We will be looking at accuracy, precision, and recall. In our problem domain, we favor a classifier with high recall in the tumor classes. Why is this? Missing a true positive (a tumor case) carries more significant consequences than misclassifying a non tumor case as a tumor case. Prioritizing high recall in the tumor classes will allow us to capture as many true tumor cases as possible. While this approach may lead to lower precision in the tumor classes– the classifier may assign non-tumor cases to tumor classes more liberally– , we will be able to minimize the risk of overlooking true tumor cases.

## Model Types
**ResNet50**

- Residual Networks (ResNets) are designed to address challenges in training deep neural networks, particularly the vanishing gradient problem. Resnets mitigate this issue through the use of shortcut connections that allow gradients to flow directly to earlier layers without passing through all intermediate layers. 
- The building block of a ResNet is the residual block. This block includes both a shortcut path and a main path. The shortcut path bypasses the convolutional layers and directly connects the input to the output, while the main path processes the input through the convolutional layers. The output of the main path F(x) is then added to the output of the shortcut path (x), yielding the output of the residual block y=F(x)+x. 
- The goal is to make the output of the main path F(x) as close to zero as possible so that the output y approximates the input x. The network learns to adjust the weights in the main path to minimize F(x). Consequently, the output y becomes primarily influenced by the shortcut path, which involves few layers, preventing the issue of the vanishing gradients. 

**InceptionNet**
- InceptionNet, also known as GoogleNet, uses inception modules, which employ parallel filters of different sizes at the same layer to capture features at various spatial scales. An inception model typically consists of 1x1, 3x3, and 5x5 convolutional filters followed by a max pooling layer. The filters are applied in parallel, and their outputs are concatenated before being passed to the next module in the network. 
- The core concept behind the inception modules is to leverage filters of different sizes to capture information at both global and local scales: larger kernels are useful for information that is distributed globally, while smaller kernels are better for information that is distributed locally. 
- By combining filters of various sizes, the InceptionNet network can represent a wide range of features, making it ideal for computer vision applications. 

**Efficient Net**
- EfficientNet employs a compound scaling approach to efficiently scale up models by maintaining a fixed ratio across three key dimesions: width, depth, and image resolution. This scaling method uniformly scales all three dimensions with a fixed ratio, contributing to a harmonious adjustment of model size.  
- The compound scaling is controlled by a single parameter phi, which determines the model size. Larger phi values tend to result in larger and more powerful models. 
- This technique has resulted in increased performance in various computer vision tasks. 

