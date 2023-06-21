# EthBeg_Assessment

This solidity program is a program that let's you create your very own token! A basic ERC-20 compatible token contract implemented in Solidity

## Description

This Solidity program defines a simple token contract called MyToken. It allows users to create and transfer tokens on the Ethereum blockchain. The contract follows the ERC-20 standard, providing basic functionalities such as checking balances and transferring tokens between addresses.

## Prerequisites

To interact with the token contract, you will need:

  *- An Ethereum development environment (e.g., Remix, Truffle, or Hardhat).
  *- An Ethereum account with a compatible wallet (e.g., MetaMask) for testing and deploying the contract.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "Metacrafters";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
    // mapping variable here
    mapping (address => uint) public balances;
    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public {
        if(balances[_address]>= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the 'burn' and 'mint'  functions. 

## Authors

Hetashi Guru Singh Pal 
[@gurusinghpal](https://www.linkedin.com/in/guru-singh-pal-99a305254/)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
