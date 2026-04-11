# Random Walk

[ Source:
1.  **Marco Peixeiro**'s book **Time Series Forecasting in Python**
2. My college notes

Code source: https://github.com/marcopeix/TimeSeriesForecastingInPython/tree/master/CH03 <br>
]

## White Noise

White noise is a sequence of independent and identically distributed random variables:

$$
\epsilon_t \sim \mathcal{N}(0, 1)
$$

- $\mathbb{E}[\epsilon_t] = 0$  
- $\mathrm{Var}(\epsilon_t) = 1$  
- $\mathrm{Cov}(\epsilon_t, \epsilon_{t-k}) = 0 \quad \forall k \ne 0$ 



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