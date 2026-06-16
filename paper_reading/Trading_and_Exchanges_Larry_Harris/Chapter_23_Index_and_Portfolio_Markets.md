# Chapter 23 Index and Portfolio Markets

## Summary (TLDR)

Index and portfolio markets let investors trade broad market risk through index funds, ETFs, futures, options, and portfolio baskets instead of trading every underlying security separately. Index construction matters: price-weighted, value-weighted, equal-weighted, and total-return indexes embed different assumptions about weights, dividends, rebalancing, and corporate actions. For model risk management, these details are not implementation trivia; they define the benchmark, explain residuals, and affect whether backtests, hedges, and performance attribution are valid.

Index funds aim to replicate dividend-adjusted benchmark returns, but tracking error arises from fees, transaction costs, cash flows, dividend reinvestment timing, sampling, substitutions, and rebalancing choices. Passive indexation is powerful because active management is a zero-sum game before costs and negative-sum after costs, so turnover and fees are central risk and performance drivers. Index products are liquid because they concentrate order flow, reduce adverse-selection risk, and package many component trades into one instrument, but their derivatives introduce basis, roll, margin, settlement, and liquidity risks. Portfolio and basket trading can lower execution cost, yet pricing depends on dealer quotes, end-of-day valuation conventions, and component liquidity.


## Table of Contents


- [Price indexes](#price-indexes)
- [Index funds](#index-funds)
- [The argument for indexation](#the-argument-for-indexation)
- [Liquidity and price formation in index markets](#liquidity-and-price-formation-in-index-markets)
  - [Package trading, basket trading, and portfolio trading](#package-trading-basket-trading-and-portfolio-trading)
- [Index products](#index-products)


---

- index market: Index markets trade index products and let traders exchange index risk more cheaply and more liquidly than they could by trading each underlying component instrument separately.
- index product: Index products include index futures contracts, index option contracts, and securities that represent ownership in index funds, allowing investors and speculators to trade index risk or hedge firm-specific positions.
- index fund: An index fund is a portfolio that its managers design to replicate the performance of a price index, most often a market equity index but sometimes a debt or sector equity index.

## Price indexes

- price index: People use price indexes to characterize the values of lists of instruments, and a generic index can be written as $I=\frac{S}{D}$, where $S$ is the price or value sum used by the index creator and $D$ is the index divisor chosen to set and maintain the index level, so the index is essentially an average scaled by a constant.
- index components: The instruments upon which a price index is based are the index components, and these components determine whether the index represents an entire market, a subset of a market, or a set of markets.
- Dow 30: The Dow Jones Industrial Average (DJIA), or Dow 30, is a price-weighted index of 30 large U.S. stocks that was originally industrial but now includes finance and service stocks and is the best-known U.S. market index.
- MMI: The Major Market Index (MMI) is a price-weighted index of 20 blue chip stocks created by the American Stock Exchange when Dow Jones refused to license the DJIA, with changes that were very closely correlated with the Dow 30.
- S&P 500: The S&P 500 Index is the best-known **value-weighted index**, meaning securities with the highest capital value have the greatest influence over its value.
- index creators: Most price indexes are proprietary products that exchanges, brokers, or data vendors compute, often offering them to clients to promote business or licensing them to firms that base index products upon them.
- price-weighted index: A price-weighted index is proportional to the sum of the prices of the index components, so $I_{PW}=\frac{\sum_{i=1}^{N}P_i}{D}$, where $P_i$ is the price of component $i$, $N$ is the number of components, and $D$ is the index divisor, meaning the highest priced instruments have the greatest influence on index values.
- value-weighted index: A value-weighted index is proportional to the total capital value of all index components, so $I_{VW}=\frac{\sum_{i=1}^{N}P_iQ_i}{D}$, where $P_i$ is the price of component $i$, $Q_i$ is its number of outstanding shares or units, and $D$ is the index divisor, meaning securities with the highest capital value have the greatest influence.
- capitalization-weighted index: A capitalization-weighted index is another name for a value-weighted index because it weights securities by their capital value or market capitalization rather than by their prices alone.
- index divisor: The index divisor is the constant by which the price or value sum is divided to obtain the index value, and it changes when necessary to ensure that adding or deleting components or a stock split in a price-weighted index does not mechanically change the index value.
- equal-weighted index: Equal-weighted indexes measure the returns from investing an equal dollar amount in each index component, so their index values represent the cumulative returns to this hypothetical investment strategy.
- geoetrically-weighted index: Geometrically weighted indexes average logarithmic returns rather than prices, as in the Value Line Geometric Index, which is a value-weighted index of logarithmic returns.
- dividend-adjusted, total return index: A price index is dividend-adjusted if it is adjusted upward when securities pay dividends, and traders call these total return indexes because they measure the total return—capital gains plus income yield—that investors would receive if they could invest in the index without transaction costs.

## Index funds

- index manager: An index manager designs and manages a portfolio to replicate the performance of an index while minimizing deviations from the corresponding dividend-adjusted index return.
- tracking error: Tracking error is the difference between the portfolio return and the corresponding dividend-adjusted index return, so $TE=R_p-R_I$, where $R_p$ is the index fund portfolio return and $R_I$ is the dividend-adjusted index return, meaning managers try to keep this return difference as small as possible.
- replicating a value-weighted equity index: Replicating a value-weighted equity index is simple because if the fund value is $f$ percent of the total capitalization of all index components, the manager buys $f$ percent of the outstanding shares of each component so the fund value, component capital value, and index value have identical percentage changes.
- replicating a price-weighted equity index: Replicating a price-weighted equity index is equally simple because the fund holds an equal number of shares in each index component, making the portfolio value proportional to the sum of component prices and therefore proportional to the price-weighted index.
- replicting the returns to a dividend-adjusted index: To replicate the returns to a dividend-adjusted index, index funds must reinvest their dividends as they are paid so that the fund captures both capital gains and income yield.
- frictions drag down performance: Index funds generally slightly underperform their target indexes because transaction costs from dividend reinvestment, deposits and redemptions, rebalancing transactions, and management fees drag down performance.
- careful management of trading: Index funds can slightly improve returns by careful trading—supplying rather than demanding liquidity, substituting nonindex components when index components are expensive to trade, rebalancing only around deposits, redemptions, and dividends, or holding only a subset of components—although these policies generally increase tracking error.

## The argument for indexation

- active portfolio managers: Active portfolio managers are speculators who try to beat the market by clever trading and may act as informed traders, value traders, or technical traders.
- turnover: The turnover of a portfolio is the ratio between the total dollar value of all portfolio purchases, sales, or their average in a period and the total value of the portfolio, so $Turnover=\frac{\text{dollar value of purchases, sales, or their average}}{\text{total portfolio value}}$, measuring how much the manager trades relative to portfolio size.
- passive managers: Passive managers construct portfolios and then leave them alone, so they rarely trade, usually have turnover rates between 0 and 10 percent per year, and typically charge much lower fees than active managers.
- Most active managers cannot beat the market: Most active managers cannot beat the market because transaction costs and management fees reduce performance in what is otherwise a zero-sum game where, before costs, the value-weighted average return of all portfolios equals the value-weighted market index return.
- buy and hold strategy: Many uninformed investors employ buy and hold strategies to avoid selecting skilled active managers and paying the costs of unskilled active management, and index funds implement buy and hold strategies that give index-risk exposure while usually beating three-quarters of active managers despite slightly underperforming their indexes.

## Liquidity and price formation in index markets

- Several factors ensure that index products have low transaction costs: Several factors ensure that index products have low transaction costs because index dealers face limited adverse-selection risk, index markets concentrate order flow, and index products reduce many component trades to a single transaction.
    1. little risk of trading with well-informed trader: Index dealers face little risk of trading with well-informed traders because most index traders are uninformed investors and few traders have valuable insights into the future direction of the entire market, so dealers need not quote wide spreads.
    2. active market: Index markets tend to be very active because most people trade the same index products, making it easy for buyers to find sellers and allowing dealers to turn inventories quickly and quote tight markets.
    3. reducing trade: Traders of index products generally arrange, clear, and settle only a single transaction, which saves time and effort compared with arranging many trades in the underlying component instruments.
- program trade: A program trade involves the simultaneous submission of many orders at the same time, and for statistical purposes the NYSE and SEC classify program trades as coordinated trades involving 15 or more transactions with a total value of 1 million dollars or more.
- order list processing software: Traders who do program trades generally use specialized order list processing software to manage their many coordinated orders.

### Package trading, basket trading, and portfolio trading

- package dealers: Package dealers make firm bids or offers for entire portfolios and often quote lower trading costs for index portfolios because informed traders are less likely to trade portfolios than individual securities.
- firm bid/offer market: The firm bid/offer market, also called the package trading market, basket market, or portfolio trading market, works when a trader submits a portfolio characterization to one or more package dealers, receives firm prices often expressed relative to the end-of-day portfolio value, and usually trades with the dealer offering the best price.

## Index products

- Major U.S. Broad-based Index Products: Major U.S. broad-based index products include open-end mutual funds such as Vanguard 500 Index Fund Investor Shares and Fidelity Spartan 500 Index Fund, ETFs such as Spiders, Cubes, and Diamonds, cash-settled futures on the S&P 500, Nasdaq 100, and Dow 30, cash-settled index options such as SPX, OEX, and DJX, and options on futures contracts.
- Exchange-traded index funds (ETFs): Exchange-traded index funds are trusts that typically hold index portfolios whose units trade like stocks on exchanges and ECNs, while large traders can create units by depositing an index portfolio with the trust or redeem units for their pro rata share of the portfolio.
- index future contract: Index futures contracts are the most important derivative index products and are especially popular among hedgers and speculators because they can buy and sell index risk without posting large margins, although long-term holders must roll positions into new contracts when current contracts expire and thereby incur transaction costs.
