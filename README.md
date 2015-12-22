# Real Estate Net Operating Income Risk

Risk model accessible on http://app.airr.io remotely by registered users.

## Usage

1. Upload a model file. Use the latest [template] (https://raw.githubusercontent.com/advicelogic/evca-fund-growth-method/master/template.xlsx).
2. Download the risk engine output file(s).

## Template

### Risk Factor

This model supports the [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion).
A process is defined for the NOI with the following:

|name    | type | initial value |  drift | sigma |
|-------:|-----:|--------------:|-------:|------:|
| NOI_gbm |   gbm|             1 | 0.1375 |  0.06 |


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

Running the model on [airr] (http://app.airr.io) provides the following [here] (https://github.com/airr-templates/evca-fund-growth-method/blob/master/examples/real_estate_rental_income_risk_output.xlsx?raw=true).
