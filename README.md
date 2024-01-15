# ultimate_forex_trade_bot

_Project Brief_
    
    This is a project to test the trading index boosting algorithm combined with level(previous high, low on daily time frame)
    This portion need to be tested:
    1. CNN(convolutional neural network) graph detection approach // do not recommend
    2. Price action approach (bar activity, algorithm can be very dynamic and very challenging, but pretty correct, similar to human made decision)
    3. interpolation approach.
    These will be in seperated files

    The strategy's rebalancing frequency is very low.
    It is simply that we would like to test when to not hold or short nasdaq QQQ. 
    It is observed that in volatile market, we tend to discover that 
    [vol1 and Price+, vol2 > vol1 and Price +, vol3 > vol1 and similar to vol2 and Price -]
    when price approaches or above previous high can lead to a reversal to lower level.
    
    The reversal trend tends to stop at several conditions:
    1. when approaching lower level(except for previous high)and
        a). enlarged volume with a star bar
        b). rejection pattern when price approach previous level (reach and bump back)
    2. if bar breach below previous value (large price change between open and close and overlap the level):
        a). any star bar
        b). any shrink volume decrease pattern where the immediate last volume is smaller than half of the starting half
    
    There can also be false signals, but since we only put short holdings on occational cases(still need to be determined)
    We will re-enter as long as there is enlarged volume with two sequential price increment where (close-open)/(high-low) > 1/2

_Potential Directions_
    1. Different market regimes tends to have different patterns. Partitioning the market maybe can work.
    
    2. Different volatility may be combined with different likelyhood of breaking previous level. 
       Thus volitility prediction as predicting shorting opportunity can be a potential direction. 
       Predicted opportunities combined with existing cases can be used to optimize maximize return and minimize max draw down of shorting position. 
    
    3. Decision tree can be something worth trying on making the decision. BUt this can be a validating signal.

