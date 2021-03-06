# Machine Learning Note

github 不支持 LaTeX 公式，然而我懒得去使用一些别的方式去支持，可以通过安装 [chrome 插件](https://chrome.google.com/webstore/detail/mathjax-plugin-for-github/ioemnmodlmafdkllaclgeombjnmnbima)解决

[coursera ML](https://www.coursera.org/learn/machine-learning)

## Week 1

### 机器学习的定义：

A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E.

一个程序被认为能从经验 E 中学习，解决任务 T，达到性能度量 P。当且仅当有了经验 E 之后，经过 P 的评判，程序在处理 T 的时候性能有所提升。

### 机器学习的两大主要类型：

1. 监督学习（supervised learning）
2. 无监督学习（unsupervised learning）

### 监督学习（supervised learning）

we are giving a data set and already know what our correct should look like, having the idea that there is a relationship between the input and the output.

_意指给出一个实验法，需要部分数据集已经有正确的答案，算法的结果是算出更多正确的数据。_

#### 符号与含义（Symbol & Meaning）

| symbol                                          | meaning                                            |
| ----------------------------------------------- | -------------------------------------------------- |
| m                                               | Number of training expamples                       |
| x‘s                                             | "input" variable / feature                         |
| y's                                             | "output" variable / "target" variable              |
| (x, y)                                          | one training example(one row in dataset)           |
| (x<sup>(i)</sup>, y<sup>(i)</sup>)              | i<sub>th</sub> training expample(i just the index) |
| (x<sup>(i)</sup>, y<sup>(i)</sup>); i = i,... m | a training set                                     |
| X                                               | the space of input values                          |
| Y                                               | the space of output values                         |
| θ<sub>i</sub>'s                                 | (Model)Parameters                                  |

superscript "(i)" in the notation is simply an index into the training set, and has nothing to do with exponentiation.

#### 模型的表示（Model Respresentation）

To describe the supervised learning problem slightly more formally, our goal is, given a training set, to learn a function **`h`**: `X —> Y`, so that `h(x)` is a "good" predictor for the corresponding(相符的) value of `y`. For historical reasons, this function `h` is called a hypothesis. Seen pictorially(用图表表示), the process is therefore like this:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/H6qTdZmYEeaagxL7xdFKxA_2f0f671110e8f7446bb2b5b2f75a8874_Screenshot-2016-10-23-20.14.58.png?expiry=1544400000000&hmac=6JPRuFVnOfT0f_nz3nfiQ16gs6OYjxo4gsgnwZdl6Lw)

Note: 单变量线性回归模型(univariate linear regression model) is a simplest model.

#### 回归问题（regression problems）

we are trying to predict results within a **continuous(连续的)** output， meaning that we are trying to map input variables to some **continuous function**.

#### 分类问题（classfication problems）

we are instead trying to predict results in a **discreate** output we are trying to map input variables into **discrete categories**.

#### 代价函数（Cost Function）

Training Set:

| Size of feets<sup>2</sup>(x) | Price in 1000's(y) |
| ---------------------------- | ------------------ |
| 2014                         | 460                |
| 1416                         | 232                |
| 1534                         | 315                |
| 852                          | 178                |

´
total M = 47

Parameters:

$${\theta_0},{\theta_1}$$

Hypothesis:

$$h_\theta(x) = \theta_0 + \theta_1 x$$

**Cost Function(Squared error cost fucntion): measure the accuracy(准确性) of our hypothesis function**

$$J({\theta_0}, {\theta_1}) = \frac{1}{2m}\sum_{i=1}^m{(\tilde{y_i} -{y_i})}^2 = \frac{1}{2m}\sum_{i=1}^m{(h_\theta{(x_i)}-{y_i})}^2$$

Gradient descent alorithm:

repeat until convergence {

$${\theta_0} = {\theta_0} - \frac{\partial}{\partial\theta_0}J({\theta_0},{\theta_1}) = {\theta_0} - {\frac{1}{m}\sum_{i=1}^m(h_\theta(x^{(i)})-y^{(i)})}$$

$${\theta_1} = {\theta_1} - \frac{\partial}{\partial\theta_1}J({\theta_0},{\theta_1}) = {\theta_1} - {\frac{1}{m}\sum_{i=1}^m(h_\theta((x^{(i)})-y^{(i)}){x^{(1)}})}$$

}

### 无监督学习（unsupervised learning）

Unsuprvised learning allows us to approach problems with little or no idea what our results should look like. We can derive(推导) structure from data where we don't necessery know the effect of the varibles.

We can derive strcture by clustering(聚类) the data baseed on relationships among the viribles in the data.

## Week 2

### Muticariate Linear Regression（多元线性回归）


| Symbol          | Meaning                                          |
| --------------- | ------------------------------------------------ |
| n               | number of features                               |
| ${x^{(i)}}$     | input (features) of $i^{th}$ training example    |
| ${x^{(i)}_{j}}$ | value of feature `j` in $i{th}$ training exmaple |

#### mutivariable hypothesis function

Hypothesis:

$$
h(x) = \begin{bmatrix}
{\theta_0} & {\theta_1} & \cdots & {\theta_n} 
\end{bmatrix}^T
\begin{bmatrix}
x_{0} & x_{1} & \cdots & x_{n}
\end{bmatrix} = {\theta}^T{x}
$$

Cost Function:

$$J({\theta}) = \frac{1}{2m}\sum_{i=1}^m{(h_\theta{(x_i)}-{y_i})}^2$$

Gradient descent alorithm:

repeat until convergence {

$$
{\theta_0} = {\theta_0} - \frac{\partial}{\partial\theta_0}J({\theta})
$$

$$
{\theta_j} = {\theta_j} - \frac{\partial}{\partial\theta_j}J({\theta}) 
$$

(simultaneously update ${\theta_0}, {\theta_j}$)

}

### Gradient Descend in Practice

#### Feature Scalling

$${x_i} = \frac{x_i - \mu_i}{s_i}$$

$\mu_i$ is the **average** of all the values for feature(i) and $s_i$ is standard deviation(max - min).

#### Learning Rate

#### Feature and Polynomial Regression


### Normal Equation(正规方程)

$${\theta} = ({X^T}{X})^{-1}{X^T}{y}$$

```Octave
pinv(X'*X)*X'*y
```

## Week 3 Classification and Representation

### Logistic Regression Model

$$
Cost(h_{\theta}(x),y) = -ylog(h_{\theta}(x)) - (1-y)log(1-h_{\theta}(x))
$$

$$
h = g(X{\theta})
$$

$$
J({\theta}) =  -\frac{1}{m}\left[\sum_{i=1}^{m}y^{(i)}log(h_{\theta}(x^{(i)})) + (1 - y^{(i)})log(1-h_{\theta}(x^{(i)}))\right] + \frac{\lambda}{2m}\sum_{j = 1}^{n}{\theta}^2_{j}
$$

$$
J({\theta})= \frac{1}{m} \cdot ({-y^T}log(h) - {(1-y)^T}log(1-h))
$$

## Week 4 && Week 5 Neural Networks
$
(h_{\Theta}(x)\in\mathbb{R}) 
$

$
(h_{\Theta(x)})_i = i^{th} $  output


$$
J({\Theta}) = -\frac{1}{m}\left[\sum_{i=1}^{m}\sum_{k=1}^{K}y^{(i)}_{k}log(h_{\Theta}(x^{(i)}))_k + (1 - y^{(i)}_k)log(1-(h_{\Theta}(x^{(i)}))_k)\right] + \frac{\lambda}{2m}\sum_{l=1}^{L-1}\sum_{i=1}^{s_l}\sum_{j=1}^{s_l+1}({\Theta}_{ji}^{(i)})^{2}
$$