# ML Theory

## What is Machine Learning?
A computer program is said to *learn* from experience E w.r.t some task T and some performance measure P, if it's performance on T, as measured by P, improves with experience E.

## Types of Learning Algorithms
- Supervised Learning
- Unsupervised Learning

### Supervised Learning
**In supervised learning, we are providing the computer with a set of "right" answers for each input value. This is called the training data. The job of the computer is to then *learn* from these values and _guess_ another "right" answer which wasn't provided.**

In supervised learning, we are given a data set and already know what our correct output should look like, having the idea that there is a relationship between the input and the output.

Supervised learning problems are categorized into "regression" and "classification" problems. In a regression problem, we are trying to predict results within a continuous output, meaning that we are trying to map input variables to some continuous function. In a classification problem, we are instead trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories. 

Supervised learning problems are of two types:

1. Regression Problems

2. Classification Problems

#### Regression
![House Price Prediction](https://user-images.githubusercontent.com/39856034/110796216-b8647600-829d-11eb-98be-ac1fc3417a2c.png)

**In the above example, we are trying to predict a continuous value attribute (cost).**


#### Classification
![breast cancer detection](https://user-images.githubusercontent.com/39856034/110796015-7e936f80-829d-11eb-9aac-cc1f95bf85e0.png)

**In the above example, we are trying to predict a discrete value attribute (malignant/not-malignant).**


### Unsupervised Learning
Unsupervised learning allows us to approach problems with little or no idea what our results should look like. We can derive structure from data where we don't necessarily know the effect of the variables.

We can derive this structure by clustering the data based on relationships among the variables in the data.

With unsupervised learning there is no feedback based on the prediction results.

#### Clustering: 
Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.

#### Non-clustering
The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a cocktail party).
