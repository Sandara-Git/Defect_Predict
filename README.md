# Defect_Predict

### Assumptions 
Assume that historical data is a good indicator of future defects.

Assume that the chosen features are sufficient for defect prediction.

### Data sets

In this experiment, I have used open source publicly available data from PROMISE Software Engineering Database

### Why Machine Learning or NLP

There are several theoretical approaches to address this problem. One of these might be to use a supervised machine learning model to classify test cases based on their relationship to a specific code change. This would involve training the model with a labeled dataset containing pairs of code changes and test cases, along with the relationship label.

#### NLP model
An NLP model could be useful for processing code text and test case names and generating numerical features that represent the text content. These numerical features could include, for example, the frequency of certain words or phrases, or the semantic similarity between the code and the test cases.

#### Classification Algorithm
A classification algorithm, such as SVM or Random Forest, could use these numerical features to associate code changes with the most relevant test cases. It is important to note that these algorithms require a labeled dataset in order to train the model.


As for both algorithms working together, you could use the NLP model to generate numerical features from code text and test cases, and then use these features as input to a classification algorithm, such as SVM or Random Forest. 
For the model, machine learning algorithms such as Random Forest, SVM, or even a Neural Network are recommended.

## Process of Defect_Predict
![Smart_test_selector drawio](https://github.com/Sandara-Git/Defect_Predict/assets/140485221/db004b8c-2b94-41b1-be07-eabbeb88e257)

## References
 Research paper link: https://dl.acm.org/doi/abs/10.1145/3379247.3379278

 Software Defect Prediction using Deep Learning
