---
published: true
---

---
published: true
layout: post
title: The Tin Man's Heart
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

