
<p align="center">
  <h1>Task</h1>
</p>

![1](https://github.com/blockReal/Task-Testnet/assets/96944994/b484f38f-7a19-49f3-9d69-4c0db559a2a2)

1. <a href="https://scroll.io/portal">Configure </a>

![3](https://github.com/blockReal/Task-Testnet/assets/96944994/d463fc1f-f60b-4835-8d25-d5ad33287e7f)


2. <a href="https://scroll.io/bridge">Bridge</a> Any Amount

![2](https://github.com/blockReal/Task-Testnet/assets/96944994/48dbae02-b883-42d8-92e4-cbc8153c5b6a)


3. Create <a href="https://remix.ethereum.org/">Contract</a> `TestDeploy.sol`

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
4. Create <a href="https://remix.ethereum.org/">Contract</a> `TestTokenDeploy.sol`
```
// SPDX-License-Identifier: MIT
// WTF Solidity by 0xAA
pragma solidity ^0.8.4;

interface IERC20 {
    event Transfer(address indexed from, address indexed to, uint256 value);
    event Approval(address indexed owner, address indexed spender, uint256 value);

    function totalSupply() external view returns (uint256);
    function balanceOf(address account) external view returns (uint256);
    function transfer(address to, uint256 amount) external returns (bool);
    function allowance(address owner, address spender) external view returns (uint256);
    function approve(address spender, uint256 amount) external returns (bool);
    function transferFrom(address sender, address recipient, uint256 amount) external returns (bool);
}

contract ERC20 is IERC20 {
    mapping(address => uint256) public override balanceOf;
    mapping(address => mapping(address => uint256)) public override allowance;
    uint256 public override totalSupply;
    string public name;
    string public symbol;
    uint8 public decimals = 18;
    address public owner;
    
    constructor(string memory name_, string memory symbol_) {
        name = name_;
        symbol = symbol_;
        owner = msg.sender;
    }
    
    function transfer(address recipient, uint256 amount) external override returns (bool) {
        balanceOf[msg.sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(msg.sender, recipient, amount);
        return true;
    }
    
    function approve(address spender, uint256 amount) external override returns (bool) {
        allowance[msg.sender][spender] = amount;
        emit Approval(msg.sender, spender, amount);
        return true;
    }
    
    function transferFrom(address sender, address recipient, uint256 amount) external override returns (bool) {
        allowance[sender][msg.sender] -= amount;
        balanceOf[sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(sender, recipient, amount);
        return true;
    }
    
    function mint(uint256 amount) external {
        require(owner == msg.sender);
        balanceOf[msg.sender] += amount;
        totalSupply += amount;
        emit Transfer(address(0), msg.sender, amount);
    }
    
    function burn(uint256 amount) external {
        balanceOf[msg.sender] -= amount;
        totalSupply -= amount;
        emit Transfer(msg.sender, address(0), amount);
    }
}
```

![4](https://github.com/blockReal/Task-Testnet/assets/96944994/588ad675-f73b-43b8-a9ae-3a51d28c3b8f)

- After Deploy Success Goto Tab `mint` input 1800000000000000000000 `transac`


- copy contract address then import it to metamask

5. Add <a href="https://uniswap-v3.scroll.io/#/pool">Liquid</a>

![6](https://github.com/blockReal/Task-Testnet/assets/96944994/4882f1d7-abe7-4432-a62b-a089827b01cc)

![7](https://github.com/blockReal/Task-Testnet/assets/96944994/f24b5b65-c7af-4c4e-905d-c3cb79b48303)

