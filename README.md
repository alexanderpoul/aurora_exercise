# aurora_exercise
Exercise for Aurora Energy Research

My approach to this exercise is to look at the challenge at two levels, since there are two time intervals to consider (essentially, an 'inner' half hourly interval and an 'outer' daily interval). The approach to handle these was as follows:
1. For the half hourly market, using a simple linear optimisation to determine whether it is better to buy or sell energy, and which half hourly market it is better to buy or sell from/to. This also uses a 'forecast' (model) of future energy prices to inform the decision of whether it is preferable to buy or sell energy in the current interval. 
2. The 'daily' loop is treated as a 'commitment' in each half hourly interval (e.g., energy that must be brought/sold in each interval). A linear minimizer (Powell's method) is used to determine what the optimal commitment should be, on the basis we can buy or sell energy in the half hourly market to support this commitment.
I have assumed I can act as an inter-connector (buy energy from one market, and sell immediately into another). However, I have assumed the amount I can buy/sell from one market is capped (2MW), and that the total the battery can charge / discharge is also capped (2MW). Further comments may be found in the workbook. 

The next steps would be largely improving the efficiency of the code (since it currently works by iteration through time).

Modules used are as follows:
* pandas
* numpy
* scipy.optimize
* matplotlib.pyplot
