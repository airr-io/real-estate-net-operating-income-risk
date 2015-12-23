# Real Estate Net Operating Income Risk

Risk model accessible on http://app.airr.io remotely by registered users.

## Documentation

This template is made of four tabs:

* [Risk Factor](#risk_factor)
* [Cash Flows](#cash_flows)
* [Discount Rate](#discount_rate)
* [Simulation Settings](#simulation_settings)

###<a name="risk_factor"></a>Risk Factor

This template supports one risk factor in the form of a [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion).

<p><a href="https://commons.wikimedia.org/wiki/File:GeoBM.png#/media/File:GeoBM.png"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/GeoBM.png/1200px-GeoBM.png" alt="GeoBM.png"></a><br>"<a href="https://commons.wikimedia.org/wiki/File:GeoBM.png#/media/File:GeoBM.png">GeoBM</a>" by <a href="//commons.wikimedia.org/wiki/User:Arthena" title="User:Arthena">Arthena</a> - <span class="int-own-work" lang="en" xml:lang="en">Own work</span>. Licensed under <a href="http://creativecommons.org/licenses/by-sa/3.0" title="Creative Commons Attribution-Share Alike 3.0">CC BY-SA 3.0</a> via <a href="https://commons.wikimedia.org/wiki/">Commons</a>.</p>


![alt text](img/risk_factor.png)

###<a name="cash_flows"></a>Cash Flows

The Cash flows are the financial objects the risk engine will simulate.
This template tells the engine that the NOI component should take, at the first 5 annual steps, the corresponding value of the risk factor.

![alt text](img/cash_flows.png)

###<a name="discount_rate"></a>Discount Rate

![alt text](img/discount_rate.png)

###<a name="simulation_settings"></a>Simulation Settings

![alt text](img/simulation_settings.png)
