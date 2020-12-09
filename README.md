# Introduction

This repository builds a binary classifier to detect plagiarized text files. That is, a model that can distinguish if an answer to a test question was copied to some degree. The model is a very simple neural network with just one hidden layer defined with Pytorch. The model is trained and deployed using SageMaker service of Amazon Web Services (AWS).  

Note: Detecting plagiarism is an active area of research; the task is non-trivial and the differences between paraphrased answers and original work are often not so obvious.


### Jupyter notebooks workflow at a glance

The project is divided in three notebooks, each of them performing a data modelling step, from exploration to deployment.

1.- The file 1\_Data\_Exploration.ipynb is in charge of the data exploration step:   

- Get the data.
- Define types of plagiasm.
- Study the distribution of the data.

2.- The file 2\_Plagiarism\_Feature\_Engineering.ipynb is in charge of data pre-processing and creation of data features. In our case these features are similarity measures between text data:


* Clean and pre-process the text data.
* Define features for comparing the similarity of an answer text and a source text, and extract similarity features.
* Select "good" features, by analyzing the correlations between different features.
* Create train/test `.csv` files that hold the relevant features and class labels for train/test data points.

3.- The file 3\_Training\_a\_Model.ipynb is in charge of training and deploying:

* Upload your train/test feature data to S3.
* Define a binary classification model and a training script.
* Train your model and deploy it using SageMaker.
* Evaluate your deployed classifier.

