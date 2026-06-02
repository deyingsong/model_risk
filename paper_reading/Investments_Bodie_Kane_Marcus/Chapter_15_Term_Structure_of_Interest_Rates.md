# Chapter 15 The Term Structure of Interest Rates


## The Yield Curve

- A yield curve is a plot of yield to maturity as a function of time to maturity, and it is central to bond valuation and to comparing an investor’s expectations for future interest rates against those of the market.


### Bond pricing

- The trick is to consider each bond cash flow—either coupon or principal payment—as at least potentially sold off separately as a stand-alone zero-coupon bond, so the value of the whole coupon bond equals the sum of the present values of its individual cash flows discounted at the stripped Treasury yield for each cash flow’s maturity.
- Bond stripping is the process of splitting a whole Treasury bond into separate zero-coupon securities, each representing one coupon or principal cash flow, so if a bond sells for less than the sum of its parts, investment bankers can buy the bond, strip it, sell the separate cash flows, and earn arbitrage profit.
- Bond reconstitution is the reverse process of buying individual STRIPS, reassembling their cash flows into a coupon bond, and selling the whole bond when it sells for more than the cost of its pieces, thereby enforcing the Law of One Price.
- The pure yield curve refers to the curve for stripped, or zero-coupon, Treasuries, whose yields are the appropriate discount rates for valuing individual cash flows at different maturities.
- The on-the-run yield curve refers to the plot of yield as a function of maturity for recently issued coupon bonds selling at or near par value, and these on-the-run Treasuries are especially liquid and commonly reported in the financial press.

## The Yield Curve and Future Interest Rates

### The Yield Curve under Certainty

- With no risk, all bonds and indeed all securities must offer identical returns over the same investment period, because otherwise investors would bid up the price of the higher-return security until its return was no longer superior.
- The spot rate is the yield to maturity on a zero-coupon bond that prevails today for a time period corresponding to the zero’s maturity.
- The short rate for a given time interval is the one-period interest rate for that interval available at different points in time, such as the current one-year rate $r_1$ or next year’s one-year rate $r_2$.
- Figure 15.3 shows that the top row gives the one-year short rates in each future year, while the lower rows give today’s spot rates or zero-coupon yields for different maturities, meaning that each longer spot rate is a geometric average of the short rates over the bond’s life.

### Holding-period returns

- Bonds selling at higher yields to maturity will not offer higher 1-year returns, because in a world of certainty all bonds must offer identical holding-period returns or investors would flock to the higher-return securities, bid up their prices, and reduce their returns.

### Forward rates

- Equation 15.3 solves the break-even future one-period rate from adjacent spot rates, $1+r_n=\frac{(1+y_n)^n}{(1+y_{n-1})^{n-1}}$, where $y_n$ is the yield to maturity on an $n$-period zero-coupon bond, $y_{n-1}$ is the yield to maturity on an $(n-1)$-period zero-coupon bond, and $r_n$ is the one-period short rate in period $n$ that makes buying and holding the $n$-period zero equivalent to buying the $(n-1)$-period zero and rolling over into a one-period bond.
- When future interest rates are uncertain, the rate inferred from today’s yield curve is called the forward interest rate rather than the future short rate because no one knows today what the future short rate will actually be.
- The forward rate $f_n$ is the “break-even” interest rate defined by $1+f_n=\frac{(1+y_n)^n}{(1+y_{n-1})^{n-1}}$, where $f_n$ is the forward rate for period $n$, $y_n$ and $y_{n-1}$ are current zero-coupon spot rates, and the equation equates the return on an $n$-period zero-coupon bond to the return on an $(n-1)$-period zero-coupon bond rolled over into a 1-year bond in year $n$.
- Forward rates equal future short rates in the special case of interest rate certainty, because then the actual short rate in the future must equal the break-even rate that equalizes the riskless returns on competing strategies.

## Interest Rate Uncertainty and Forward Rates

- A liquidity premium is the difference between the forward rate and the expected future short rate, $\text{Liquidity premium}=f_n-E(r_n)$, where $f_n$ is the forward rate and $E(r_n)$ is the expected short rate in period $n$, and it compensates investors for bearing interest rate risk or holding bonds that do not match their preferred investment horizons.
- The forward rate will be more than the expected future spot rate when most investors are short-term investors who require a higher expected return to hold risky long-term bonds, so $f_n>E(r_n)$ and the liquidity premium is positive.
- The forward rate will be less than the expected future spot rate when long-term investors regard long bonds as safer than rolling over short bonds and therefore require rollover strategies to offer a reward for interest rate risk, so $f_n<E(r_n)$ and the liquidity premium is negative.

## Theories of the Term Structure

### The Expectations Hypothesis

- The expectations hypothesis states that the forward rate equals the market consensus expectation of the future short interest rate, $f_n=E(r_n)$, so liquidity premiums are zero and long-term yields depend only on current and expected future short rates.
- Under the expectations hypothesis, an upward-sloping yield curve implies that investors anticipate increases in interest rates, because forward rates reveal expected future short rates and higher long-term yields require higher expected future short rates.

### Liquidity Preference Theory

- Liquidity preference theory holds that short-term investors dominate the market, so forward rates generally exceed expected short rates, $f_n>E(r_n)$, and the positive excess $f_n-E(r_n)$ is a liquidity premium required to induce investors to hold longer-term bonds.

### Market Segmentation

- Market segmentation theory holds that long- and short-maturity bonds trade in essentially distinct and unconnected markets, so the term structure is determined by the separate equilibrium rates set in each segmented maturity market rather than by free substitution across maturities.
- Some investors may face binding limitations on their ability to shift from one maturity to another, such as money market funds being required to invest only in very-short-term securities regardless of current and expected rates elsewhere in the fixed-income market.

## Interpreting the Term Structure

- A rising yield curve can be accounted for by the fact that the forward rate for the next period exceeds the current yield at that maturity, because adding an above-average forward rate to the geometric average raises the longer-maturity yield.
- The higher forward rate can be accounted for either by a high expected future short rate or by a liquidity premium, as summarized by $f_n=E(r_n)+\text{Liquidity premium}$, where $f_n$ is the forward rate, $E(r_n)$ is the expected future short rate, and the liquidity premium is compensation for holding bonds whose maturities differ from preferred investment horizons.
- We should expect risk premiums on various maturity bonds to fluctuate because interest rate risk and the price volatility of long-term Treasury bonds fluctuate over time, making the liquidity premium difficult to estimate reliably as a constant.
- Very steep yield curves are interpreted by many market professionals as warning signs of impending rate increases, because long-term rates tend to rise in anticipation of expansion in economic activity.
- The typical implication of an upward-sloping yield curve is either expected future rate increases or a positive liquidity premium on longer maturities, while a downward-sloping yield curve is taken as a strong indication that yields are more likely than not to fall and is often interpreted as a signal of a coming recession.
- Interest rates might fall because either expected real rates or expected inflation rates decline, as shown by $1+\text{Nominal rate}=(1+\text{Real rate})(1+\text{Inflation rate})$ and approximately $\text{Nominal rate}\approx\text{Real rate}+\text{Inflation rate}$, where the nominal rate compensates investors for both real return and inflation, and the equation explains why a decline in either component can lower nominal interest rates.

## Forward Rates as Forward Contracts

- To construct the synthetic 2-year forward loan in the example, buy one 1-year zero-coupon bond and sell $1+f_2$ 2-year zero-coupon bonds so the initial cash flow is zero, then receive $\$1{,}000$ at time 1 and repay $\$1{,}000(1+f_2)$ at time 2, which in the numerical example means borrowing $\$1{,}000$ one year from now and repaying $\$1{,}070.10$ one year later at the forward rate $f_2=7.01\%$.
- The general engineering of a synthetic forward loan is to issue a longer-maturity zero-coupon bond and buy a shorter-maturity zero-coupon bond so the initial borrowing and lending positions offset until the forward start date, leaving an effective loan over the deferred period whose rate is the corresponding forward rate implied by the yield curve.
