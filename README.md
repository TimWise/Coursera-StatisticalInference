### Published Reports

- [An Exercise in the Central Limit Theorem]("http://rpubs.com/timwise/161361")
- [A Summary of the Tooth Growth Data Set](http://rpubs.com/timwise/178927)

### Project 1: A Simulation Exercise

The exponential distribution can be simulated in R with rexp(n, lambda) where lambda is the rate parameter. The mean of exponential distribution is 1/lambda and the standard deviation is also also 1/lambda.Set lambda = 0.2 for all of the simulations. In this simulation, you will investigate the distribution of averages of 40 exponential(0.2)s. Note that you will need to do a thousand or so simulated averages of 40 exponentials.

Illustrate via simulation and associated explanatory text the properties of the distribution of the mean of 40 exponential(0.2)s.  You should
1. Show where the distribution is centered at and compare it to the theoretical center of the distribution.
2. Show how variable it is and compare it to the theoretical variance of the distribution.
3. Show that the distribution is approximately normal.

Note that for point 3, focus on the difference between the distribution of a large collection of random exponentials and the distribution of a large collection of averages of 40 exponentials. 

### Project 2: Analyze the ToothGrowth data 

Analyze the ToothGrowth data in the R datasets package. 

1.	Load the ToothGrowth data and perform some basic exploratory data analyses 
2.	Provide a basic summary of the data.  
3.	Use confidence intervals and/or hypothesis tests to compare tooth growth by supp and dose. (Only use the techniques from class, even if there's other approaches worth considering)  
4.	State your conclusions and the assumptions needed for your conclusions.  

Some criteria that you will be evaluated on

- Did you  perform an exploratory data analysis of at least a single plot or table highlighting basic features of the data?  
- Did you perform some relevant confidence intervals and/or tests?  
- Were the results of the tests and/or intervals interpreted in the context of the problem correctly?   
- Did you describe the assumptions needed for their conclusions?
 