# Real Estate Net Operating Income Risk

Risk model accessible on http://app.airr.io remotely by registered users.

## Usage

1. Upload a model file. Customize the latest [template] (https://raw.githubusercontent.com/advicelogic/real-estate-net-operating-income-risk/master/model.xlsx).
2. Download the risk engine output file(s).

## Template

### Risk Factor

This template supports the [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion).

![Risk Factor](/img/risk_factor.png)

### Cash Flows

The Cash flows are the financial objects the risk engine will simulate.
This template tells the engine that the NOI component should take, at the first 5 annual steps, the corresponding value of the risk factor.

|                  |   y1 |  y2 |   y3 |  y4 |   y5 |
|------------------|-----:|----:|-----:|----:|-----:|
|NOI|NOI_gbm[1]|NOI_gbm[2]|NOI_gbm[3]|NOI_gbm[4]|NOI_gbm[5]|
|Capex|-0.25||-0.35||-1|
|Terminal_value|||||78.9|
|Net_result|NOI[1]+Capex[1]|NOI[2]|NOI[3]+Capex[3]|NOI[4]|NOI[5]+Capex[5]+Terminal_value[5]|

### Discount Rate

| discount rate |
|-----------:|
|       0.10 |


## Output

The risk engines outputs are, for each cash flow:

* statistics : expected value and histogram of net present values
* paths : all simulated paths

### Statistics examples

#### NOI_npv

|expected value|
|-------------:|
|5.69|


|histogram|bin edges|
|--------:|--------:|
|1|3.95|
|1|4|
|2|4.04|
|6|4.09|
|8|4.13|
|12|4.18|
|9|4.23|
|20|4.27|
|28|4.32|
|40|4.36|
|...|...|
|0|8.37|
|0|8.41|
|0|8.46|
|1|8.51|
||8.55|

#### Net_result_npv

|expected value|
|-------------:|
|53.57|

|histogram|bin edges|
|--------:|--------:|
|1|51.83|
|1|51.88|
|2|51.92|
|6|51.97|
|8|52.01|
|12|52.06|
|9|52.11|
|20|52.15|
|28|52.2|
|40|52.24|
|...|...|
|0|56.25|
|0|56.29|
|0|56.34|
|1|56.39|
||56.43|
