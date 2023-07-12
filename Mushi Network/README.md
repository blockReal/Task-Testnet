<p align="center">
  <img src="https://mushi.network/wp-content/uploads/2023/07/cropped-Black-And-White-Modern-Vintage-Retro-Brand-Logo-1.jpg" alt="Mushi Logo">
</p>

<p align="center">
  <a href="https://mushi.network/">Official</a> |
  <a href="https://mushi.network/docs/">Docs</a> |
</p>

<p align="center">
  <h1>Task</h1>
</p>

## Mushi Description
Mushi is a protocol completely open to everyone!
Mushi is a completely commission-free protocol, for applicants and for oracles, that’s why we appreciate your support. Thanks to you, developers can access off-chain data for free.

## 1. Sending Requests
1. Request <a href="https://faucets.chain.link/">Faucet</a>
2. Create <a href="https://www.infura.io/">Api Key Sepolia</a>
3. Open <a href="https://remix.ethereum.org">Remix</a>
4. Create Contract `Test.sol`
```
/ SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

    interface IMushi {
        function sendRequest(string memory,string memory, address) external payable;
        function getData(uint256) external view returns (string memory);
        function getRequestId(address) external view returns (uint256);

    }

contract Test{
    address public mushiAddress = 0x5B079d5705788762bed6dDDaF6BF4bB4400Ea1D3;

    address mushi;

    constructor(){
        mushi = mushiAddress;
    }

    function sendRequest(string memory _url, string memory _path, address _sender) public payable{
        IMushi (mushi).sendRequest(_url, _path,_sender);
    }
    function getData(uint256 _requestId) public view returns (string memory){
        return IMushi (mushi).getData(_requestId);
    }
    function getRequestId(address _sender) public view returns (uint256){
        return IMushi(mushi).getRequestId(_sender);
    }
}

```
5. Deploy Contract `Test.sol`

## 2. Getting the price of ether in USD
Goto Tab `sendRequest`
`_url:`
```
	"https://min-api.cryptocompare.com/data/pricemultifull?fsyms=ETH&tsyms=USD"
```
`_path: `
```
	"RAW,ETH,USD,PRICE"
```
`_sender: `
```
	"Your Wallet"
```
 Click `transact`


