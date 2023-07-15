<p align="center"> <h1>BASE : EARLY COMMEMORATIVE</h1></p>
<p align="center">
  <img src="https://avatars.githubusercontent.com/u/108554348?s=200&v=4" alt="BASE">
</p>

<p align="center">
  <a href="https://base.org/">Official</a> |
  <a href="https://twitter.com/buildonbase">Twitter</a> |
  <a href="https://discord.com/invite/buildonbase">Discord</a> |
  <a href="https://github.com/base-org">Github</a> 
</p>


## BASE Description
Base is a secure, low-cost, builder-friendly Ethereum L2 built to bring the next billion users onchain.

<p align="center">
  <h1>Reward : EARLY COMMEMORATIVE NFT </h1>
</p>


## Task Testnet

## 1. Connect Metamask to Chain <a href="https://chainlist.org/chain/84531 ">BASE</a>  


## 2. <a href="https://bridge.base.org/deposit">Bridge</a> Any Amount

<p align="center">
  <img src="https://i.ibb.co/nLQh7wG/1.png" alt="BASE">
</p>

## 3. Create <a href="https://remix.ethereum.org/">Contract</a> `Test.sol` Change `Name Contract` and `Ticker`

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.9;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract DeployBaseTest is ERC721, Ownable {
    constructor() ERC721("DeployBaseTest", "BASIS") {}

    function safeMint(address to, uint256 tokenId) public onlyOwner {
        _safeMint(to, tokenId);
    }
}
```

- Deploy & Copy contract address import to metamask
