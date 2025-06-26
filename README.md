# Simulating Asset Prices using Geometric Brownian Motion, Black-Scholes & Monte Carlo

This project demonstrates core techniques in quantitative finance by:
1. Simulating stock-price paths via Geometric Brownian Motion (GBM)  
2. Pricing European options analytically with Black-Scholes–Merton (BSM)  
3. Estimating option values via Monte Carlo simulation  
4. Visualizing results   

---

## Overview

We’ll generate multiple stock-price trajectories, compute option prices both analytically and by simulation, then show how volatility and randomness affect option value.

---

## Objectives

- Simulate 50–100 GBM price paths  
- Compute call/put prices using Black-Scholes  
- Estimate the same via Monte Carlo  
- Visualize and save plots of:  
  - GBM paths  
  - Option price vs. volatility  

---

## Tools & Technologies

| Concept                      | Python Library / Function        |
| ---------------------------- | -------------------------------- |
| GBM simulation               | numpy                            |
| Analytical option pricing    | scipy.stats.norm, math           |
| Monte Carlo pricing          | numpy.random.normal()            |
| Plotting                     | matplotlib.pyplot                |
| Development environment      | Anaconda → Jupyter Notebook      |

---

## Financial Background

### Geometric Brownian Motion (GBM)

Models stock-price evolution assuming constant drift & volatility:

$$
S_{t+1} = S_t \cdot \exp\!\Bigl[\bigl(\mu - \tfrac12\sigma^2\bigr)\Delta t + \sigma\sqrt{\Delta t}\;Z\Bigr]
$$

### Black-Scholes–Merton (BSM)

Closed-form for European call price:

$$
C = S\,N(d_1) \;-\; K\,e^{-rT}\,N(d_2)
$$

### Monte Carlo Option Pricing

Estimate option value by simulating many terminal prices, computing payoffs, and discounting:

```python
def monte_carlo_option_price(S0, K, T, r, sigma, M=20000, option_type='call'):
    Z = np.random.normal(size=M)
    ST = S0 * np.exp((r - 0.5*sigma**2)*T + sigma*np.sqrt(T)*Z)
    payoff = np.maximum(ST - K, 0) if option_type=='call' else np.maximum(K - ST, 0)
    return np.exp(-r*T)*np.mean(payoff)

