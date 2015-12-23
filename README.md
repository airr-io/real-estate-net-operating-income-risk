#Real Estate Net Operating Income Risk

Risk model accessible on http://app.airr.io remotely by registered users.

##Use Case

Consider a projection made of three *important* real estate
cash flows:

* NOI
* Capital expenses
* Terminal Value

|                  |   eoy1 |  eoy2 |   eoy3 |  eoy4 |   eoy5 |
|------------------|-----:|----:|-----:|----:|-----:|
| NOI              |  1.1 | 1.3 |  1.6 | 1.8 |  2.1 |
| Capital expenses | -0.25 |     | -0.35 |     |    -1 |
| Terminal value   |      |     |      |     | 78.9 |
<sup>(numbers are in $ M)</sup>

The acronym *eoy* stands for *end of year*. This means that, these numbers are
projections of what our investment would make after one year, after two years...

With a [cost of capital](https://en.wikipedia.org/wiki/Cost_of_capital) of say 10%,
we have a [net present value](https://en.wikipedia.org/wiki/Net_present_value),
today, of $53.6M.

Now what about NOI risk.

We have an expected NOI evolution. But, starting from a current value of say $1M,
figuring out some possible evolutions of the NOI, what would be the impact on
our investments performance?

##Configuration

* [Risk Factor](#risk_factor)
* [Cash Flows](#cash_flows)
* [Discount Rate](#discount_rate)
* [Simulation Settings](#simulation_settings)

###<a name="risk_factor"></a>Risk Factor

Lets include uncertainty by defining a [stochastic process](https://en.wikipedia.org/wiki/Stochastic_process)
for the NOI. Currently, this template only supports the [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion).
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

* name : the actual name of the template
* trials : the number of trials the engine will run
* output : the available output files

![alt text](img/simulation_settings.png)

##Output

###statistics

For each cash flow we get:

* expected value : the net present values mean
* histogram : the net present values percentiles
