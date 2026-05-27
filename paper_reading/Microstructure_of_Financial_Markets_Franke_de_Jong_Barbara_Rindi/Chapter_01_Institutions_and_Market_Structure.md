# Chapter 1 Institutions and market structure

## Table of Contents

1. [Trading protocol](#trading-protocol)
    - [Order-driven markets](#order-driven-markets)
      - [Auction markets](#auction-markets)
      - [Quote-driven markets](#quote-driven-markets)
      - [Hybrid markets](#hybrid-markets)
      - [Transparency](#transparency)
2. [Market structure](#market-structure)
    - [Market structures around the world](#market-structures-around-the-world)
    - [The market structure of the NYSE](#the-market-structure-of-the-nyse-new-york-stock-exchange)
    - [The hybrid market model](#the-hybrid-market-model)
3. [Orders and order properties](#orders-and-order-properties)


## Trading protocol

### Order-driven markets

1. defition of order-driven market: In order-driven markets, investors’ buy and sell orders are **matched directly without intermediaries**, liquidity is guaranteed by the flow of orders from market participants, and brokers only transmit clients’ orders without taking positions in the traded asset.

#### Auction markets

* definition of auction market: Auction markets are order-driven markets **organized either as call markets or continuous auctions**, where prices are determined according to specific trade pricing rules.
* limit orders: A limit order **specifies both quantity and a maximum or minimum execution price**, guarantees price but not immediate execution, and remains in the limit order book until executed or cancelled.
* market orders: A market order **specifies only quantity and is executed immediately at the best available price**, although the execution price may be unfavourable.

* order precedence rules
  * time priority: Time priority means that **traders submitting the same quoted price earlier** gain precedence for execution over traders submitting later.
  * price priority: Price priority means that **traders with the highest bid and lowest ask** gain precedence for order execution.
  * visibility and size restriction: Visibility and size restrictions govern whether orders are publicly observable and whether execution precedence depends on disclosed order size.

* trade pricing rules
  * uniform price (electronic call): In electronic call auctions, all trades are executed **simultaneously** at the same equilibrium price under a uniform pricing rule.
  * discriminatory price (continuous call): In electronic continuous auctions, orders are executed **one by one at available prices** under a discriminatory pricing rule.
  * derivative price (crossing network): In crossing networks, orders are crossed **using derivative pricing rules** based on prices from the stocks’ primary markets.

* oral call auctions: Oral call auctions are **open-outcry auctions** where traders publicly announce bids and offers face-to-face on a trading floor and contracts are executed according to price and time priority.
* electronic call auctions: Electronic call auctions **collect orders through a computerized system** during a predetermined period and execute all trades simultaneously at a single equilibrium price.
* opening and closing auctions: Opening and closing auctions consist of pre-opening order submission, equilibrium price validation, and simultaneous order clearing phases designed to maximize trading volume and minimize excess demand.
* crossing networks: Crossing networks are call systems that **cross orders at predetermined times using prices derived from primary markets** instead of generating their own equilibrium prices.

#### Quote-driven markets

* A quote-driven market is a market where **designated liquidity suppliers continuously quote bid and ask prices** and guarantee liquidity by trading on their own account.

#### Hybrid markets

* Hybrid markets combine elements of both order-driven and quote-driven protocols so that liquidity is supplied both by market-makers and by investors’ limit orders.

#### Transparency

* Post-trade transparency refers to the rules of disclosure on the size and direction of the orders executed and the identity of the traders.
* Pre-trade transparency refers to the quoted prices and quantities and/or to the market participants’ identities, and may be directed either to all the agents present in the market or to some only (i.e. brokers/dealers).

## Market structure

### Market structures around the world

* main features of the major financial markets related to organizational structure and transparency: Major financial markets **differ** in organizational structure, trading protocol, automation, opening and closing auctions, limit order book transparency, anonymity rules, and the use of hidden orders.

### The market structure of the NYSE (New York Stock Exchange)

* The NYSE is characterized by a **mixed market structure** in which an electronic limit order book competes with professional specialists to provide liquidity.
* rules of price and time priority: Trading on the NYSE is regulated by price priority, precedence rules favoring public orders over specialists’ orders, time priority, and size precedence rules.
* opening and closing prices: Opening and closing prices at the NYSE are determined by specialists who minimize market imbalances by matching buy and sell orders.
* timing of opening auction and closing auction: Trading at the NYSE runs from the opening auction at 9:30 a.m. to the closing auction at 4:00 p.m.

### The hybrid market model

* The Hybrid Market initiative introduced a more flexible electronic trading structure that enhanced Direct+ and expanded electronic access to the NYSE limit order book.
* The size and time restrictions on automatic execution of orders were removed: The Hybrid Market removed restrictions limiting automatic execution to orders smaller than 1,099 shares and to one order every thirty seconds.
* new trading tools: The Hybrid NYSE introduced new tools such as AL and AM orders, e-Quote, s-Quote, and API algorithms for specialists and floor brokers.

## Orders and order properties

* Market orders are **‘at best’ orders** and are usually submitted by impatient traders: Market orders are aggressive liquidity-consuming orders submitted by traders who prioritize immediacy over execution price.
* Limit orders are **liquidity-supplying orders submitted by patient traders** who prioritize favorable prices over immediate execution.
* The opening and closing auction at NASDAQ: NASDAQ opening and closing crosses are single-price mechanisms that execute orders at 9:30 a.m. and 4:00 p.m. using algorithms that maximize paired shares and minimize imbalances.
