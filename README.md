# Company Valuation Notebook

This Jupyter Notebook is designed to perform a company valuation based on a set of financial inputs and assumptions. The notebook calculates various financial metrics and ultimately provides the value per share of the company. It is an extension of Damodaran's fcffsimpleginzu spreadsheet. As of now, only default assumptions are at play and key metrics like cost of capital needs to be entered manually. I will try to a provision of that too in the future

## Inputs
The inputs required for this valuation are provided in the below section of the notebook. These inputs include:

- Revenue growth rate for year 1 (`rev_gr_1`)
- Compound Annual Growth Rate (CAGR) for years 2-5 (`cagr_2_5`)
- Risk-free rate (`risk_free_rate`)
- Revenue for the last 12 months (`rev_r12m`)
- EBIT for the last 12 months (`ebit_r12m`)
- R&D amortization years (`rnd_amr_yrs`)
- Current R&D (`curr_rnd`)
- Previous R&D (`prev_rnd`)
- Target Pre-tax Operating margin (`tgt_ebit_margin`)
- Years to convert to target margin (`yr_conv_margin`)
- Effective tax rate (`eff_tx_rate`)
- Marginal tax rate (`mar_tax_rate`)
- Sales to capital ratio for years 1-5 (`sales_to_cap_1_5`)
- Sales to capital ratio for years 6-10 (`sales_to_cap_6_10`)
- Mature market Equity Risk Premium (ERP) (`mature_market_erp`)
- Country ERP (`country_risk_premium`)
- Cost of capital (`cost_of_capital`)
- Probability of failure (`prob_failure`)
- Book value of debt (`book_val_debt`)
- Cash and marketable securities (`cash`)
- Non-operating assets (`non_op_assets`)
- Minority interests (`minority_interests`)
- Shares outstanding (`shares_out`)

## Description
This notebook performs the following calculations:

1. **Growth Rates**: Calculates the growth rates for the next 10 years.
2. **Revenues**: Projects the revenues for the next 10 years based on the growth rates.
3. **Amortization Weights**: Calculates the amortization weights for R&D expenses.
4. **Value of Research Asset**: Computes the value of the research asset.
5. **Adjusted EBIT**: Adjusts the EBIT for R&D expenses.
6. **Operating Margins**: Projects the operating margins for the next 10 years.
7. **Operating Income**: Calculates the operating income (EBIT) for the next 10 years.
8. **Tax Rates**: Projects the tax rates for the next 10 years.
9. **EBIT(1-tax)**: Calculates the after-tax EBIT for the next 10 years.
10. **Reinvestment**: Computes the reinvestment required for the next 10 years.
11. **Free Cash Flow to Firm (FCFF)**: Calculates the FCFF for the next 10 years.
12. **Cost of Capital**: Projects the cost of capital for the next 10 years.
13. **Discount Factors**: Computes the discount factors for the next 10 years.
14. **Present Value of FCFF**: Calculates the present value of FCFF for the next 10 years.
15. **Terminal Year Calculations**: Computes the terminal value and its present value.
16. **Valuation**: Calculates the value of operating assets, equity, and value per share.

## Default assumptions
1. In stable growth, I will assume that your firm will have a cost of capital similar to that of typical mature companies
2. I will assume that your firm will earn a return on capital equal to its cost of capital after year 10. I am assuming that whatever competitive advantages you have today will fade over time.
3. I will assume that your firm has no chance of failure over the foreseeable future.
4. I assume that reinvestment in a year translates into growth in the next year, i.e., there is a one year lag between reinvesting and generating growth from that reinvestment.
5. I will assume that your effective tax rate will adjust to your marginal tax rate by your terminal year. If you override this assumption, I will leave the tax rate at your effective tax rate.
6. I will assume that you have no losses carried forward from prior years ( NOL) coming into the valuation. If you have a money losing company, you may want to override this.
7. I will asssume that today's risk free rate will prevail in perpetuity. If you override this assumption, I will change the riskfree rate after year 10. (**Override feature unavailable as of now**)
8. I will assume that the growth rate in perpetuity will be equal to the risk free rate. This allows for both valuation consistency and prevents "impossible" growth rates.
9. I have assumed that none of the cash is trapped (in foreign countries) and that there is no additional tax liability coming due and that cash is a neutral asset.

