#  Simulating Asset Prices using Geometric Brownian Motion and the Black-Scholes Model

This project demonstrates key techniques in **quantitative finance** by combining **stochastic simulation** with **analytical option pricing**.

---

##  Overview

We simulate asset price paths using **Geometric Brownian Motion (GBM)** and compute the theoretical values of European call and put options using the **Black-Scholes-Merton (BSM)** formula.

This compact project mirrors real techniques used in **hedge funds**, **quantitative trading**, and **investment banking**.

---

##  Objectives

- Simulate 50–100 stock price paths using GBM  
- Compute option prices using the Black-Scholes formula  
- Visualize asset paths and option sensitivity to volatility  

---

##  Tools & Technologies

| Concept                  | Python Library/Function      |
| ------------------------ | ---------------------------- |
| GBM simulation           | `numpy`, `matplotlib.pyplot` |
| Option pricing           | `scipy.stats.norm`, `math`   |
| Random number generation | `numpy.random.normal()`      |
| Visualization            | `matplotlib`                 |
| Development format       | Jupyter Notebook `.ipynb`    |

---

##  Key Features

-  GBM simulation implemented from scratch  
-  Parameterized Black-Scholes pricing function  
-  Interactive plots of stock price paths and option values  
-  Markdown explanations for readability and sharing  
-  Modular functions for reuse and testing  

---

##  Financial Background

### Geometric Brownian Motion (GBM)

GBM is a continuous-time stochastic process often used to model stock prices:

$$
S_{t+1} = S_t \cdot \exp\left[\left(\mu - \frac{1}{2} \sigma^2\right)\Delta t + \sigma \sqrt{\Delta t} \cdot Z\right]
$$

Where:
- \( S_t \): current stock price  
- \( \mu \): expected return  
- \( \sigma \): volatility  
- \( Z \): standard normal random variable  

---

### Black-Scholes-Merton Model (BSM)

The Black-Scholes model gives a closed-form solution for European option prices:

$$
C = S \cdot N(d_1) - K \cdot e^{-rT} \cdot N(d_2)
$$

Where:
- \( C \): call option price  
- \( S \): current price  
- \( K \): strike price  
- \( T \): time to maturity  
- \( r \): risk-free rate  
- \( \sigma \): volatility  
- \( N() \): cumulative standard normal distribution  
