# Linear Regression

## Cost Function
We can measure the accuracy of our hypothesis function by using a cost function. 
This takes an average difference (actually a fancier version of an average) of all the results of the hypothesis with inputs from x's and the actual output y's.
This function is also known as squared error function.

![cost function eqn](https://i.ibb.co/5jx3S5f/image.png)

### Cost function intuition
If we try to think of it in visual terms, our training data set is scattered on the x-y plane. We are trying to make a straight line (defined by h(x) which passes through these scattered data points.

Our **objective** is to get the best possible line. The best possible line will be such so that the average squared vertical distances of the scattered points from the line will be the least. Which means, cost function should be minimum.  Ideally, the line should pass through all the points of our training data set. In such a case, the value of <img src="https://render.githubusercontent.com/render/math?math=J(\theta_0,\theta_1)"> will be 0. The following example shows the ideal situation where we have a cost function of 0.

![ideal scenario of min cost func](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/_B8TJZtREea33w76dwnDIg_3e3d4433e32478f8df446d0b6da26c27_Screenshot-2016-10-26-00.57.56.png?expiry=1615593600000&hmac=wCDd-VlCY1x7eD29FGGwQdtOAGKtXB1afXUgBefYpyk)

However in a real scenario, we take different <img src="https://render.githubusercontent.com/render/math?math=\theta"> values and find <img src="https://render.githubusercontent.com/render/math?math=h(x)">, and then find the <img src="https://render.githubusercontent.com/render/math?math=\theta"> value which minimises cost function.

![Cost function vs h(x)](https://i.ibb.co/QdN6n96/image.png)

#### Cost Function with 2 parameters
![cost function with 2 parameters](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/hsGgT536Eeai9RKvXdDYag_2a61803b5f4f86d4290b6e878befc44f_Screenshot-2016-10-29-09.59.41.png?expiry=1615593600000&hmac=R9MQGBu4E7bge5Jn9rUPmzHX4_M9ion-3aDUUs9N66A)

The graph above minimizes the cost function as much as possible and consequently, the result of <img src="https://render.githubusercontent.com/render/math?math=\theta_0"> and <img src="https://render.githubusercontent.com/render/math?math=\theta_1"> tend to be around 0.12 and 250 respectively. Plotting those values on our graph to the right seems to put our point in the center of the inner most 'circle'. 


## Gradient Descent
![Gradient Descent Example](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/bn9SyaDIEeav5QpTGIv-Pg_0d06dca3d225f3de8b5a4a7e92254153_Screenshot-2016-11-01-23.48.26.png?expiry=1615593600000&hmac=vwTDK5y-0sn3g2yYsDpbIwd5vY6HFhkaoTkKP1xpyVA)

We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum.  The red arrows show the minimum points in the graph.

The way we do this is by taking the derivative (the tangential line to a function) of our cost function. The slope of the tangent is the derivative at that point and it will give us a direction to move towards. We make steps down the cost function in the direction with the steepest descent. The size of each step is determined by the parameter α, which is called the learning rate. 

For example, the distance between each 'star' in the graph above represents a step determined by our parameter α. A smaller α would result in a smaller step and a larger α results in a larger step. The direction in which the step is taken is determined by the partial derivative of <img src="https://render.githubusercontent.com/render/math?math=J(\theta_0,\theta_1)">. Depending on where one starts on the graph, one could end up at different points. The image above shows us two different starting points that end up in two different places. 

### Algorithm
![Gradient Descent Algorithm](https://i.ibb.co/0fMPRSw/image.png)
