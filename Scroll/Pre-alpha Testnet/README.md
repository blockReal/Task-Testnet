
<p align="center">
  <h1>Task</h1>
</p>

![1](https://github.com/blockReal/Task-Testnet/assets/96944994/b484f38f-7a19-49f3-9d69-4c0db559a2a2)

1. <a href="https://scroll.io/portal">Configure </a>

![3](https://github.com/blockReal/Task-Testnet/assets/96944994/d463fc1f-f60b-4835-8d25-d5ad33287e7f)


2. <a href="https://scroll.io/bridge">Bridge</a> Any Amount

![2](https://github.com/blockReal/Task-Testnet/assets/96944994/48dbae02-b883-42d8-92e4-cbc8153c5b6a)


3. Create <a href="https://remix.ethereum.org/">Contract</a> Test.sol

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;

contract FunctionTypes {
    uint256 public number = 5;

    constructor() payable {}

    // Function Types
    // function (<parameter types>) {internal|external} [pure|view|payable] [returns (<return types>)]
    // Default function
    function add() external {
        number = number + 1;
    }

    // Pure function
    function addPure(uint256 _number) external pure returns (uint256 new_number) {
        new_number = _number + 1;
    }

    // View function
    function addView() external view returns (uint256 new_number) {
        new_number = number + 1;
    }

    // Internal function
    function minus() internal {
        number = number - 1;
    }

    // The functions within the contract can call internal functions
    function minusCall() external {
        minus();
    }

    // Payable function: a function that can receive ETH to the contract
    function minusPayable() external payable returns (uint256 balance) {
        minus();
        balance = address(this).balance;
    }
}
```
