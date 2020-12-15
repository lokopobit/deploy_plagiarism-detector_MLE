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

### Jupyter notebooks workflow detailed
#### First notebook: Data Exploration


1. Get the data: the dataset is uploaded at [University of Sheffield](https://ir.shef.ac.uk/cloughie/resources/plagiarism_corpus.html "University of Sheffield").
2. Define types of plagiasm: copy-pasted from source (cut), copied and paraphrased from source (light)n based on source but expressed differently (heavy) and not plagiarized (non). As you can image the type of plagiarism heavy is the most challenging.  
3. Study the distribution of the data: the dataset contains only 100 texts (very small) evenly distributed across the 5 different tasks (the tasks are questions and the texts are the answers). The original answers from wikipedia (source text) are also provided. The records are fiarly balanced with respect to the plagisism types.


#### Second notebook: Feature Engineering




#### Third notebook: Training and Deployment



### Changes between old sagemaker version (1) and latest (2)

See changes\_in\_sagemaker\_version.txt. Take a look to [sagemaker latest version](https://sagemaker.readthedocs.io/en/stable/v2.html "sagemaker latest version").


### Reviewer comments

Suggestions: in the second notebook, function make\_csv(), get rid of any incomplete rows using dropna() method of da pandas DataFrame. This could increase  the test accuracy.

### TODO list



