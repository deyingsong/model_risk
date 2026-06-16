# Chapter 9 Correlations and Copulas

## Summary

Correlation is only a narrow summary of dependence. Zero correlation does not imply independence, and linear correlation can miss nonlinear, state-dependent, and tail relationships that matter most in stress. Variance-covariance matrices must be internally consistent and positive semi-definite; otherwise portfolio variances, simulations, and risk reports can become mathematically impossible. EWMA and GARCH-style covariance updates should use weighting schemes consistent with volatility estimates. Factor models reduce dimensionality but impose structure that must be validated against economic intuition and empirical behavior.

The daily takeaway is to treat dependence modeling as a core validation topic, not a calibration detail. Check whether correlations rise in stress, whether the matrix is stable and positive semi-definite, and whether simulation methods reproduce intended marginal distributions and joint behavior. Copulas are useful because they separate marginal distributions from dependence, but Gaussian copulas can understate joint tail events. Student's t-copulas or heavy-tailed factor copulas may better capture simultaneous defaults or market moves. For credit portfolios and Vasicek-style models, validate PD, asset correlation, worst-case default rates, tail dependence, and sensitivity to macro factors rather than relying on average default behavior.

## Table of Contents

1. [Summary](#summary)
2. [Definition of correlation](#definition-of-correlation)
   - [correlation vs. dependence](#correlation-vs-dependence)
   - [Monitoring correlation](#monitoring-correlation)
   - [EWMA](#ewma)
   - [GARCH](#garch)
3. [Correlation and covariance matrices](#correlation-and-covariance-matrices)
   - [Consistency condition for covariances](#consistency-condition-for-covariances)
4. [Multivariate normal distributions](#multivariate-normal-distributions)
   - [Generating Random Samples from Multivariate Normal Distributions](#generating-random-samples-from-multivariate-normal-distributions)
   - [Factor models](#factor-models)
5. [Copulas](#copulas)
   - [Expressing the approach algebraically](#expressing-the-approach-algebraically)
   - [Other copulas](#other-copulas)
   - [Tail dependence](#tail-dependence)
   - [Multivariate copulas](#multivariate-copulas)
   - [A factor copula model](#a-factor-copula-model)
6. [Application to Loan Portfolios: Vasicek's Model](#application-to-loan-portfolios-vasiceks-model)
   - [Proof of Vasicek's result](#proof-of-vasiceks-result)
   - [Estimating PD and $\rho$](#estimating-pd-and-rho)
   - [Alternatives to the Gaussian copula](#alternatives-to-the-gaussian-copula)

## Definition of correlation

- The coefficient of correlation, $\rho$, between two variables $V_1$ and $V_2$ is defined by equation 9.1 as $\rho=\frac{E(V_1V_2)-E(V_1)E(V_2)}{SD(V_1)SD(V_2)}$, where $E(\cdot)$ denotes expected value and $SD(\cdot)$ denotes standard deviation, so it measures the covariance between the variables scaled by the product of their standard deviations.
- The covariance between $V_1$ and $V_2$ is defined by equation 9.2 as $\operatorname{cov}(V_1,V_2)=E(V_1V_2)-E(V_1)E(V_2)$, where $E(V_1V_2)$ is the expected product of the two variables and $E(V_1)E(V_2)$ is the product of their expected values, so correlation can be written as $\rho=\frac{\operatorname{cov}(V_1,V_2)}{SD(V_1)SD(V_2)}$.

### correlation vs. dependence

- Two variables are defined as statistically independent if knowledge about one of them does not affect the probability distribution for the other, or formally if $f(V_2\mid V_1=x)=f(V_2)$ for all $x$, where $f(\cdot)$ is the probability density function and $\mid$ denotes “conditional on.”
- A correlation coefficient of zero does not necessarily imply that there is no dependence between the variables, because two variables can be perfectly related in a nonlinear way, such as a symmetric V-shaped relationship, while still satisfying $E(V_1V_2)=0$ and $E(V_1)=0$.
- The coefficient of correlation measures one particular type of dependence between two variables, namely linear dependence, while many other relationships can exist in which the expected value or conditional standard deviation of one variable depends on the other in nonlinear or tail-related ways.

### Monitoring correlation

- The covariance rate per day between two variables $X$ and $Y$ is defined as the covariance between their daily returns $x_i=\frac{X_i-X_{i-1}}{X_{i-1}}$ and $y_i=\frac{Y_i-Y_{i-1}}{Y_{i-1}}$, and under the usual risk-management assumption that expected daily returns are zero it is $\operatorname{cov}_n=E(x_ny_n)$, estimated with equal weights as $\operatorname{cov}_n=\frac{1}{m}\sum_{i=1}^m x_{n-i}y_{n-i}$, where $m$ is the number of past observations.

### EWMA

- In the exponentially weighted moving average model, the covariance estimate is updated as $\operatorname{cov}_n=\lambda\operatorname{cov}_{n-1}+(1-\lambda)x_{n-1}y_{n-1}$, where $\lambda$ is the decay parameter, $\operatorname{cov}_{n-1}$ is yesterday’s covariance estimate, and $x_{n-1}y_{n-1}$ is the most recent observed product of returns, so lower $\lambda$ gives greater weight to recent observations.

### GARCH

- In the GARCH(1,1) model, the covariance rate between $X$ and $Y$ is updated as $\operatorname{cov}_n=\omega+\alpha x_{n-1}y_{n-1}+\beta\operatorname{cov}_{n-1}$, where $\omega$ gives weight to the long-run average covariance, $\alpha$ gives weight to the most recent observed covariance proxy, and $\beta$ gives weight to the previous covariance estimate, with long-term average covariance $\omega/(1-\alpha-\beta)$.

## Correlation and covariance matrices

### Consistency condition for covariances

 - The condition for an $N\times N$ variance-covariance matrix $\Omega$ to be internally consistent is equation 9.4, $w^T\Omega w\ge 0$ for all $N\times1$ vectors $w$, where $w^T$ is the transpose of $w$, and a matrix satisfying this property is known as positive semi-definite.

- A variance-covariance matrix is internally consistent only when its variances and covariances can represent possible joint movements of variables without implying a negative variance for any portfolio or linear combination.
- Equation 9.4 must hold because if $w=(w_1,w_2,\ldots,w_N)^T$, then $w^T\Omega w$ is the variance rate of a portfolio investing amount $w_i$ in market variable $i$, and a variance cannot be negative.
- Variances and covariances should be calculated consistently, so if variance rates are based on equal weights, EWMA, or another method, covariance rates should be calculated using the same weighting scheme to help ensure that the resulting variance-covariance matrix is positive semi-definite.

## Multivariate normal distributions

### Generating Random Samples from Multivariate Normal Distributions

- To generate samples $\varepsilon_1$ and $\varepsilon_2$ from a bivariate standard normal distribution with correlation $\rho$, first obtain independent standard normal samples $z_1$ and $z_2$, then set $\varepsilon_1=z_1$ and $\varepsilon_2=\rho z_1+z_2\sqrt{1-\rho^2}$, where $\rho$ determines the linear correlation induced between the two sampled variables.

- In the Cholesky decomposition for a multivariate normal distribution, independent standard normal samples $z_i$ are transformed into correlated samples $\varepsilon_i=\sum_{k=1}^i\alpha_{ik}z_k$, where the parameters $\alpha_{ik}$ are chosen so that $\sum_{k=1}^i\alpha_{ik}^2=1$ and $\sum_{k=1}^j\alpha_{ik}\alpha_{jk}=\rho_{ij}$ for $j<i$, thereby giving the required variances and correlations.

### Factor models

- In a one-factor model, each standard normal variable $U_i$ is written as $U_i=a_iF+\sqrt{1-a_i^2}Z_i$, where $F$ is the common standard normal factor, $Z_i$ is an idiosyncratic standard normal component uncorrelated with the other $Z$’s and with $F$, and the correlation between $U_i$ and $U_j$ is $a_ia_j$.
    - In the capital asset pricing model example, the return on a stock has a component dependent on the return from the market and an idiosyncratic or nonsystematic component that is independent of the return on other stocks.
- In an $M$-factor model, each standard normal variable is written as $U_i=a_{i1}F_1+a_{i2}F_2+\cdots+a_{iM}F_M+\sqrt{1-a_{i1}^2-a_{i2}^2-\cdots-a_{iM}^2}Z_i$, where the factors $F_1,\ldots,F_M$ and idiosyncratic terms $Z_i$ are uncorrelated standard normal variables and the correlation between $U_i$ and $U_j$ is $\sum_{m=1}^M a_{im}a_{jm}$.

## Copulas

- The marginal distribution of $V_1$, sometimes called the unconditional distribution, is its distribution assuming we know nothing about $V_2$, and similarly the marginal distribution of $V_2$ is its distribution assuming we know nothing about $V_1$.
- Often there is no natural way of defining a correlation structure between two marginal distributions, especially when they are not normal, and copulas provide a way to define a joint distribution while preserving the specified marginal distributions.
- The Gaussian copula maps variables $V_1$ and $V_2$ into standard normal variables $U_1$ and $U_2$, assumes that $U_1$ and $U_2$ are jointly bivariate normal with a chosen copula correlation, and thereby implies a joint distribution and correlation structure for $V_1$ and $V_2$.
    - The percentile-to-percentile mapping sends each percentile point of the distribution of $V_i$ to the same percentile point of the standard normal distribution of $U_i$, so for example the one-percentile point of $V_i$ is mapped to the one-percentile point of $U_i$.
    - Instead of defining a correlation structure between $V_1$ and $V_2$ directly, the copula defines it indirectly by mapping them into variables $U_1$ and $U_2$ that have well-behaved distributions and for which it is easy to define a correlation structure.

### Expressing the approach algebraically

- If $G_1$ and $G_2$ are the cumulative marginal distributions of $V_1$ and $V_2$, the Gaussian copula maps $V_1=v_1$ and $V_2=v_2$ to $U_1=u_1$ and $U_2=u_2$ by $G_1(v_1)=N(u_1)$ and $G_2(v_2)=N(u_2)$, equivalently $u_1=N^{-1}[G_1(v_1)]$, $u_2=N^{-1}[G_2(v_2)]$, $v_1=G_1^{-1}[N(u_1)]$, and $v_2=G_2^{-1}[N(u_2)]$, where $N$ is the cumulative normal distribution function.

### Other copulas

- A Student’s t-copula works in the same way as the Gaussian copula except that $U_1$ and $U_2$ are assumed to have a bivariate Student’s t-distribution rather than a bivariate normal distribution, so sampling with $f$ degrees of freedom and correlation $\rho$ involves sampling $\chi$ from an inverse chi-square distribution, sampling from a bivariate normal distribution with correlation $\rho$, and multiplying the normal samples by $\sqrt{f/\chi}$.

### Tail dependence

- Tail dependence is higher in a bivariate Student’s t-distribution than in a bivariate normal distribution because it is much more common for the two variables to have left- or right-tail values at the same time under the Student’s t-distribution.
- Because correlations between market variables tend to increase in extreme market conditions, some researchers argue that the Student’s t-copula provides a better description of the joint behavior of two market variables than the Gaussian copula.

### Multivariate copulas

- A multivariate copula defines a correlation structure among more than two variables by transforming each variable $V_i$ into a variable $U_i$ with a chosen standard distribution, typically standard normal in a multivariate Gaussian copula, on a percentile-to-percentile basis and then assuming a multivariate distribution for the $U_i$.

### A factor copula model

- In multivariate copula models, analysts often assume a factor model for the correlation structure between the $U_i$, and with one factor this is $U_i=a_iF+\sqrt{1-a_i^2}Z_i$, where $F$ and $Z_i$ have standard normal distributions and the $Z_i$ are uncorrelated with each other and with $F$.

## Application to Loan Portfolios: Vasicek's Model

- Table 9.6 illustrates that annual default rates for all rated companies between 1981 and 2020 vary substantially, from a low of 0.15% in 1981 to a high of 4.19% in 2009, showing that loans do not default independently because they are all influenced by macroeconomic conditions.
- The worst case default rate $WCDR(T,X)$ is the default rate during time $T$ that will not be exceeded with probability $X$, and Vasicek’s model gives $WCDR(T,X)=N\!\left(\frac{N^{-1}(PD)+\sqrt{\rho}N^{-1}(X)}{\sqrt{1-\rho}}\right)$, where $PD=\operatorname{Prob}(T_i<T)$, $\rho$ is the copula correlation, and $N$ and $N^{-1}$ are the cumulative normal and inverse cumulative normal distribution functions.

### Proof of Vasicek's result

- Vasicek’s result follows by mapping each time to default $T_i$ to $U_i$, writing $U_i=\sqrt{\rho}F+\sqrt{1-\rho}Z_i$, setting $U=N^{-1}(PD)$, deriving $\operatorname{Prob}(T_i<T\mid F)=N\!\left(\frac{N^{-1}(PD)-\sqrt{\rho}F}{\sqrt{1-\rho}}\right)$, and substituting the factor percentile $F=N^{-1}(1-X)=-N^{-1}(X)$ to obtain the default rate not exceeded with probability $X$.

### Estimating PD and $\rho$

- Maximum likelihood estimation chooses trial values for $PD$ and $\rho$, calculates the logarithm of the default-rate density $g(DR)=\sqrt{\frac{1-\rho}{\rho}}\exp\!\left\{\frac{1}{2}\left[(N^{-1}(DR))^2-\left(\frac{\sqrt{1-\rho}N^{-1}(DR)-N^{-1}(PD)}{\sqrt{\rho}}\right)^2\right]\right\}$ for each observed default rate $DR$, and searches for the values maximizing the sum of the log densities.

### Alternatives to the Gaussian copula

- Alternatives to the one-factor Gaussian copula use heavier-tailed distributions for $F$, $Z_i$, or both, scaled to mean zero and standard deviation one, so that $WCDR(T,X)=\Phi\!\left(\frac{\Psi^{-1}(PD)+\sqrt{\rho}\Theta^{-1}(X)}{\sqrt{1-\rho}}\right)$, where $\Phi$, $\Theta$, and $\Psi$ are the cumulative distributions of $Z_i$, $F$, and $U_i$, respectively, and the model can generate more tail dependence and fit default data better.

