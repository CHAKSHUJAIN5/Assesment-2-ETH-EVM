# Solidity Contract

This is a contract written in solidity, using basic functions and some variables to store the information of token requied to fulfil the contract

## Description

This Solidity contract defines a simple token named "MyToken" with the abbreviation "MTK". It includes functionalities to mint and burn tokens. The contract tracks the total supply of tokens and maintains balances for different addresses using a mapping. The `mint_token` function allows creating new tokens, increasing both the total supply and the balance of the specified recipient. The `burn_token` function enables destroying tokens, provided the recipient has a sufficient balance, reducing both the total supply and the balance of the recipient.

## Getting Started

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., First.sol). Copy and paste the following code into the file:

```javascript
pragma solidity ^0.8.18;

contract MyToken {

    string public token_name;
    string public token_abbrv;
    uint256 public total_supply;

    mapping(address => uint256) public balances;

    function mint_token (address recipient, uint256 amount) public {
        total_supply += amount;
        balances[recipient] += amount;
    }

    function burn_token (address recipient, uint256 amount) public {
        uint256 senderBalance = balances[recipient];
        if (senderBalance >= amount) {
            total_supply -= amount;
            balances[recipient] -= amount;
        }
    }   
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to any compiler with version equal to or greater than 0.8.18 (or another compatible version), and then click on the "Compile First.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "First" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "First" contract in the left-hand sidebar, and then click on the variours function. Finally, click on the "transact" button to execute the function.

## Authors
Chakshu jain

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
