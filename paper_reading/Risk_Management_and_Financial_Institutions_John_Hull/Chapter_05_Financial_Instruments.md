# Chapter 5 Financial Instruments

## Long and short positions in assets

- Spot trades are trades that lead to almost immediate, or **"on the spot,"** delivery of the asset.
- Buying on margin is **borrowing part of the cost** of an asset from a broker when purchasing it on an exchange, with the asset pledged as collateral and the margin account monitored against a maintenance margin.

### Short sales

- Shorting the asset means **selling an asset that you do not own** with the intention of buying it back later.
- An investor is short-squeezed when, while the short position is open, the broker is unable to borrow the shares and the investor is forced to close out the position immediately, even if not ready to do so.
- An investor with a short position **must pay to the broker any income**, such as dividends or interest, that would normally be received on the asset that has been shorted.
- An investor entering into a short position has potential future liabilities and is therefore required to provide margin, or collateral, with United States stock short sales typically requiring margin of 150% of the value of the shares shorted.
- Prior to 2007, the United States **uptick rule** allowed stocks to be shorted only when the most recent price movement had been up, while the 2010 **alternative uptick rule** applies *after a stock price declines by more than 10% in one day and remains in force for the rest of that day and the next one*.

## Derivatives markets

- A derivative is an instrument whose value **depends on, or derives from**, other more basic market variables.
- Derivatives trade in both the **exchange-traded and OTC markets**, and the over-the-counter derivatives market is much larger than the exchange-traded derivatives market when measured by underlying principal amounts or asset values.
- The principal, or value of assets, underlying a derivatives transaction is not the same as its value, because a contract with a large underlying principal can have a much smaller market value.

## Plain vanilla derivatives

### Forward contracts

- A forward contract is an agreement to **buy an asset in the future for a certain price**, and forward contracts trade in the over-the-counter market.
    - The party with the **long position** in a forward contract agrees to buy the underlying asset on a specified future date for a specified price, with payoff equal to the spot price of the asset at maturity minus the agreed delivery price.
    - The party with the **short position** in a forward contract agrees to sell the underlying asset on the same date for the same price, with payoff equal to the agreed delivery price minus the spot price of the asset at maturity.
- **Forward contracts on foreign exchange** are very popular, and banks quote bid and ask exchange rates for spot and different forward maturities.
- Forward contracts can be used to **hedge foreign currency risk** by locking in today the exchange rate at which a future foreign-currency payment or receipt will be made.

### Futures contracts

- Futures contracts, like forward contracts, are **agreements to buy an asset at a future time**.
    - Unlike forward contracts, futures are **traded on an exchange** and are therefore standardized contracts.
    - The exchange defines the amount of the asset underlying one contract, when delivery can be made, exactly what can be delivered, alternative delivery times, delivery locations, and related contract terms.
- Most futures contracts trade actively, with the futures price at any given time being determined by supply and demand.
- One attractive feature of exchange-traded contracts such as futures is that **it is easy to close out a position** by taking the opposite position in the same contract.
- The futures price of an asset is usually very similar to its forward price, although a futures contract is settled daily whereas a forward contract is settled at the end of its life.
- Futures are cleared on an **exchange clearing house**, which stands between the two sides and is responsible for ensuring that required payments are made.
- The clearing house requires initial margin and variation margin from members, and brokers require margin from clients so that the margin account is adjusted for daily gains and losses and replenished when it falls below the maintenance margin.

### LIBOR and its replacements

- The **London Interbank Offered Rate, or LIBOR**, was compiled for 40 years by asking a panel of global banks to estimate the unsecured rates at which they could borrow from other banks just before 11 A.M. United Kingdom time.
- A problem with LIBOR was that there was not enough borrowing between banks for submissions to be based on market transactions, so the quotes involved judgment and **some banks manipulated their LIBOR quotes**.
- The **secured overnight funding rate, or SOFR**, is the United States replacement overnight reference rate chosen by regulators and based on actively traded overnight rates.
- The two key differences are that LIBOR is known at the beginning of the period to which it applies while a compounded overnight rate is known only at the end of the period, and LIBOR incorporates some credit risk while the replacement overnight rates and longer-term rates calculated from them are generally assumed to be risk-free rates.
- Other reference rates similar to LIBOR but based on actual transactions include the Bloomberg Short-Term Yield Index, or BSBY, and AMERIBOR, created by the American Financial Exchange.

### Swaps

- A swap is an agreement between two companies to **exchange cash flows in the future**, with the agreement defining the payment dates and how the cash flows are calculated.
- A forward contract can be viewed as a simple example of a swap because it is equivalent to exchanging cash flows on one future date.
- Unlike a forward contract, swaps typically lead to **cash flow exchanges taking place on several future dates**.
- A "plain vanilla" interest rate swap is the most common swap and exchanges a fixed rate of interest for a floating reference rate, with both rates applied to the same notional principal that is used only for determining interest exchanges and is not itself exchanged.

### Options

- Options are traded both on exchanges and in the over-the-counter market, with exchange-traded options tending to be American and OTC options frequently European.
- A **call option** gives the holder the right to buy the underlying asset by a certain date for a certain price.
- A **put option** gives the holder the right to sell the underlying asset by a certain date for a certain price.
- The **strike price**, also called the exercise price, is the price in the option contract at which the underlying asset can be bought or sold.
- The **expiration date, or maturity date**, is the date in the option contract by which or on which the holder can exercise the right.
- An **at-the-money option** is an option where the strike price equals the price of the underlying asset.
- An **out-of-the-money option** is a call option where the strike price is above the price of the underlying asset or a put option where the strike price is below this price.
- An **in-the-money option** is a call option where the strike price is below the price of the underlying asset or a put option where the strike price is above this price.
- The **option premium** is the cost of acquiring an option.
- Buyers of options have long positions and sellers of options have short positions.
- Writing an option means selling an option.

### Interest rate options

- A **cap** is a series of call options on a floating rate, paying the **excess of the floating rate over the cap rate** applied to a predetermined notional for the appropriate accrual period when the floating rate is greater than the strike rate and paying nothing otherwise.
- A **floor** is a series of put options on a floating rate, paying the **difference between the floor rate and the floating rate** applied to the notional principal for the appropriate accrual period when the floating rate is less than the strike price and paying nothing otherwise.
- A swap option, or **swaption**, is an option to enter into a swap at some future time where the fixed rate is the strike rate, either to pay the strike rate and receive the floating rate or to pay the floating rate and receive the strike rate.

## Non-traditional derivatives

### Weather derivatives

- A day's heating degree days and cooling degree days are defined by the equations `HDD = max(0, 65 - A)` and `CDD = max(0, A - 65)`, where `A` is the average of the highest and lowest temperature during the day at a specified weather station in degrees Fahrenheit, so **HDD measures energy required for heating and CDD measures energy required for cooling**.
- A typical OTC weather product is a forward or option contract with a payoff dependent on the cumulative HDD or CDD during a month, such as a call option on cumulative HDD with a strike price, payment rate, and often a payment cap.

### Oil derivatives

- In the OTC oil market, swaps, forward contracts, options, and virtually any derivative available on common stocks or stock indices can be written on oil as the underlying asset, with settlement either in cash or by physical delivery.
- Exchange-traded oil contracts are popular on the CME Group and Intercontinental Exchange, including futures and futures options on crude oil and refined products with either cash settlement or physical delivery depending on the contract.

### Natural gas derivatives

- The natural gas industry throughout the world went through a period of deregulation and the elimination of government monopolies in the 1980s and 1990s, so the supplier of natural gas is now not necessarily the same company as the producer and suppliers must meet daily demand.
- A typical OTC natural gas contract is for delivery of a specified amount of natural gas at a roughly uniform rate over a one-month period, with forward contracts, options, and swaps available and the seller usually responsible for pipeline delivery to the specified location.

### Electricity derivatives

- Electricity is an unusual commodity because it **cannot easily be stored**, which can cause occasional very large movements in the spot price.
- In the United States there are 140 regions known as **control areas**, where demand and supply are first matched within a control area and any excess power is sold to other control areas subject to transmission capacity, transmission cost, and energy transmission losses.
- Deregulation and the elimination of government monopolies have been accompanied by the development of an electricity derivatives market, including CME Group futures and active OTC forward contracts, options, and swaps.
- A **swing option**, or take-and-pay option, specifies minimum and maximum amounts of power or natural gas to be purchased at a certain price each day and in total for the month, allowing the holder to change or swing the purchase rate subject to a limit on the number of changes.

## Exotic options and structured products

- Asian options provide a payoff based on the average price of the underlying asset over a specified period rather than the price at exercise, as in an average price call option with payoff `max(S - K, 0)`, where `S` is the average asset price during the period and `K` is the strike price.
- Barrier options are options that come into existence or disappear when the price of the underlying asset reaches a certain barrier.
- Basket options are options to buy or sell a portfolio of assets rather than options on a single asset.
- Binary options provide a fixed dollar payoff or a certain amount of the underlying asset if some condition is satisfied.
- Compound options are options on options, including a call on a call, a call on a put, a put on a call, and a put on a put.
- Lookback options provide a payoff based on the maximum or minimum price of the underlying asset over some period, such as payoff `S_T - S_min`, where `S_T` is the asset price at the end of the year and `S_min` is the minimum asset price during the year.

## Risk management challenges

- Jérôme Kerviel's activities at Société Générale illustrate the risk that traders can take unauthorized positions, hide them with fictitious trades, and create very large losses when controls fail.
- Both financial and nonfinancial corporations must set up controls to ensure that derivatives are being used for their intended purpose.
