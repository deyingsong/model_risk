# Chapter 14 Bond Prices and Yields 

## Table of Contents

- [Summary (TLDR)](#summary-tldr)
- [Bond characteristics](#bond-characteristics)
  - [Treasury bonds and notes](#treasury-bonds-and-notes)
    - [Accrued Interest and Quoted Bond Prices](#accrued-interest-and-quoted-bond-prices)
  - [Corporate bonds](#corporate-bonds)
    - [Call Provisions on Corporate Bonds](#call-provisions-on-corporate-bonds)
    - [Convertible bonds](#convertible-bonds)
    - [Puttable bonds](#puttable-bonds)
    - [Floating-rate bonds](#floating-rate-bonds)
  - [Preferred stock](#preferred-stock)
  - [Other domestic issues](#other-domestic-issues)
  - [International bonds](#international-bonds)
  - [Innovation in the bond market](#innovation-in-the-bond-market)
- [Bond pricing](#bond-pricing)
  - [Bond Pricing between Coupon Dates](#bond-pricing-between-coupon-dates)
- [Bond yields](#bond-yields)
  - [Yield to maturity](#yield-to-maturity)
  - [Yield to call](#yield-to-call)
  - [Realized Compound Return versus Yield to Maturity](#realized-compound-return-versus-yield-to-maturity)
- [Bond prices over time](#bond-prices-over-time)
  - [Yield to maturity versus holding-period return](#yield-to-maturity-versus-holding-period-return)
  - [Zero-Coupon Bonds and Treasury Strips](#zero-coupon-bonds-and-treasury-strips)
  - [After-tax returns](#after-tax-returns)
- [Default risk and bond pricing](#default-risk-and-bond-pricing)
  - [Junk bonds](#junk-bonds)
  - [Determinants of Bond Safety](#determinants-of-bond-safety)
  - [Bond indentures](#bond-indentures)
    - [Sinking funds](#sinking-funds)
    - [Subordination of Further Debt](#subordination-of-further-debt)
    - [Dividend Restrictions](#dividend-restrictions)
    - [Collateral](#collateral)
  - [Yield to Maturity and Default Risk](#yield-to-maturity-and-default-risk)
  - [Credit Default Swaps](#credit-default-swaps)
  - [Credit Risk and Collateralized Debt Obligations](#credit-risk-and-collateralized-debt-obligations)



## Summary (TLDR)

Bond models are cash-flow discounting models whose outputs are highly sensitive to assumptions about rates, timing, embedded options, credit risk, liquidity, taxes, and legal structure. A bond’s fair value is the present value of coupons and principal, so validation should start by checking cash-flow construction, discount-rate conventions, day-count/accrued-interest treatment, coupon frequency, and whether the model distinguishes flat price from invoice price. Yield metrics are not interchangeable: YTM assumes holding to maturity and reinvestment at the same yield, while realized return depends on future reinvestment rates and exit price. Callable, puttable, floating-rate, convertible, zero-coupon, and structured bonds require special handling because their effective cash flows change with market conditions. Interest-rate risk generally rises with maturity, while premium and discount bonds converge toward par over time. Credit-risk modeling should not rely only on promised yield; expected yield must incorporate default probability, loss severity, collateral, seniority, covenants, leverage, liquidity, and profitability indicators. For structured products such as CDOs or CDS-linked exposures, model review should scrutinize tranche assumptions, correlation, conflicts of interest, and stress behavior under widening default premiums. 


## Bond characteristics

- A bond is a debt security issued in a borrowing arrangement that represents the issuer’s promise to make specified payments to the bondholder on specified dates.
- Coupon payments are periodic interest payments, usually made semiannually, equal to the coupon rate multiplied by par value.
- Par value (face value) is the principal amount repaid to the bondholder at maturity.
- The coupon rate is the annual interest rate specified in the bond indenture and determines the bond’s coupon payments.
- A bond indenture is the contract between the issuer and bondholders specifying coupon rate, maturity date, par value, and other provisions.
- Zero-coupon bonds make no coupon payments and are issued at prices below par value, with returns coming solely from price appreciation to par at maturity.

### Treasury bonds and notes

- Treasury notes have original maturities of 1–10 years and Treasury bonds 10–30 years, with quoted prices expressed as percentages of par value and associated yields to maturity.

#### Accrued Interest and Quoted Bond Prices
- Accrued interest is the prorated share of the upcoming coupon owed to the seller and is calculated as $(\text{Annual Coupon}/2)\times(\text{Days Since Last Coupon Payment}/\text{Days in Coupon Period})$.
- The invoice price is the actual transaction price paid by the buyer and equals the flat price plus accrued interest.
- The flat price is the quoted bond price excluding accrued interest.

### Corporate bonds

- The bond market can be “thin” because firms often have many distinct bond issues differing in maturity, coupon, and seniority, resulting in limited trading interest in any single issue.

#### Call Provisions on Corporate Bonds

- The call price is the price at which the issuer may repurchase a callable bond before maturity.
- Refunding is the practice of retiring outstanding high-coupon debt and replacing it with lower-coupon debt when interest rates fall.
- Callable bonds give the issuer the option to repurchase the bond before maturity and therefore typically offer higher coupon rates and yields.
- Deferred callable bonds include an initial call-protection period during which the bond cannot be called.

#### Convertible bonds

- A convertible bond allows the bondholder to exchange the bond for a specified number of shares of the issuer’s common stock.
- The market conversion value equals the current market value of the shares obtainable through conversion.
- The conversion premium is the excess of the bond’s market value over its market conversion value.

#### Puttable bonds

- An extendable or put bond gives the bondholder the option either to extend the bond’s life or reclaim principal depending on prevailing market yields.

#### Floating-rate bonds

- Floating-rate bonds have coupon payments linked to current market interest rates and periodically reset according to a specified formula.

### Preferred stock

- Preferred stock is often viewed as a fixed-income security because it promises a specified stream of dividend payments.
- Preferred stock commonly pays a fixed dividend and therefore resembles a perpetuity.
- Preferred dividends are not tax-deductible expenses for the issuing firm, unlike bond interest payments.

### Other domestic issues

- Municipal bonds are issued by state and local governments and feature interest income that is generally exempt from federal income tax.

### International bonds

- Foreign bonds are issued by borrowers from one country and sold in another country in the currency of the market where they are sold.
    - **Yankee bonds**: Yankee bonds are U.S. dollar–denominated foreign bonds sold in the United States.
    - **Samurai bonds**: Samurai bonds are yen-denominated foreign bonds sold in Japan by non-Japanese issuers.
    - **bulldog bonds**: Bulldog bonds are pound-denominated foreign bonds sold in the United Kingdom by foreign issuers.
- Eurobonds are denominated in one currency but sold outside the country associated with that currency.

### Innovation in the bond market

- Bond maturities can range far beyond traditional horizons, including 50-year, 100-year, and even perpetual bonds.
- Inverse floaters have coupon rates that decrease when market interest rates increase.
- Asset-backed bonds are serviced by the cash flows generated from a specified pool of assets.
- Catastrophe bonds transfer disaster risk to investors, who may lose principal if specified catastrophic events occur.
- Indexed bonds tie principal and/or coupon payments to inflation or commodity prices, such as Treasury Inflation-Protected Securities (TIPS).

## Bond pricing

- Bond value equals the present value of all coupon payments plus the present value of par value, $\text{Bond Value}=\sum_{t=1}^{T}\frac{\text{Coupon}}{(1+r)^t}+\frac{\text{Par Value}}{(1+r)^T}$, where $T$ is maturity and $r$ is the appropriate discount rate.
    - Coupon: The periodic interest payment promised by the bond.
    - Par Value: The principal repaid at maturity.
    - r: The bond’s appropriate discount rate or required yield.
    - T: The number of periods until maturity.
    - Interpretation: The bond price equals the discounted present value of all future cash flows promised by the bond.
- The annuity factor is $\frac{1}{r}\left[1-\frac{1}{(1+r)^T}\right]$ and represents the present value of a stream of \$1 payments for $T$ periods.
    - r: Discount rate per period.
    - T: Number of periods.
    - Interpretation: It converts a constant periodic payment stream into present value.
- The PV factor is $\frac{1}{(1+r)^T}$ and represents the present value of \$1 received in $T$ periods.
    - r: Discount rate per period.
    - T: Number of periods.
    - Interpretation: It discounts a single future payment back to today.
- **bond pricing on a financial calculator**
    - **n**: Number of payment periods until maturity.
    - **i**: Interest rate per period expressed as a percentage.
    - **PV**: Present value or bond price.
    - **FV**: Future value or face value paid at maturity.
    - **PMT**: Periodic coupon payment.
- Bond prices move inversely with market interest rates because higher discount rates reduce the present value of future cash flows.
- Longer-maturity bonds exhibit greater interest-rate risk because their cash flows are discounted over a longer horizon.
- Short-term Treasury securities are considered safest because they have negligible default risk and very little price risk from interest-rate changes.

### Bond Pricing between Coupon Dates

- Between coupon dates, the invoice price equals the flat price plus accrued interest, while the flat price is the quoted price excluding accrued interest.

## Bond yields

### Yield to maturity

- Yield to maturity is the discount rate that equates a bond’s price to the present value of all promised cash flows if held to maturity.
- Current yield equals annual coupon payments divided by the bond’s current market price.
- Premium bonds sell above par value because their coupon rates exceed prevailing market yields.
- Discount bonds sell below par value because their coupon rates are lower than prevailing market yields.

### Yield to call

- Yield to call is the yield earned assuming the bond is called on the first eligible call date rather than held to maturity.
- Investors focus on yield to call when call is likely because the call date determines the actual life of the bond.
- Premium bond investors often emphasize yield to call because issuers are especially likely to call high-coupon bonds when rates decline.

### Realized Compound Return versus Yield to Maturity

- The realized compound return is the actual compound rate earned over an investment horizon based on realized reinvestment rates and sale prices.
- Horizon analysis evaluates bond performance over a specified holding period using assumptions about future rates and bond values.
- Reinvestment rate risk is the uncertainty that coupon payments will be reinvested at rates different from the bond’s yield to maturity.

## Bond prices over time

- As maturity approaches, discount bonds gain value toward par while premium bonds decline toward par, offsetting differences in coupon income.
- Figure 14.6 illustrates the convergence of bond prices toward par value as maturity approaches regardless of whether the bond initially sells at a premium or discount.

### Yield to maturity versus holding-period return

- Holding-period return can differ from initial YTM because future interest rates affect reinvestment income and the bond’s eventual sale price.

### Zero-Coupon Bonds and Treasury Strips

- Original-issue-discount bonds are issued below par and provide returns primarily through appreciation toward maturity value.
- A zero-coupon bond pays no periodic coupons and delivers a single payment of par value at maturity.
- Treasury strips are created by separating Treasury coupon and principal payments into individual zero-coupon securities.

### After-tax returns

- The IRS taxes the accrued appreciation of discount bonds annually as imputed interest income even before realization.
- Holding-period return (HPR) measures the total return over a holding period including income, price change, and tax effects where relevant.

## Default risk and bond pricing

- Default risk or credit risk is the possibility that a bond issuer will fail to make promised payments.
- Investment-grade bonds are higher-quality bonds with relatively low default risk and ratings of BBB/Baa or above.
- Speculative-grade or junk bonds have lower credit ratings and higher probabilities of default.

### Junk bonds

- High-yield bonds are speculative-grade bonds that offer higher promised yields to compensate investors for greater credit risk.

### Determinants of Bond Safety

- Bond safety is commonly assessed using coverage ratios, leverage ratios, liquidity ratios, profitability measures, and cash-flow adequacy indicators.
- Discriminant analysis combines multiple financial ratios into a statistical model for predicting default risk.

### Bond indentures

- A bond indenture is the legal contract specifying the rights of bondholders and obligations of the issuer.
- A protective covenant is a contractual restriction designed to protect bondholders from actions that could weaken their claims.

#### Sinking funds

- A sinking fund may require either periodic retirement of bonds at market prices or random redemption at a specified sinking-fund price.
- The double option refers to the issuer’s ability to choose whether to buy bonds in the market or redeem them through the sinking-fund provision.
- A sinking fund can hurt investors because bonds may be retired when prices are high, limiting capital gains.
- A serial bond issue retires portions of principal periodically through a schedule of staggered maturities.

#### Subordination of Further Debt

- Subordination clauses restrict the priority or amount of additional debt that may be issued ahead of existing bondholders.

#### Dividend Restrictions

- Dividend restrictions protect bondholders by preventing excessive cash distributions that could weaken the issuer’s financial position.

#### Collateral

- Collateral consists of assets pledged to secure a bond issue.
- A mortgage bond is secured by real property.
- A collateral trust bond is secured by financial assets such as stocks or bonds held in trust.
- An equipment obligation bond is secured by specific equipment owned by the issuer.
- Debentures are unsecured bonds backed only by the issuer’s general creditworthiness.

### Yield to Maturity and Default Risk

- Expected yield to maturity adjusts promised yield for the possibility of default and expected losses.
- The default premium is the portion of a bond’s yield that compensates investors for expected credit losses and default risk.
    - During October 2008, default premiums widened dramatically as investors demanded much higher compensation for heightened credit risk.

### Credit Default Swaps

- A credit default swap (CDS) is a contract in which a protection seller compensates a protection buyer if a referenced borrower defaults.
- CDS premiums are determined by the market’s assessment of default probability and expected loss given default.

### Credit Risk and Collateralized Debt Obligations

- CDOs are structured securities that pool debt instruments and redistribute credit risk through multiple tranches.
- An SIV is a special-purpose entity that finances long-term assets with short-term borrowing to earn a spread.
- Riskier CDO tranches offer higher coupon rates to compensate for greater expected losses.
- Conflicts of interest arise when parties involved in structuring, rating, or selling CDOs have incentives that differ from those of investors.
