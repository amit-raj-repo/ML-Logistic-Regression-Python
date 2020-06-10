# ML-Logistic-Regression-Python

To understand Logistic Regression, we need to understand the concept of Maximum likelihood. Following steps will help us in doing that.

## Maximum Likelihood

***Step-1***

Suppose we have a distribution of weights i.e. mouse weights

<p align="center">
<img src=https://github.com/amit-raj-repo/ML-Logistic-Regression-Python/blob/master/Resources/mxl-1.png width=550 height=200>
</p>

***Step-2***

We need to find the normal distribution curve which will fit best on this data, for this we need optimum values of mu and sigma

<p align="center">
<img src=https://www.thoughtco.com/thmb/pYkVzv3wJGeULFip-z1t75557WA=/1500x1124/filters:no_upscale():max_bytes(150000):strip_icc()/bellformula-56b749555f9b5829f8380dc8.jpg width=200 height=150>
</p>

***Step-3***

- We then try out various values of mean so that the weights are closest to the mean and gives maximum likelihood while doing this, we fix sigma to any value and not chnge it
- Once we get the optimum value of mean i.e. mu then we switch to sigma and vary sigma to finalize of curve's spread to get max likelihood value during this time the mean stays fixed to the optimum value obtained in previous step
- There is a catch here, we have n number of observations here so to calculate max likelihood, we calculate max likelihood for individual samples and multiply them together
- Finally we get our optimum values of mean and sd using which we can best fit our data to normal distribution

<p align="center">
<img src=https://github.com/amit-raj-repo/ML-Logistic-Regression-Python/blob/master/Resources/mxl-2.png width=400 height=200>
</p>

## Logistic Regression

<p align="center">
<img src=https://www.equiskill.com/wp-content/uploads/2018/07/WhatsApp-Image-2020-02-11-at-8.30.11-PM.jpeg width=500 height=300>
</p>

- On the left side of the image we have our base data, we can have n number of variables in the data, just imagine an N dimension graph and all our data points plotted there.

- Logistic regression uses a logit function which is used to calculate probabilities given a set of values for the variables. The graph with the formula of logit function is given below.

<p align="center">
<img src=https://qph.fs.quoracdn.net/main-qimg-7c9b7670c90b286160a88cb599d1b733 width=500 height=300>
</p> 

- To get the best fitting curve of logit function, we need to follow a bunch of steps
  - First being converting the y axis with probability to log odds using the formula: 
        Log odds = Log(p/1-p)
  - Once the probability is converted to log odds, the y axis ranges from -infinity(former 0) to + infinity(former 1)
  
  <p align="center">
  <img src=https://github.com/amit-raj-repo/ML-Logistic-Regression-Python/blob/master/Resources/mxl-3.png width=250 height=250>
  </p>
  
  - We now select a random line to start with and then project the points on the line
  <p align="center">
  <img src=https://github.com/amit-raj-repo/ML-Logistic-Regression-Python/blob/master/Resources/mxl-4.png width=250 height=250>
  </p>
  - From the step above, we have the log odds for each point, we now use the following formula to calculate the probability:
                           Probability =  e^(log odds)/ 1 + e^(log odds)
                           
- We now calculate the likelihood for each point, which is nothing but the probability value for all 1s and 1-p value for all 0s, we have seen earlier that to calculate the final likelihood value we multiplied the values but here, we calculate log likelihood which is nothing but sum of log of likelihood values 
  <p align="center">
  <img src=https://github.com/amit-raj-repo/ML-Logistic-Regression-Python/blob/master/Resources/mxl-5.png width=450 height=80>
  </p>
 
- Now the algorithm rotates the line in such a way that it increases the value of log likelihood. We continue the above steps till we get the best fit squiggle/ maximum log likelihood
