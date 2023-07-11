# Overview
The purpose of this project was to create a model that detects pneumonia from xray images. The model was able to achieve a precision of 1.0, recall of 0.997, and an accuracy of 0.998 on the test dataset.

# Repository Overview
This project contains several folders:

- data, which contains the training, cross validation, and testing data.
- logs, which collects and stores detailed information during training
- models, which contains the successful pneumonia model
- test, which contains 16 photos that we can use as additional confirmation that the model predicts correctly
- better_pneumonia, which contains a copy of the final code for the project

# Data

There are 5,863 X-Ray images (JPEG) with 2 categories (Pneumonia/Normal). The publisher of this dataset on kaggle noted that:

> The chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care. 

> For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnoses for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.

Here is the citation:

![image](https://github.com/DylanBerger/Pneumonia/assets/82914031/d70e3ba5-0eca-43bc-91f2-540723e1c8ab)

The dataset was also heavily imbalanced, favoring pneumonia images, something that is accounted for in the project. Despite this, more pneumonia images is not a bad thing. If anything, we would perfer that the model be better at detecting pneumonia than normal cases because a false positive diagnosis is better than a false negative, especially in medicine.  

# Technical Overview

We can split the project into the following phases:

1. Importing dependencies
2. Data Preprocessing
3. Model design
4. Model Training
5. Model Evaluation/Testing
6. Saving the model

# Results

As mentioned earlier, the model attained a precision of 1, a recall of 0.997 and an accuracy of 0.998 on the testing set, which is very good. I tested the model on 16 more images (8 pneumonia and 8 normal), and the model got all of those correct.

![image](https://github.com/DylanBerger/Pneumonia/assets/82914031/11a6b2e6-f43c-494e-98f7-0001abbd4ded)

Here is the loss of the training and validation set during training: 

![image](https://github.com/DylanBerger/Pneumonia/assets/82914031/f6a8f041-051d-45cb-94f2-41a555642e1b)

It converges as expected. Here is the accuracy during training for further evaluation: 

![image](https://github.com/DylanBerger/Pneumonia/assets/82914031/7c8e9f43-9f9e-4296-90aa-a4fa623ff678)

The model produced really impressive results given the small size of the dataset, but it is far from complete. Convolutional neural networks require orders of magnitude more images to be effective, so the next step would be to train it on more data, and adjust the model accordingly. Additionally, the data was primarily from children ages 1-5, so to create a general model, we need images from a strong variety of ages, conditions, and whatever would cause variety in the data. I would imagine that to account for this, the model would need to increase in complexity. 

For now, however, the model works really well with the dataset, hope you enjoyed!

