MT4-fxLabs (Beta)
=================

The MT4-fxLabs project brings the power of [OANDA Forex Labs](http://fxtrade.oanda.com/analysis/labs/) to [MT4](http://fxtrade.oanda.com/trade-forex/metatrader/). 

![MT4-fxLabs Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-fxlabs.jpg)

You can either use one of several pre-existing custom indicators/scripts in your MT4 client, or you can create your own using the MQL4 API for fxLabs. 

(Please note that this tool is still in beta stages and may undergo changes to its interface.)

## Installation of MT4-fxLabs Tools

### Prerequisites 

* MT4 Client, build 600 or greater. This can be downloaded by following the instructions at OANDA's [MT4 Account Setup](http://fxtrade.oanda.com/trade-forex/metatrader/trade-account-setup) page. 

* .NET3.5 framework. Can be installed as follows:
    * Windows 7/8: Control Panel -> Programs -> Turn Windows Features on or off, navigate to .NET Framework 3.5 entry.
    * Windows XP/Vista/Server2003/Server2008: See instructions at [Microsoft .NET Framework 3.5](http://www.microsoft.com/en-ca/download/details.aspx?id=21)


### Instructions

1. Download [fxlabs-MQL4.zip](https://github.com/oanda/mt4-fxlabs/raw/master/fxlabs-MQL4.zip)

2. In your MT4 Client, click File->Open Data Folder. Copy fxlabs-MQL4.zip to this folder, and unzip. The contents should unzip into the appropriate subdirectories in this folder. 

3. Using Windows File Explorer, go to the MQL4\Libraries subdirectory, right-click on fxlabsnet.dll, and choose 'Properties'. Click the 'Unblock' button if it's present. (If the 'Unblock' button is not there, then don't worry about this step.) 

4. In your MT4 client, select Tools->Options, and navigate to the "Expert Advisors" tab. 
    * Ensure checkboxes for "Allow DLL imports", and "Allow external experts imports" are all checked. 
    * Ensure the checkbox for "Confirm DLL function calls" is NOT checked. 
5. Restart your MT4 client if it is currently running. 

You should now see new entries under the 'Custom Indicators' and 'Scripts' sections of the Navigator panel. The available indicators and scripts are described below. 

## Available Custom Indicators/Scripts

### Indicator: OANDA_Historical_Position_Ratios

![MT4-fxLabs HPR Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-hpr.jpg)

Graph OANDA's historical ratios between long and short positions held by customers. 

Available instruments: AUD/JPY, AUD/USD, EUR/AUD, EUR/CHF, EUR/GBP, EUR/JPY, EUR/USD, GBP/CHF, GBP/JPY, GBP/USD, NZD/USD, USD/CAD, USD/CHF, USD/JPY, XAU/USD, XAG/USD. 

### Indicator: OANDA_Spreads

![MT4-fxLabs Spreads Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-spreads.jpg)

Graph OANDA's historical spread values (ask-bid difference) for an instrument. 

Available instruments: All tradable.

### Indicator: OANDA_Commitments_of_Traders

![MT4-fxLabs COT Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-cot.jpg)

Graph net non-commercial Commitments of Traders data from the [CFTC](http://www.cftc.gov/MarketReports/CommitmentsofTraders/index.htm). 

Available instruments: AUD/USD, GBP/USD, USD/CAD, EUR/USD, USD/JPY, USD/MXN, NZD/USD, USD/CHF, XAU/USD, XAG/USD

### Indicator: OANDA_Orderbook

![MT4-fxLabs Orderbook Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-orderbook.jpg)

Graph OANDA's Orderbook data. See [OANDA Forex Order Book](http://fxtrade.oanda.ca/analysis/forex-order-book) for more details. 

MT4 is limited to how it can show the orderbook data in a price vs time chart window, so the indicator does not display the same as what's on the fxLabs page. It is, however,  based on the same data. 

In particular, the MT4 indicator graphs two bars, similar to the Historical Position Ratios indicator. The top one is the percentage of long orders with trigger prices above the high price of the candle, and the lower bar is the percentage of short orders with trigger prices below the low price of the candle. This is intended to give an idea of how strong market sentiment is that the instrument's price will increase or decrease. 

Available instruments: AUD/JPY, AUD/USD, EUR/AUD, EUR/CHF, EUR/GBP, EUR/JPY, EUR/USD, GBP/CHF, GBP/JPY, GBP/USD, NZD/USD, USD/CAD, USD/CHF, USD/JPY, XAU/USD, XAG/USD. 

### Script: fxlabs_calendar_demo

![MT4-fxLabs Calendar Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-calendar.jpg)

Draws markers associated with significant forex calendar headlines overlaid on a chart window.

Available instruments: All tradable.

### Script: fxlabs_hpr_demo

![MT4-fxLabs HPR-Script Screenshot](https://github.com/oanda/mt4-fxlabs/raw/master/images/mt4-hpr-script.jpg)

Similar to the Historical Position Ratio indicator, except it will draw the HPR graph overlaid
on the chart window, instead of drawing the graph in a separate indicator window. 

Available instruments: AUD/JPY, AUD/USD, EUR/AUD, EUR/CHF, EUR/GBP, EUR/JPY, EUR/USD, GBP/CHF, GBP/JPY, GBP/USD, NZD/USD, USD/CAD, USD/CHF, USD/JPY, XAU/USD, XAG/USD. 

## Writing MQL4 Based fxLabs Tools

To write your own fxLabs tools in MT4, add the declaration `#include <fxlabsnet.mqh>` to the beginning of your MQL4 source. The various methods that you can call are documented inline in the fxlabsnet.mqh file. A [tutorial](https://github.com/oanda/mt4-fxlabs/blob/master/TUTORIAL.md) to help you get started is also available. 

___


###### Copyright and License

This software is copyright (c) 2014 by OANDA Corporation and distributed under MIT [License](https://github.com/oanda/mt4-fxlabs/blob/master/LICENSE.md).

###### Disclaimer

This information is for general purposes only. Please note that leveraged trading in Foreign Currency Contracts, precious metals, and CFDs carries a high degree of risk and may not be suitable for everybody. Since you could lose some or all of your deposited funds, you should carefully consider whether trading is appropriate for you in light of your experience, objectives, financial resources, and appetite for such risk. The services and content on this page should not be construed as a solicitation to invest and/or trade. You are solely responsible for determining whether forex trading or a particular transaction is suitable for you and for seeking professional advice.
