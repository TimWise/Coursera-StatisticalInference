# An Exercise in the Central Limit Theorem
Tim Wise  
February 21, 2015  

### Overview

This is an exercise in the Central Limit Theorem (CLT) where we investigate the distribution of the average of exponential numbers. 

For our purposes, the important points of the CLT are as follows [...]: 

- Consider a population of random numbers from any distribution with mean $\mu$ and variance $\sigma^2$  
- The average of $n$ random draws from this population is itself a random variable. This variable is commonly symbolized as $\bar X_n$  
- The mean of that random variable is the population mean, that is $E[\bar X_n] = \mu$  
- The variance of that random variable is $Var(\bar X_n) = \sigma^2/n$
- The distribution of $\bar X_n$ is approximately standard normal, $N(\mu,\sigma^2/n)$

In this exercise:  

- We start with a population of random numbers from the exponential distribution
- Our $\bar X_n$, which we will call $Z$, is going to be the average of 40 random exponential numbers
- We generate 1000 values for $Z$ 
- We look at the distribution of $Z$, its sample mean and variance
- We compare those to the theoretical values given to us by the CLT
- We show that $Z$ is normally distributed

### Simulations

In this section, we create a random variable, $Z$, whose value is the average of 40 numbers drawn from an exponential distribution. We generate 1000 values for $Z$. It is the distribution of these values that we are interested in.

####  The exponential distribution

The exponential distribution is simulated in R with *rexp(n, lambda)* function where $n$ is the number of exponentials to generate and $lambda$ is the rate parameter (e.g., 35 web hits per minute). The mean and standard deviation of the exponential distribution are both $1/lambda$. 

For this analysis, we'll use $lambda = 0.2$. Let's set $lambda$ and compute the mean, $mu$, and the standard deviation, $sigma$:

```r
lambda <- 0.2
mu <- 1 / lambda
sigma <- 1 / lambda
c(lambda, mu, sigma)
```

```
## [1] 0.2 5.0 5.0
```

Just for grins, let's look at the shape of an exponential distribution with a mean of 5:

```r
hist(rexp(n=1000, rate=1/5))
```

![](StatInf_P1_ASimulationExercise_files/figure-html/unnamed-chunk-2-1.png) 

We see it's a highly skewed distribution, with most of the weight below the mean and a long tail extending above the mean. It looks most un-normal.

#### Random variable Z, the average of 40 exponential numbers 

Now, we generate the average of 40 random exponential numbers 1000 times. We store those values in a vector $Z$, which is our random variable of interest:

```r
set.seed(123456789)
n <- 40
Z <- NULL
for (i in 1:1000) { Z <- c(Z, mean(rexp(n, lambda))) }
str(Z)
```

```
##  num [1:1000] 4.43 4.4 4.6 3.25 3.95 ...
```

### Sample Mean vs Theoretical Mean

The CLT states **the distribution of averages** of independent identically distributed (iid) variables **is normally distributed around the population mean**[...].

For our example, that implies the values of Z should be distributed around the mean of our exponential distribution, $mu=5$. Let's see if that's true. 

First, let's visualize $Z$, looking at the distribution of values: 

```r
hist(Z)
```

![](StatInf_P1_ASimulationExercise_files/figure-html/unnamed-chunk-4-1.png) 

The distribution of $Z$, shown in the histogram above, looks centered around $5$.

The CLT says that the theorectical mean of Z is $mu$.. So, let's compute the sample mean of Z and compare with mu:

```r
round(c(mu, mean(Z)), 2)
```

```
## [1] 5.00 5.01
```
We can see that the two compare very closely.

### Sample Variance versus Theoretical Variance 

The CLT implies the variance of $Z$ is $\sigma^2/n$

Let's compare the theoretical variance of Z to the sample variance:


```r
round(c(sigma^2/n, var(Z)), 2)
```

```
## [1] 0.62 0.60
```
These two compare closly also.

### Distribution of Z is normal

