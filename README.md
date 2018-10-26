# logisticRegression
Implementing logistic regression to classify handwritten digits from MNIST from scratch

Terminology used:


y is the class label, which is either 0 or 1


x is an image from the dataset which is a vector of size 1x782


w is the weight vector, which is a 9x782 matrix


P(y=1|x,w) is the probability that a given sample x and weight vector w, the class label y=1


This is given by:

![P(Y=k|X=x,w)](https://latex.codecogs.com/gif.latex?P%28Y%3Dk%7CX%3Dx%29%3D%20%5Cfrac%7Bexp%28w%5ET_kx%29%7D%7B1&plus;%20%5Csum%20%5E%7BK-1%7D%20_%7Bi%3D1%7D%20exp%28w_i%5ETx%29%7D%3B%20k%3D1%2C2%2C..%2CK-1)

![P(Y=K|X=x,w)](https://latex.codecogs.com/gif.latex?P%28Y%3DK%7CX%3Dx%29%3D%20%5Cfrac%7B1%7D%7B1&plus;%20%5Csum%20%5E%7BK-1%7D%20_%7Bi%3D1%7D%20exp%28w_i%5ETx%29%7D)

For MNIST dataset, K=10 (numbers 0 to 9).

Logistic regression is an optimiztion problem, where the object function to be maximized is the conditional log likelihood. In other words, we need to find the weight vector w such that the object function has its maximum possible value. The object function is given by: 

![ObjectFunc](https://latex.codecogs.com/gif.latex?J%28w%29%3D%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%20%28y_i-1%29w%5ETx_i-ln%281&plus;e%5E%7B-w%5ETx_i%7D%29)

The gradient of this objecct function is given by:

![Gradient](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%20J%28w%29%29%7D%7B%5Cpartial%20w%7D%3D%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%20%28y_i-P%28y_i%3D1%7Cx_i%2Cw%29%29x_i)

Hence, the update equation for logistic regression is :

![UpdateEqn](https://latex.codecogs.com/gif.latex?w_%7Bupdate%7D%3Dw&plus;%5Ceta%20%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%20%28y_i-P%28y_i%3D1%7Cx_i%2Cw%29%29x_i)

Where eta is the leaning rate.

With each update, the weight vector w slowly moves to the global optimum value, at which point, most of the classes in the testset are classified accurately
