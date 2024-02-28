# CCI-Corrected

Developer's Site: [forexroboteasy.com](https://forexroboteasy.com)

Developer: Forex Robot Easy Team

---

## Description

The CCI-Corrected indicator is a technical analysis tool that calculates the Commodity Channel Index (CCI) corrected values for each bar. The CCI is a momentum-based oscillator that measures the current price level relative to an average price level over a specified period of time. The CCI-Corrected indicator provides a more accurate representation of the CCI values by taking into account the mean deviation of the typical price.

For detailed reviews and trading results of this product, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/cci-corrected-review-enhanced-forex-software-solution/). Please note that ForexRobotEasy is not the official developer of this product. We only provide sample code that can work as described in this product. To find the official developer of this product, please refer to MQL5.

---

## Global Variables

- `cciCBuffer[]`: Buffer to store CCI-C values
- `period`: Default period for CCI-C calculation

---

## Initialization

The `OnInit()` function is called during the initialization of the indicator. It performs the following tasks:

1. Initializes the `cciCBuffer` array with the size of `Bars - period`.
2. Sets the indicator label to 'CCI-C' using the `IndicatorSetString()` function.
3. Sets the period for CCI-C calculation using the `SetCCIPeriod()` function.

---

## Deinitialization

The `OnDeinit()` function is called during the deinitialization of the indicator. It clears the `cciCBuffer` array by initializing all elements to 0 using the `ArrayInitialize()` function.

---

## CCI-C Calculation

The `OnCalculate()` function is called for each new tick or bar. It calculates the CCI-C values for each bar based on the input price data. The calculation is performed as follows:

1. Calculates the typical price for the current bar using the formula: `(high[i] + low[i] + close[i]) / 3`.
2. Calculates the simple moving average (SMA) of the typical price over the specified period using the `SimpleMovingAverage()` function.
3. Calculates the mean deviation of the typical price over the specified period using the `MeanDeviation()` function.
4. Checks if the mean deviation is 0 to handle the division by zero error.
5. Calculates the CCI-C value using the formula: `(typicalPrice - sma) / meanDeviation`.
6. Stores the CCI-C value in the `cciCBuffer` array.

After calculating the CCI-C values, the function draws the values on the chart using the `IndicatorBufferSet()` function. It connects the current bar with the last calculated CCI-C value or the previous bar's CCI-C value.

---

## Set CCI-C Period

The `SetCCIPeriod()` function is used to set the period for CCI-C calculation. It updates the `period` variable and sets the `INDICATOR_DIGITS` property of the indicator to the new period using the `IndicatorSetInteger()` function.

---

## Simple Moving Average

The `SimpleMovingAverage()` function calculates the simple moving average of a given price over a specified period. It sums the price values over the period and divides the sum by the period to calculate the average.

---

## Mean Deviation

The `MeanDeviation()` function calculates the mean deviation of a given price over a specified period. It calculates the absolute difference between the price and the simple moving average for each period and sums the differences. The sum is then divided by the period to calculate the mean deviation.

---

For more information and usage instructions, please refer to the official developer of this product through MQL5.
