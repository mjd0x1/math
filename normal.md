# Normal Distribution

*  Bell shaped cuve X = N(mean,st-dev^2)

*  1 standard deviation 68% of area
   2 standard deviations 95% of area
   3 standard deviations 99.97% of area.

* Standard Normal  

```julia
    using Distributions


    #returns area (total probability) under the curve from 
    #point x P(X <= x)
    cdf(Normal(0,1),-0.5244)
    #cumulates to 1
    cdf(Normal(0,1),-3:0.5:3)

    pdf(Normal(0,1),0.1)

    #Inverse Normal,  which value gives area under the curve 30%
    quantile(Normal(0,1),0.3)

```

Any Normal distribution can be transformed to a Standard Normal.  

Normal distribution returns the area under the curve <= the value e.g P(X <= k)

Inverse Normal returns the value k that gives us a specific area (probability)

Z =  (X - m) / sd

So P(X <= k),  transforms to  P( (X-m)/sd <= (X - m) / sd)  
P(Z <= (X - m) / sd)


# Hypothesis Testing

* Binomial Hypothesis Testing.

Let p be the probability of 'something'

H0:  p = k 
H1:  p <> k (two tailed) or p > k,  p < k

m% level of signicance,  compare B(n,p) to m,  if B(n,p) < m then reject null hypothesis and evidence suggests that H1 is true

For two tailed m/2

* Critical Regions 

Generate Cumulative Probabity distribution B(n,p).  Find x values that fall inside the critical region.

* Normal Samples

If N(m,sd^2)  then test  N(m,(sd/n)^2)


# Complex Numbers

* De Moivres theroem   (cos(t)+isin(t))^n  = cos(nt) + isin(nt)

* nth roots of unity

z^3  = 1   =>   cos(3t)+isin(3t) = cos(2*pi*k)+isin(2*pi*k)  
           =>   t  =  2 * pi *k/3  for k = 0,1,2

