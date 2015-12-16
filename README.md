# EVCA Fund growth method

**EVCA Fund growth method** is a template for configuring a risk model accessible
remotely by registered users.

## Access

The model is hosted on http://app.airr.io.

## Usage

1. Upload a model **config** file. Use the latest [template] (https://raw.githubusercontent.com/advicelogic/evca-fund-growth-method/master/template.xlsx).
2. Download the model **output** file.

## Model config variables

| config variable | definition<sup>1</sup> |
| -------------- |------------------------|
| trials | number of paths per simulation |
| sample_size | number of paths for stochastic processes and dependent variables |
| name | reference to the stochastic process |
| drift | ![alt text] (https://raw.githubusercontent.com/advicelogic/vanilla-cash/master/images/mu.png) |
| step | ![alt text] (https://raw.githubusercontent.com/advicelogic/vanilla-cash/master/images/dt.png) |
| sigma | ![alt text] (https://raw.githubusercontent.com/advicelogic/vanilla-cash/master/images/sigma.png) |
| correlation_matrix | rank-order correlation coefficients (optional) |
<sup>1</sup>: Constant definitions refer to their meaning into the corresponding
stochastic process.


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Available stochastic process: [Geometric Brownian motion](https://en.wikipedia.org/wiki/Geometric_Brownian_motion)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![alt text] (https://raw.githubusercontent.com/advicelogic/vanilla-cash/master/images/gbm_equation.png)
## Model output variables

| output variable | definition |
| -------------- |------------------------|
| paths_total | sample of total cash flow paths|
| total_npv_mean | average total cash flow net present value |
| total_npv_histogram | total cash flow net present value distribution |
| paths_total_npv | sample of total cash flow  net present values |
| total_annual_gain_loss_histogram | total cash flow annual gain/loss distribution |
| VaR_1 | 1% percentile of total cash flow annual gain/loss |
| VaR_5 | 5% percentile of total cash flow annual gain/loss |
| paths_cash_flow_*i* | sample of cash flow *i* paths |
