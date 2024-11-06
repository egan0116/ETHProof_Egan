# Minting and Burning Tokens Using Solidity

A simple program that burns and mints tokens made in Solidity

## Description

I made this program as my final project submission for ETHProof: Getting Started with Solidity. It burns and mints tokens named "CatCoin" referencing my previous JSProof final project of minting Cat NFT's. 

## Getting Started

### Executing program

- Copy and paste the code below into your IDE (Preferably, use [Remix](https://remix.ethereum.org/) and create an account for less hassle in installing plug-ins)
- Save the file with the extension ".sol"
- Compile and Deploy the Program
  
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

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
    string public tokenName = "Cat Coin";
    string public tokenAbbrv = "CTC";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint (address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

## Authors

Francis L. Chuegan
[Egan](202111700@fit.edu.ph)


## License

This project is licensed under the [Francis L. Chuegan] License - see the LICENSE.md file for details
