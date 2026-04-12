# 1. Random Walk

[ Source:
1.  **Marco Peixeiro**'s book **Time Series Forecasting in Python**
2. My college notes

Code source: https://github.com/marcopeix/TimeSeriesForecastingInPython/tree/master/CH03 <br>
]

## White Noise / Purely Random Process

A discrete time stochastic process is called a **White Noise** or a **Purely Random Process** if it consists of a sequence of random variables $\epsilon_t$ which have a constant mean, constant variance and are uncorrelated. Which means,

- $\mathbb{E}[\epsilon_t] = 0$  
- $\mathrm{Var}(\epsilon_t) = \sigma^2$  
- $\mathrm{Cov}(\epsilon_t, \epsilon_{t+k}) = 0 \quad \forall k \ne 0$ 

Some authors make a stronger assumption that $\epsilon_t$ is a white noise process if $\epsilon_t$'s are i.i.d (identical and independently distributed). <br>
It is further assumed that $\epsilon_t$'s are n**ormally distributed**. 

$$
\epsilon_t \sim  \mathcal{N}(0, \sigma^2)
$$



## Random Walk

A random walk is defined as:

$$
y_t = C + y_{t-1} + \epsilon_t
$$

Where:
- $y_t$: value at time $t$  
- $C$: constant (drift)  
- $y_{t-1}$: previous value  
- $\epsilon_t$: white noise  

Note that if the constant $C$ is nonzero, we designate this process as a random walk with drift.

