The data in the .csv files displays the electricity prices in for the type day mentioned in the file name.
Prices are given in euro / kwh in 15-minutes intervalls starting at 06:00.

In the header, the parametrization for the network fees are displayed (factor_network_fees, network_fees[0] and network_fees[1]).
The network fees are calculated as follows:
1) Determine the aggregated maximum load *max_load* in kw and the total consumption *total_cons* in kwh
2) Scale up the consumption to one year by multiplying *total_cons* by 365.25
3) Calculate network fees: factor_network_fees * (network_fees[0} * max_load + network_fees[1] * total_cons)
	(The additional factor accounts for the fact, that not all parts of the network fees are covered in this function such 
	as payments for measuring services)
4) Divide the network fees by 365.25 to get the fees for the particular type day.