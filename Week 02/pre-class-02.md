# pre-class


Make sure you commit this often with meaningfull messages. 

### Background

The exponential distribution is defined by its cumulative distribution function
\(F(x) = 1-e^{-\lambda x}\)

The R function ***rexp()*** generates random variables with an exponential distribution. For example 
<center><strong>rexp(n=10, rate=5)</strong> </center>

results in 10 exponentially distributed numbers with a rate \(\lambda=5\). If you leave out the 5 and just have
<center><strong>rexp(n=10) </strong></center>
then this results in 10 exponentially distributed numbers with a rate \(\lambda=1\), this is also referred to as the "standard exponential distribution". 

### Part 1


1. Generate 200 random values from the standard exponential distribution and store them in a vector `exp.draws.1`.  Find the mean and standard deviation of `exp.draws.1`.

``` {r}
exp.draws.1 <- rexp(200)
mean_exp.draws.1 <- mean(exp.draws.1)
sd_exp.draws.1 <- sd(exp.draws.1)
```

2. Repeat, but change the rate to 0.2, 5, 7.3 and 10, storing the results in vectors called  `exp.draws.0.2`,  `exp.draws.5`,  `exp.draws.7.3` and  `exp.draws.10`. 

``` {r}
exp.draws.0.2 <- rexp(200, rate = 0.2)
mean_exp.draws.0.2 <- mean(exp.draws.0.2)
sd_exp.draws.0.2 <- sd(exp.draws.0.2)

exp.draws.5 <- rexp(200, rate = 5)
mean_exp.draws.5 <- mean(exp.draws.5)
sd_exp.draws.5 <- sd(exp.draws.5)

exp.draws.7.3 <- rexp(200, rate = 7.3)
mean_exp.draws.7.3 <- mean(exp.draws.7.3)
sd_exp.draws.7.3 <- sd(exp.draws.7.3)

exp.draws.10 <- rexp(200, rate = 10)
mean_exp.draws.10 <- mean(exp.draws.10)
sd_exp.draws.10 <- sd(exp.draws.10)
```

3. The function `plot()` is the generic function in R for the visual display of data. `hist()` is a function that takes in and bins data as a side effect. To use this function, we must first specify what we'd like to plot.
    a. Use the `hist()` function to produce a histogram of your standard exponential distribution. 
    
``` {r}    
 hist(exp.draws.1)
```    
    b. Use `plot()` with this vector to display the random values from your standard distribution in order.
    
```{r}    
  plot(exp.draws.1) 
```
    c. Now, use `plot()` with two arguments -- any two of your other stored random value vectors -- to create a scatterplot of the two vectors against each other.
    
``` {r}    
  plot(exp.draws.1, exp.draws.5)  
```

4. We'd now like to compare the properties of each of our vectors. Begin by creating a vector of the means of each of our five distributions in the order we created them and saving this to a variable name of your choice. Using this and other similar vectors, create the following scatterplots and explain in words what is going on:

```{r}
vector_means <- c(mean_exp.draws.1, mean_exp.draws.0.2, mean_exp.draws.5, mean_exp.draws.7.3, mean_exp.draws.10)
```

  a. The five means versus the five rates used to generate the distribution.
  
```{r}  
rates <- c(1, 0.2, 5, 7.3, 10)
plot(rates, vector_means)
  
Explanation: When the rate is low at the value of 0.2, the value of the mean is high. Increasing the rate causes a dramatic decrease in the mean, so a significant inverse relationship is found. As the rates increase to 5, to 7.3, to 10, it is clear that the mean is approaching 0.
```  
  
    b. The standard deviations versus the rates.
    
```{r}    
 vector_sds <- c(sd_exp.draws.1, sd_exp.draws.0.2, sd_exp.draws.5, sd_exp.draws.7.3, sd_exp.draws.10)
 plot(rates, vector_sds)
 
 The relationship here strikingly appears to be similar to the relationship I found in part 4a. When the rate is at a low level, the Standard Deviation is quite high. As the rate increases, the Standard Deviation shoots downward very quickly, expressing a clear negative relationship.
```

    c. The means versus the standard deviations.
```{r}
plot(vector_means, vector_sds)

The plot in 4c differs from parts 4a and 4b. Instead of a negative, inverse relationship, there appears to be a linear, positive relationship. As the mean increases, so, too, does the standard deviation.
```
For each plot, explain in words what's going on.

