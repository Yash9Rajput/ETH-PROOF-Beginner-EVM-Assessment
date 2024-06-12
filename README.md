Project: Create a Token

In this solidity program we will create a contract "My Token" that will have public variables that store the details about our coin. And the purpose of this program is 
to check the balance of account using mint and burn functions that will work opposite to each other.

Description

This program is a written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. Here we will have public variables that store the details
about our coin (Token Name, Token Abbrv., Total Supply). Our contract will have a mapping of addresses to balances (address => uint). Also we will have a mint function that takes two
parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount. Our contract will also have a burn
function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the
total supply and from the balance of the address. And finally our burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is
supposed to be burned.

Getting Started
Executing Program

To run this program, we use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/

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
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

     // mapping variable here
    mapping(address => uint) public balances;

     // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

     // burn function
     function burn (address _address, uint _value) public{
        if (balances[_address] >= _value) {
           totalSupply -= _value;
           balances[_address] -= _value;
        }
    }

}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the 
"Compile MyToken.sol" button.

Authors

Yash9Rajput
[@RoyalYa46075768](https://x.com/RoyalYa46075768)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
