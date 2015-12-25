#Real Estate Net Operating Income Risk

Risk model accessible on http://app.airr.io remotely by registered users.

##Use Case

A projection made, in 2015, estimates a real estate's three *important*
cash flows: the net operating income, capital expenses and its terminal value.

|   |2015|   2016 |  2017 |   2018 |  2019 |   2020 |
|---|---:|---:|---:|----:|-----:|----:|
| NOI| |1.1|1.3|1.6|1.8|2.1|
| Capex| |-0.25||-0.35||-1 |
| TV| | | | | |78.9|
| Result| |0.85|1.3|1.25|1.8|75.8|
| NPV@10%|53.6||||||
<sup>(numbers are in $ M)</sup>

While there's some uncertainty in all variables, we have established the NOI
as the risk factor where the range of values is the most significant.

Based on some research the NOI is expected to behave like a [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion) with a annual growth rate of 13.75%
and a volatility of 6%.

To turn the projection into a risk model we can use our template .

##Configuration

* [Risk Factor](#risk_factor)
* [Cash Flows](#cash_flows)
* [Discount Rate](#discount_rate)
* [Simulation Settings](#simulation_settings)

###<a name="risk_factor"></a>Risk Factor

Lets include uncertainty by defining a [stochastic process](https://en.wikipedia.org/wiki/Stochastic_process)
for the NOI. Currently, this template only supports the .
We could give it a try with the following parameters:

* initial value : $1M
* drift : 13.75%
* volatility : 6%


![alt text](img/risk_factor.png)

###<a name="cash_flows"></a>Cash Flows

The Cash flows are the financial objects the risk engine will simulate.

We have to tell the engine that the NOI component should take, at the first 5 annual steps, the corresponding value of the risk factor.

Besides, we will also define a new variable, the Net_result, as the metric
for which we want risk statistics.

![alt text](img/cash_flows.png)

###<a name="discount_rate"></a>Discount Rate

We'll use our cost of capital of 10%.

![alt text](img/discount_rate.png)

###<a name="simulation_settings"></a>Simulation Settings

The template has default values for:

* template : the actual name of the template
* trials : the number of trials the engine will run
* output : the selected output will be produced for each cash flow

Let's go with the defaults.

![alt text](img/simulation_settings.png)

##Output

###statistics

For each cash flow, we have a tab with net present value distribution statistics:

* mean
* histogram
* bin edges

Taking into account a uncertainty for the NOI, we still have our net present value of $53.6M.
*Thats what we call calibration. ;-)*


But, having histograms and distributions, we have risk metrics. And, they tell
us that 95% of the time, the investment would not lose more that $1.6M ($53.6M - $52M).


###paths

For each cash flow a file with the trial values.
