# Expiration Price Option Model

The model allows users to calculate daily amortization amount using total number of amortization dates and amortization of the initial premium based on the specified amortization history.

In that model, the daily amortization amount   is calculated as

	 	(1)

and is used in computing amortization of the initial premium  , where f is equal to 1/365 or 1/360 depending on the choice of day count convention.  Now we allow users to calculate   using total number of amortization dates N if specified, which is given by

	 .	(2)

In the original model,   is obtained as

	 	(3)

where d is the number of days from amortization start date to the immediate proceeding amortization before the value date.  A new feature now allows users to specify an amortization history file, which is for cases when the customer changed the notional of the trade so that new daily amortization amounts should be applied in computing  , given by

	 	(4)

where  ,   are the historical daily amortization amounts from the amortization start date to the immediate proceeding amortization prior to the value date.  In a amortization history file, if no daily amortization amount is specified for a particular amortization date, the most recent daily amortization amount should be used.

Pricing of EPO is trivial.  In general, the call and put prices are respectively given by

	 	 (5)
	 .	 (5)

There is no randomness involved in calculation.

An Expiration Price Option (EPO) is an option with a knock-out feature. At any time, if the option value is equal or less than a specified barrier price, the writer of the option will provide notification to the option holder. The option holder can either

•	Pay an additional premium to prevent the option from knocking-out. The additional premium is equal to the difference between initial premium and the option value at the time of notification.
•	Pay nothing to allow the option to be knocked out. The writer pays the option holder an amount equal to
max (0, premium paid -amortization of the initial premium + stock return) for a call 
and
max (0, premium paid -amortization of the initial premium -stock return) for a put.
The notation used is as follows:

Pi:  initial premium
Pa: additional premium
S:  stock price
K:  option strike
ra:  amortization ratio
di:  i = 1,…, n dividends payment dates
Ci: i = 1,…, n dividends payment amounts
ti:  i = 1, ..., m amortization dates

We use I1, I2 and I3 to denote the terms premium paid, amortization of the initial premium, stock return respectively. We have 
1. 11 = Pi + Pa
2.  , where d is the number of days from amortization start date to the immediate proceeding amortization before value date, f = 1/365 or 1/360 depending the choice of day count convention.
3. I3 = S + dividends amount – K, where dividends amount is the sum of dividends
from first amortization date to value date.
4. The value date should always be bigger or equal to first amortization date.

Reference:
https://finpricing.com/lib/IrInflationCurve.html



