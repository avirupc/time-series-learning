## 2. Moving Average (MA) Process

A discrete-time stochastic process is called a **Moving Average (MA) process** if the current value of the series is expressed as a linear combination of current and past white noise terms.

An MA process of order $q$, denoted as **MA($q$)**, is defined as:

$$
y_t = \mu + \epsilon_t + \theta_1 \epsilon_{t-1} + \theta_2 \epsilon_{t-2} + \cdots + \theta_q \epsilon_{t-q}
$$

Where:
- $y_t$: value at time $t$  
- $\mu$: constant mean of the process  
- $\epsilon_t$: white noise process  
- $\theta_1, \theta_2, \ldots, \theta_q$: parameters of the model  
- $q$: order of the moving average  

### Assumptions

- $\mathbb{E}[\epsilon_t] = 0$  
- $\mathrm{Var}(\epsilon_t) = \sigma^2$  
- $\mathrm{Cov}(\epsilon_t, \epsilon_{t+k}) = 0 \quad \forall k \ne 0$  

### Key Properties

- The process is **stationary** for all values of $\theta_i$.  
- The mean of the process is:  
  $$\mathbb{E}[y_t] = \mu$$
- The variance depends on the coefficients $\theta_i$:  
  $$\mathrm{Var}(y_t) = \sigma^2 \left(1 + \theta_1^2 + \theta_2^2 + \cdots + \theta_q^2 \right)$$

### MA(1)

A first-order moving average process is given by:

$$
y_t = \mu + \epsilon_t + \theta_1 \epsilon_{t-1}
$$

This is the simplest form of an MA process, where the current value depends only on the current and immediately preceding white noise terms.

For an MA(1) process:

$$
\mathrm{Var}(y_t) = \sigma^2(1+\theta_1^2)
$$

The autocovariance at lag $1$ is:

$$
\gamma_1 = \theta_1\sigma^2
$$

and for lags greater than $1$:

$$
\gamma_k = 0 \quad \text{for } k > 1
$$

Therefore, the theoretical **ACF cuts off after lag 1**.


### MA(2)

Similarly, the second-order moving average process is given by:

$$
y_t = \mu + \epsilon_t + \theta_1 \epsilon_{t-1} + \theta_2 \epsilon_{t-2}
$$

Here, the current value depends on the current white noise term and the previous two white noise terms.

For an MA(2) process:

$$
\mathrm{Var}(y_t) = \sigma^2(1+\theta_1^2+\theta_2^2)
$$

The autocovariance is zero for lags greater than $2$:

$$
\gamma_k = 0 \quad \text{for } k > 2
$$

Therefore, the **ACF cuts off after lag 2**.

### General MA(q)

The key property of an MA($q$) process is:

$$
\gamma_k = 0 \quad \text{for } k > q
$$

Thus, the theoretical **ACF of an MA($q$) process cuts off after lag $q$**.

This provides an important way to identify an MA process and determine its order.

### How to Identify an MA Process?

The main tool used to identify an MA process is the **Autocorrelation Function (ACF)**.

For an MA($q$) process:

$$
\rho_k = 0 \quad \text{for } k > q
$$

Therefore, if the sample ACF shows significant autocorrelations up to a particular lag and then becomes statistically insignificant, an MA model may be appropriate.

For example:

* ACF cuts off after lag $1$ $\rightarrow$ possible **MA(1)**
* ACF cuts off after lag $2$ $\rightarrow$ possible **MA(2)**
* ACF cuts off after lag $q$ $\rightarrow$ possible **MA($q$)**



### Identifying the Lag Order

The lag order $q$ can be estimated by examining where the ACF cuts off.

For example, suppose the ACF looks approximately like:

$$
\rho_1 \neq 0,\qquad
\rho_2 \neq 0,\qquad
\rho_3 \approx 0,\qquad
\rho_4 \approx 0,\ldots
$$

Then an **MA(2)** model is a reasonable candidate because the ACF cuts off after lag $2$.

In practice, the ACF values are compared with their confidence intervals. Lags whose ACF values are statistically insignificant are treated as approximately zero.

## Exercise 
These concepts will be explored more elaborately through [practical exercises](./2.%20Exercise.ipynb) from Chapter 4.4 of **Marco Peixeiro**'s book **Time Series Forecasting in Python**.