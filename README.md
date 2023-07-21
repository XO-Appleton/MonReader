# MonReader

## Problem Statement

Decide if a image is a page being fliped or not. 

## Data Description

The images are from video recordings of reading through a book. The images are stored under training and testing folders and marked as flip or not flip respectively.

## Approach

As the images have been nicely structured and presented, we simply constructed a data pipeline to import the images from the folders. We applied image augmentation technique to avoid overfitting and improve the model's performance.

We tried out two models for this project. One being a CNN model built from scratch and the other is a pretrained ViT model fine tuned on our dataset. 

- The CNN model achieved 92% training accuracy and 84% testing accuracy. We also tested the F1 score against different threshold and found the best F1 score at probability threshold of 0.2.

- The ViT model achieved 100% training accuracy and 99.83% testing accuracy. 

## Metrics

We used both Accuracy and F1-score to evaluate the models.

## Final Model

As the dataset is reasonably balanced. We decided to finalize our model to be the ViT model as it achieved very high accuracy score. The model was uploaded to HuggingFaceHub and can be find at [here](https://huggingface.co/XO-Appleton/vit-base-patch16-224-in21k-MR).

![Model Sample Result](https://github.com/XO-Appleton/MonReader/assets/41369365/0dfa189e-d67a-449b-bd40-3bbfa910ecb9)

## Summary

In this project, we developed a computer vision model which is able to classify if a page is being flipped or not. Despite the high accracy our final model was able to achieve on our dataset, when tested with images from internet which does not resemble the characteristics of our source, its performance decreses significantly as it tends to classify everything to be flipping. To resolve this issue, we plan on augmenting the training set with images from different sources in the future.
