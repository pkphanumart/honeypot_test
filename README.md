# honeypot_test
SwapEthtoToken then swap the token to ETH to prevent honey pot.

The contract used to interact with Router for swaping ETH for
token then swap 0.1% received token to ETH and send to caller.

If the token is honeypot the transaction may fail, cost only
gas free.

    function ctBuyTokens( address _tokenOut, uint256 _slippage, address _to)
    _tokenOut : Token address to swap eth for.
    _slippage : Slippage percentage. The msg.value is used to calculate amountOut using getAmountsOut router's API.
                AmountOutMin of function swapExactETHForTokens will be calculated by amountOut * _slippage/100.
    _to       : The address where all the token and ETH is transfered to.
