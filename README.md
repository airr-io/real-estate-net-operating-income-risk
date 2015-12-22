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

### NOI

### Net_result

|expected value|
|-------------:|
|53.57|

|histogram|bin edges|
|-:|-:|
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
|67|52.29|
|79|52.34|
|92|52.38|
|123|52.43|
|175|52.47|
|187|52.52|
|267|52.57|
|325|52.61|
|410|52.66|
|447|52.7|
|529|52.75|
|671|52.8|
|792|52.84|
|814|52.89|
|916|52.93|
|1124|52.98|
|1248|53.03|
|1267|53.07|
|1357|53.12|
|1521|53.16|
|1534|53.21|
|1674|53.26|
|1603|53.3|
|1734|53.35|
|1789|53.39|
|1821|53.44|
|1808|53.49|
|1749|53.53|
|1747|53.58|
|1665|53.62|
|1740|53.67|
|1631|53.72|
|1562|53.76|
|1432|53.81|
|1361|53.86|
|1311|53.9|
|1210|53.95|
|1129|53.99|
|1026|54.04|
|923|54.09|
|854|54.13|
|758|54.18|
|681|54.22|
|645|54.27|
|588|54.32|
|494|54.36|
|455|54.41|
|362|54.45|
|292|54.5|
|266|54.55|
|228|54.59|
|201|54.64|
|184|54.68|
|167|54.73|
|153|54.78|
|124|54.82|
|104|54.87|
|84|54.91|
|59|54.96|
|52|55.01|
|46|55.05|
|43|55.1|
|32|55.14|
|28|55.19|
|16|55.24|
|24|55.28|
|16|55.33|
|7|55.37|
|11|55.42|
|6|55.47|
|6|55.51|
|4|55.56|
|2|55.6|
|9|55.65|
|1|55.7|
|1|55.74|
|0|55.79|
|1|55.83|
|2|55.88|
|1|55.93|
|2|55.97|
|0|56.02|
|0|56.06|
|1|56.11|
|2|56.16|
|0|56.2|
|0|56.25|
|0|56.29|
|0|56.34|
|1|56.39|
||56.43|




Running the model on [airr] (http://app.airr.io) provides the following [here] (https://github.com/airr-templates/evca-fund-growth-method/blob/master/examples/real_estate_rental_income_risk_output.xlsx?raw=true).
