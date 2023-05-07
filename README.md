Download Link: https://assignmentchef.com/product/solved-fe621-final-exam
<br>
<strong>Problem A: Asian Option Pricing using Monte Carlo Control Variate. </strong>The payoff of an arithmetic Asian call option is:

<em> .</em>

Its value may be computed using straight Monte Carlo simulations. However, in order to obtain a small standard error, the number of simulations must be very high. To solve this computationally extensive problem, we will use the payoff of a geometric Asian call option as the control variate:

The idea is to use the known analytic price of the geometric Asian and the distance between MC simulations to obtain an approximate for the analytical formula for the arithmetic Asian price.

In this problem we consider <em>r </em>= 3%<em>, σ </em>= 0<em>.</em>3<em>, S</em><sub>0 </sub>= 100, and assume the goal is to price an arithmetic Asian call option with strike <em>K </em>= 100 and maturity <em>T </em>= 5.

We also assume the asset follows the standard log-normal/geometric Brownian motion model:

<ul>

 <li>The price of a geometric Asian option in the Black-Scholes model is given by:</li>

</ul>

where:

such that ˆ<em>σ </em>is adjusted sigma and <em>N </em>is the total number of trading days (<em>T </em>∗ 252).

Use the above formula to price this geometric Asian call option.

<ul>

 <li>Implement a Monte Carlo scheme to price an arithmetic Asian call option</li>

</ul>

). Use <em>M </em>= 1<em>,</em>000<em>,</em>000 simulations. Record the answer, a confidence interval and the time it takes to obtain the result.

<ul>

 <li>Implement a Monte Carlo scheme to price a geometric Asian Call option</li>

 <li>Using <em>M </em>= 10<em>,</em>000 simulations and the same exact random variables create:

  <ul>

   <li>numbers <em>X<sub>i </sub></em>which are <em>M </em>replications for the arithmetic Asian Option price</li>

   <li>numbers <em>Y<sub>i </sub></em>which are <em>M </em>replication for the geometric Asian Option price</li>

  </ul></li>

</ul>

Finally calculate <em>b</em><sup>∗ </sup>such that:

Note that <em>b</em><sup>∗ </sup>is actually the slope of a regression line <em>Y </em>= <em>a</em>+<em>bX </em>+<em>ε</em>. Please also record the price of the arithmetic <em>P<sub>a</sub><sup>sim </sup></em>and the geometric <em>P<sub>g</sub><sup>sim</sup></em>.

<ul>

 <li>Calculate the error of pricing for the geometric Asian:</li>

 <li>Calculate the modified arithmetic option price ( ) as:</li>

</ul>

Compare with the results in (b). Comment. Vary the value of <em>M </em>in part (d). What do you observe.

Bonus For this problem apply the Asian option pricing in practice. Download from the Bloomberg terminal Asian option data for an equity at your choice. Consider five different maturities and five strike prices. Construct a table and repeat the parts (<em>a</em>) to (<em>f</em>) using your data. In order to access Asian options for your equity, follow the instruction below. For example, if you want to access Asian options on IBM Us Equity:

<ul>

 <li>Enter IBM EQUITY OMON. OMON function stands for Option Monitor.</li>

 <li>On the OMON page, type OVME. OVME function (Option Valuation) is Bloomberg main pricing application for options on equity, indexes, funds, bonds, bond futures and short term interest rate futures.</li>

 <li>On the top of the screen, you will find ”Product” tab. Under this tab, click on the ”show all styles”. You will find all types of options.</li>

 <li>Click on number 17 which is Asian option.</li>

 <li>You can click on the ”Matrix” subtab to see your data as a matrix. You can modify this matrix by checking/unchecking variables at the right side of the screen. For this specific question, you can check strike prices and maturities.</li>

</ul>

<strong>Problem B: A portfolio construction problem. </strong>In this question, you need to create a portfolio which replicates the behavior of a specific select sector SPDR ETF. The goal of this question is to gain a deep understanding in multivariate Monte-Carlo simulation and option pricing.

<ol>

 <li>Please identify and select a specific sector’s SPDR ETF, for example XLF, XLE, etc. This site <a href="http://finviz.com/">http://finviz.com/</a> presents details about the tickers in each sector. In the sector you choose download 4 equity prices since 2012. Please only select equities that trade at $5 or above. Try picking equities at random among the ones that have this criteria. Using the same equities is a sure method to create suspicions.</li>

 <li>For the 4 equities that you chose, we will use the geometric BM:</li>

</ol>

<em>dS<sub>t </sub></em>= <em>θ</em><sub>1</sub><em>S<sub>t</sub>dt </em>+ <em>θ</em><sub>2</sub><em>S<sub>t</sub>dW<sub>t</sub></em>

Using the data you downloaded, please estimate the parameter values (<em>θ</em><sub>1</sub><em>,θ</em><sub>2</sub>) for each equity. Please report these values.

<ol start="3">

 <li>Estimate the correlation matrix Σ for the 4 stocks based on historical data.</li>

 <li>Using the correlation matrix in the part 3 and the parameters you estimated in part 2 generate Monte-Carlo paths for the 4 stocks. Use this matrix to generate correlated increments for your Monte Carlo paths. Please use the <strong>Euler-Milstein </strong>scheme for generation. Use <em>T </em>= 1 year, ∆ and <em>n </em>= 1000 paths in your simulation. Once it is done, you only need to keep the final value <em>S<sub>T </sub></em>for each stock. You should have 4 vectors in total each with <em>n </em> Please report basic statistics (mean, standard deviation, skewness, and kurtosis) for each stock.</li>

 <li>Download daily data for the main ETF for the same exact period as before. We will fit a geometric Brownian motion to it:</li>

</ol>

<em>dS<sub>t </sub></em>= <em>µS<sub>t</sub>dt </em>+ <em>σS<sub>t</sub>dWt</em>

Get the values for <em>µ </em>and <em>σ </em>in a similar way with what you did in part 2.

<ol start="6">

 <li>Run a multivariate regression using the historical data. The response is the ETF return and the predictors are the 4 stocks you chose earlier. Please record the regression coefficients. These are going to be the weights <em>w<sub>i </sub></em>for <em>i </em>∈{1<em>,</em>2<em>,</em>3<em>,</em>4} for the basket option we will price next.</li>

 <li>We will price a nonstandard contract next. The contract buyer has the option to exchange 1 ETF share with a weighted average of the 4 stocks. Specifically, denote with <em>S<sub>T </sub></em>the ETF value and with <em>S</em><sub>1</sub>(<em>T</em>)<em>,…,S</em><sub>4</sub>(<em>T</em>) the stock value for the 4 equities. The option payoff is:</li>

</ol>

use <em>T </em>= 1 year. Calculate the option price today (premium). What if the buyer has the option to exchange the weighted average for the ETF.

Calculate the premium for this option.

<strong>Problem C. Local volatility. </strong>We shall consider in this problem two volatility models: implied and local volatility, and compare them from the perspective of pricing, numerical efficiency, and stability. Please find the attached file SPX.xls, containing option prices for the S&amp;P 500 index for different maturities and strikes, with the following structure: on the first row you are given (in this order) today’s date, today’s price, and the interest rate in percents, assumed constant. The dividend yield is assumed 0. Starting with row 2, a four column table is given, containing the expiry date, time to maturity (calculated from the expiry date), the strike price and the European call option price. Please note that the dates are given in a number format, and the difference between any two cells represent the number of days. Use this file to answer the rest of this problem.

<ul>

 <li>Compute the implied volatilities from the Black–Scholes model, using the given file. For this purpose, implement any efficient root–finding method to compute the roots (or zeroes) of your function. You should also produce a plot of the points {<em>K<sub>i</sub>,T<sub>j</sub>,σ<sub>ij</sub></em>}, with <em>i </em>= 1<em>,…,</em>20<em>, j </em>= 1<em>,…,</em>4 in 3– dimensions, in the space (<em>K,T,σ</em>).</li>

 <li>Compute and plot the implied volatility surface. For this purpose, you should interpolate the points {<em>K<sub>i</sub>,T<sub>j</sub>,σ<sub>ij</sub></em>}, with <em>i </em>= 1<em>,…,</em>20<em>, j </em>= 1<em>,…,</em> <em>Hint. </em>Consider a cubic spline interpolation in 2 dimensions. You may use any package or toolbox that computes the interpolation.</li>

 <li>For the points on the surface you just calculated is the non–arbitrage condition holding?</li>

 <li>A conceptually different volatility model, the so–called <em>local volatility</em>, introduced by Dupire in [1], gives the volatility in terms of (<em>K,T</em>) in a nonparametric way, and is model independent.</li>

</ul>

Assuming that we are given European option prices <em>C </em>= <em>C</em>(<em>K,T</em>), Dupire’s local volatility is given by:

<em>,                            </em>(1)

where <em>r </em>≥ 0 is the risk–free interest rate and <em>q </em>≥ 0 is the dividend yield. Further, by noting that the implied volatility <em>σ </em>is a function of strike and expiry, i.e., <em>σ </em>= <em>σ</em>(<em>K,T</em>), the partial derivatives in (1) can be obtained with respect to <em>σ</em>, i.e. the local volatility function can be expressed as a function of implied volatility rather than of option prices:

<em>, </em>where

<em>.                                </em>(3)

Calculate Dupire’s local volatility {<em>K<sub>i</sub>,T<sub>j</sub>,</em>Σ<em><sub>ij</sub></em>}, with <em>i </em>= 1<em>,…,</em>20<em>, j </em>= 1<em>,…,</em>4 using both formulations. Compute and plot the local volatility surface in the space (<em>K,T,</em>Σ) using a cubic spline interpolation. Compare with the implied volatility surface from part (b).

<em>Hint. </em>Use the interpolated implied volatility surface from part (b) and use finite differences to compute the partial derivatives of the implied volatility with respect to strike, maturity, and second partial derivative with respect to strikes. Then use the formula (2) to compute the local variance Σ<sup>2</sup>(<em>K,T</em>). Two issues remain to be addressed: how to get rid of negative values in the local variance (one can use linear interpolation) and 3D interpolation of the LV surface.

<ul>

 <li>Calculate the price of an European option <em>C</em>(<em>t,S</em>;<em>T,K</em>), with the volatility equal to Σ(<em>K,T</em>) instead of <em>σ</em>. Can you calculate the price of this option? How? Calculate the option prices in the file using the local vol. Compare with the market prices you downloaded. What can you observe?</li>

 <li>Combine and present the results in a table with the following columns: time to maturity, strike price, option market price, implied volatility, local volatility, price obtained using Dupire’s local volatility. You should consider only the outputs corresponding to the pairs (<em>K<sub>i</sub>,T<sub>j</sub></em>), not the interpolated values. Comment on your findings. Also, produce a new file, SPXvolatility.xls, that would add the following columns to the existing ones: implied volatility, local volatility, Black–Scholes price, and the prices obtained using Dupire’s local volatility.</li>

 <li>Download using the Bloomberg terminal option data for an equity of your choice. You should consider at least 5 different maturities and 20 strike prices. Construct an Excel file with the same structure as SPX.xls. Repeat the parts (a)–(f) using your file. Note that you need to proper implement all the parts above, to make sure that your code will work with the new file. Also, the code that you submit will be tested with our file having the same structure as SPX.xls, for which the results are known. To get full credit in this questions, your results should match with the correct ones.</li>

</ul>