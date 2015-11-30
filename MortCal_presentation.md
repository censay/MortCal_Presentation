Mortgage Calculator
========================================================
author: GE
date: 11/19/2015

Sales pitch

What is this application?
========================================================

The mortgage calculator is designed to help home buyers
predict how much their mortgage payment will be based on
three variables

- Loan Size ($)
- Annual Percentage Rate (APR %)
- Term (in years)

How does it work?
========================================================

Normally we don't give away the secret sauce recipe, but
you seem like an eager investor so we'll make an exception

We take both the yearly term and the APR and convert them to their monthly equivalents.  We then use an equation to calculate the payment.


```r
payments  <- function(loan, apr, years) {
    months <- years * 12
    rate <- 1 + apr / 100 / 12
    loan * rate^months * (rate - 1) / (rate^months - 1)
}
```



Examples of output
========================================================

We interactively display the result to the user allowing them to decrease or increase each quantity interactively.  The server call performs the calculation


```r
# $200,000 loan at 4% APR for 30 years
payments(200000,4.0,30)
```

```
[1] 954.8306
```

```r
# $400,000 loan at 4% APR for 30 years
payments(400000,4.0,30)
```

```
[1] 1909.661
```


Who is the market
========================================================

There are three main consumers that can benefit from this application.

- Real Estate Agents
- Loan Officers
- Home Buyers

The first two markets can purchase the application and provide it to home buyers as a value added service.

Home buyers can purchase the application and bookmark the URL to be used when looking at listings in order to predict the cost.
