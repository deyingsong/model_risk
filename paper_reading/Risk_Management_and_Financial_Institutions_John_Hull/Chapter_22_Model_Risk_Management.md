# Chapter 22 Model Risk Management

## Table of Contents

1. [Regulatory guidance](#regulatory-guidance)
2. [Models in physics and finance](#models-in-physics-and-finance)
3. [Simple models: expensive mistakes](#simple-models-expensive-mistakes)
    - [Monitoring trading patterns](#monitoring-trading-patterns)
4. [Models for pricing actively traded products](#models-for-pricing-actively-traded-products)
    - [Sources of model risk for actively traded products](#sources-of-model-risk-for-actively-traded-products)
    - [Hedging](#hedging)
    - [P&L decomposition](#pl-decomposition)
5. [Models for Less Actively Traded Products](#models-for-less-actively-traded-products)
    - [Weighted Monte Carlo simulation](#weighted-monte-carlo-simulation)
6. [Accounting](#accounting)
7. [What Makes a Successful Pricing Model?](#what-makes-a-successful-pricing-model)
8. [Model-Building Missteps](#model-building-missteps)


## Regulatory guidance

SR 11-7 defines model risk as the potential for adverse consequences from decisions based on incorrect or misused model outputs and reports, and expects financial institutions to develop, document, validate, monitor, and use models within a systematic model risk management framework.

## Models in physics and finance

Models in physics describe physical processes and are **highly accurate with generally stable parameters**, whereas models in finance describe market variables, customers, borrowers, and other human-driven phenomena, so **they are at best approximate and their parameters often change daily**.

## Simple models: expensive mistakes

Models do not have to be highly complex to lead to losses, because even simple valuation assumptions can be wrong, ignored, or exploited when model prices are not checked against economic reality and market behavior.

1. Kidder Peabody’s system reported Joseph Jett’s strip-forward trades as profitable by *treating the excess of the forward price over the spot price as profit*, although that difference merely represented funding costs and the true position produced a large loss.
2. Many market participants wrongly *assumed that the futures rate in an interest rate futures contract was the same as the corresponding forward rate*, even though daily settlement and the different timing of settlement for futures and forwards make this approximation invalid for interest rate futures.

### Monitoring trading patterns

Monitoring trading patterns is an important way for a financial institution to identify valuation model risk before a model weakness produces large losses.

1. The risk management function should keep track of 
    - the type of trading done with other financial institutions, 
    - how competitive the institution is in bidding for structured transactions, and 
    - the profits being recorded from different products, because too much business or unusually large profits from simple strategies can be warning signs.

## Models for pricing actively traded products

For actively traded products, the market provides the price, and models are mainly used to ensure consistent pricing across similar instruments whose exact strike prices, maturities, or other parameters differ from traded instruments.

1. A common situation where a financial instrument that has to be valued is a standard product such as an option, but not exactly the same as one that trades in the market. In the over-the-counter market, a model is used as a tool to ensure that an instrument such as an option with a different strike price or time to maturity is priced consistently with observed market prices of other similar instruments.
2. The **Black–Scholes–Merton model** is successful in this setting because all inputs except volatility are known with a high degree of certainty, so implied volatilities from traded options form a volatility surface that traders can interpolate to value related options.

### Sources of model risk for actively traded products

For actively traded products, valuation model risk is usually small when the product is standard and similar to traded instruments, but it can become important when market data are sparse, unreliable, or extreme.

1. **whether the prices determined for actively traded instruments depend on the model used**: The validation group should ask whether replacing one model with another would materially change prices, and for standard instruments that differ only in parameters such as strike price or time to maturity the model usually acts only as a sophisticated interpolation tool.
2. **There is liable to be model risk in extreme situations**: Model risk is liable to arise in extreme situations, so the validation group should test models when the volatility surface is very steep, when market pricing data are less reliable, and when fewer data than usual are available.

### Hedging

For actively traded instruments, the main model risk often concerns hedging rather than pricing, because different models may produce similar prices but different hedge positions.

1. **Within-model hedging** deals with risks in variables that the model assumes are uncertain, such as delta and gamma hedging against underlying stock price movements in the Black–Scholes–Merton model.
2. **Outside-model hedging** deals with risks in variables that the model assumes are constant or deterministic, such as vega hedging against volatility changes in the Black–Scholes–Merton model.
3. In practice, **traders often perform only regular delta hedging** because hedging volatility changes requires trades in other options, can be expensive, and depends on assumptions about how the volatility surface changes through time.

### P&L decomposition

P&L decomposition is used to understand whether day-to-day portfolio value changes come from unhedged risks, imperfect hedging models, or trading activity.

1. Risk managers divide day-to-day changes in portfolio value into 
    - changes resulting from risks that were unhedged, 
    - changes resulting from the hedging model being imperfect, and 
    - changes resulting from new trades done during the day.

## Models for Less Actively Traded Products

For less actively traded products, models are more important and more dangerous because the chosen model can significantly affect both valuation and hedging.

1. Here the model used is **likely to have a significant effect on valuations as well as on hedging**. For non-standard instruments, the calibrating instruments are somewhat different from the product being valued, so the model chosen can materially affect valuations as well as hedging.
2. **A financial institution should not rely on a single model**. A financial institution should use several different models whenever possible to obtain a price range and a better understanding of the model risks being taken.

### Weighted Monte Carlo simulation

Weighted Monte Carlo simulation is a sophisticated way to explore the range of prices consistent with models that correctly price actively traded standard instruments.

1. When different models are being used, they should be **calibrated to the observed prices of actively traded standard products**, so each tested model prices comparable market instruments correctly.
2. Weighted Monte Carlo simulation **carries out a Monte Carlo simulation for one model and then applies path weights constrained to reproduce standard instrument prices**, using optimization to find maximum and minimum values for the non-standard derivative consistent with those constraints.

## Accounting

Accounting distinguishes the reliability of fair-value measurements according to whether prices come directly from active markets, similar market instruments, or models requiring assumptions.

1. **Marking to market** is the daily valuation of trading-book products, which accountants refer to as **fair-value accounting**.
2. **three categories of valuations**: 
    - Level 1 valuations use quoted prices in active markets, 
    - Level 2 valuations use quoted prices for similar instruments or inactive markets, and 
    - Level 3 valuations require modeling assumptions and are sometimes called marking to model.

## What Makes a Successful Pricing Model?

A successful pricing model helps users understand the market and exercise judgment efficiently, even when its parameters change from day to day.

1. The Black–Scholes–Merton model is popular because 
    - it works as an interpolation tool with the volatility surface, 
    - serves as a communication tool through implied volatilities, and 
    - is simple enough for traders to develop intuition about option markets.

## Model-Building Missteps

Model building should capture what matters for valuation and hedging without making the model more complex than necessary.

1. **Over-fitting** occurs when a model is made complex enough to exactly match the current volatility surface, but this can make it difficult to use and may produce unreasonable future volatility surfaces or poor joint probability distributions.
2. **Over-parameterization** occurs when extra features such as stochastic volatility or jumps introduce additional parameters that are hard to estimate and may work only until a regime change makes the more complicated model less flexible than a simpler one.
