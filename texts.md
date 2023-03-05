
### One sample t-test: How many SEM units is our estimate from 100?
\[ t = \frac{\bar{x}-\mu}{SEM} \]
where 
- t is the value of the one-sample t—test 
- x bar is the mean of the sample (here 108.1) 
- μ is the number to be compared with (hypothetical mean*) (here, 100) 
- SEM is the standard error of the mean (here, 3.37) 
    - so t = 2.4, in other words, our sample is 2.4 SEM units from the hypothetical mean.

### Is 2.4 units good enough?

- Manually: consult the t table based on the degree of freedom (d.f. = n-1 = 20-1 = 19).
- At alpha = 0.05, our t value is greater than the critical t value (2.4 > 2.093).
- Thus, we reject H0, and say that uni A’s students have significantly different IQ than 100. (And because 108.1 > 100, we say it’s higher than 100.)

![ttable](/images/week3/ttable.png)

### Do it in R

1. Prepare data

```{r}
a = c(117, 125, 116, 113, 102, 122, 123, 93, 99, 129, 132, 94, 85, 92, 101, 83, 119, 119, 101, 97)
```

2. Test for normality

```{r}
shapiro.test(a)
```

p > 0.05 means data is not significantly different from normal distribution, which is what we want.

3. Run the test

```{r}
t.test(a, mu=100)
```

```
> t.test(a, mu=100)

	One Sample t-test

data:  a
t = 2.4063, df = 19, p-value = 0.02646
alternative hypothesis: true mean is not equal to 100
95 percent confidence interval:
 101.0545 115.1455
sample estimates:
mean of x 
    108.1
```




### Reporting statistics 

Statistical tests need to be reported once the data have been analysed (usually in a short paragraph) 

### Basic framework for the reporting:

- Statistical test that was performed 
- The measures that were compared (with the different levels if there are any) 
- The means and standard deviations
- Significant or non-significant? 
- Specific test value – in this case the t-statistic (in later weeks, the F-value, X², r) 
- Degrees of freedom – convention dictates that these are placed in rounded parentheses 
- The specific p-value taken from R
- (confidence intervals/effect size) 
