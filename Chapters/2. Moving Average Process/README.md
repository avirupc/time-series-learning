## Moving Average (MA) Process

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
  $$
  \mathbb{E}[y_t] = \mu
  $$
- The variance depends on the coefficients $\theta_i$:  
  $$
  \mathrm{Var}(y_t) = \sigma^2 \left(1 + \theta_1^2 + \theta_2^2 + \cdots + \theta_q^2 \right)
  $$

### Special Case: MA(1)

A first-order moving average process is given by:

$$
y_t = \mu + \epsilon_t + \theta_1 \epsilon_{t-1}
$$

This is the simplest form of an MA process, where the current value depends only on the current and immediately preceding white noise terms.