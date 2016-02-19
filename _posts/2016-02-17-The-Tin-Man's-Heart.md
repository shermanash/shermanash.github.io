---
published: true
layout: post
title: "The Tin Man's Heart"
---






Our latest project involved creating a predictive classification model from a real life dataset.  Our team used a dataset relating to heart disease from the excellent [UCI Machine Learning Database](https://archive.ics.uci.edu/ml/datasets/Heart+Disease).  

The dataset is comprised of patient information from medical institutes in 4 different locations- Cleveland (Ohio), Long Beach (California), Budapest (Hungary), and Zurich (Switzerland).  

Many machine learning studies have been done using this data to predict the presence or absence of heart disease, and a sample of these studies are below:


![prev_studies.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/prev_studies.png)

My goal was to create a model that used only features that could feasibly be known by a patient before they stepped foot in a hospital, to assess their risk factor for heart disease, and retain an accuracy score on par with the previous studies.

After selecting features, I used [BigML](https://bigml.com/) to create a network graph illustrating the main relationships in the data.  These are shown below.

![Net1.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/Net1.png)
![Net2.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/Net2.png)
![Net4.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/Net4.png)
![Net5.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/Net5.png)
![network.gif](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/network.gif)

Next, I used BigML to create a decision tree.  Here is an aggressively pruned tree that only uses 4 features, and has an accuracy of 70%:
<iframe src="https://bigml.com/embedded/model/pJsPoBVcF2jbTsvtGZLg1mQE6Wj" frameborder="0" allowtransparency="true" allowfullscreen="allowfullscreen" width="600" height="400"></iframe>


And here is another tree, using all of the features, with an improved accuracy score, but a similar overall structure:
<iframe src="https://bigml.com/embedded/model/c3PhwxuqgNIPkx6pzxlwl7Wg05e" frameborder="0" allowtransparency="true" allowfullscreen="allowfullscreen" width="800" height="400"></iframe>

The visualization is nice, but the accuracy wasn't as good as the models built in [SKLearn](http://scikit-learn.org/stable/)
BigML-
![BigML_Confusion.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/BigML_Confusion.png)
Scores for a selection of SKLearn models-
![classify_compare.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/classify_compare.png)
One of the best performing models was logistic regression, and due to the nature of its construction, it has the added advantage of giving interpretable probabilities to each of its classifications.  This was very important to me, as simply telling someone whetehr or not they have heart disease is not as important as assigning a percentage-based risk assessment.  Here is the learning curve for the logistic regression model:
![logistic_learning.curve.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/logistic_learning.curve.png)
As the ROC Curve, and confusion matrix below demonstrate, the model does a decent job predicting the presence or absence of heart disease.
![Svc_ROC.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/Svc_ROC.png)
![SVC_Confusion.png](https://raw.githubusercontent.com/shermanash/shermanash.github.io/master/images/SVC_Confusion.png)

Since the model only uses features that anyone could estimate, a natural extension of this project would be to create a live prediction model.  This model is currently hosted on my local machine.

Soon, I hope to have the model hosted live on the internet, with sliders and a cleaner design.
