# Real Estate Net Operating Income Risk

Risk model accessible on http://app.airr.io remotely by registered users.

## Documentation

This template is made of four tabs:

* [Risk Factor](#risk_factor)
* [Cash Flows](#cash_flows)
* [Discount Rate](#discount_rate)
* [Simulation Settings](#simulation_settings)

###<a name="risk_factor"></a>Risk Factor

This template supports the [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion).

![alt text](img/risk_factor.png)

(#some-markdown-heading)
###<a name="cash_flows"></a>Cash Flows

The Cash flows are the financial objects the risk engine will simulate.
This template tells the engine that the NOI component should take, at the first 5 annual steps, the corresponding value of the risk factor.

![alt text](img/cash_flows.png)

###<a name="discount_rate"></a>Discount Rate

![alt text](img/discount_rate.png)

###<a name="simulation_settings"></a>Simulation Settings

![alt text](img/simulation_settings.png)
