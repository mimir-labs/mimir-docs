# Advanced - Time Delayed Proxy

Users can add a layer of security to proxies by giving them a delay time. The delay will be quantified in blocks. Polkadot has approximately 6 seconds of block time. A delay value of 10 will mean ten blocks, which equals about one minute delay.

The proxy will announce its intended action and will wait for the number of blocks defined in the delay time before executing it. Within this time window, the intended action may be canceled by accounts that control the proxy.
