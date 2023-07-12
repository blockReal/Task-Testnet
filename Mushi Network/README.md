<p align="center">
  <img src="https://mushi.network/wp-content/uploads/2023/07/cropped-Black-And-White-Modern-Vintage-Retro-Brand-Logo-1.jpg" alt="Mushi Logo">
</p>

<p align="center">
  <a href="https://mushi.network/">Official</a> |
  <a href="https://mushi.network/docs/">Docs</a> |
</p>

<p align="center">
  <h1>Reward :   <a href="https://mushi.network/docs/airdrop-and-beta-phase-of-the-mushi-protocol/">Confirm</a></h1>
</p>

<p align="center">
  <h1>Task</h1>
</p>

## Mushi Description
Mushi is a protocol completely open to everyone!
Mushi is a completely commission-free protocol, for applicants and for oracles.

## 1. Sending Requests
1. Connet Metamask to Chain <a href="https://chainlist.org/chain/11155111">Sepolia</a>
2. Request <a href="https://faucets.chain.link/">Faucet</a>
3. Create <a href="https://www.infura.io/">Api Key Sepolia</a>
4. Open <a href="https://remix.ethereum.org">Remix</a>
5. Create Contract `Test.sol`
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

<p align="center">
  <img src="https://mushi.network/wp-content/uploads/2023/07/Screenshot-5-1536x758.png" alt="Screen">
</p>


6. Deploy Contract `Test.sol`

## 2. Getting the price of ether in USD

<p align="center">
  <img src="https://mushi.network/wp-content/uploads/2023/06/Screenshot-22.png" alt="Screen">
</p>

Goto Tab `sendRequest`

_url:
```
"https://min-api.cryptocompare.com/data/pricemultifull?fsyms=ETH&tsyms=USD"
```
_path:
```
"RAW,ETH,USD,PRICE"
```
_sender:
```
"Your Wallet"
```
Click `transact`

Goto Tab `getData`
 
_requestId: 
```
"1688858465"
```
 Click `call`

Goto Tab `getRequestId`

_sender: 
```
"Your Wallet"
```
Click `call`

## 3. Getting the ether symbol with CoinGecko API
Goto Tab `sendRequest`

_url:
```
"https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=10&page=1&sparkline=false&locale=en"
```
_path:
```
"1,symbol"
```
_sender:
```
"Your Wallet"
```
Click `transact`

Goto Tab `getData`
 
_requestId: 
```
"1688858709"
```
 Click `call`

Goto Tab `getRequestId`

_sender: 
```
"Your Wallet"
```
Click `call`

## 4. The importance of oracles
1. Download Program Windows <a href="https://www.mediafire.com/file/nefidw4g0ar04ag/MushiSepoliaOracleV1.zip/file)https://www.mediafire.com/file/nefidw4g0ar04ag/MushiSepoliaOracleV1.zip/file">Link</a>
2. Run `MushiOracleV1.exe`
3. Input Api Key Infura
4. Input Wallet Address

<p align="center">
  <img src="https://i.ibb.co/QCScxyr/Capture.png" alt="Screen">
</p>   

## 5. Building an oracle with Python
`Soon Update`

   
