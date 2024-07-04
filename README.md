# soliditymeta1

# Project Title

Solidity code
In this respository we have created a program which is just basic code of soldity. 

## Description

1. The MyToken contract declaration is initiated by this program.

2.Three state variables are declared in these lines:
Name: The token's name is represented via a public string variable.
Symbol: The token's symbol is represented via a public string variable.
totalSupply: The total supply of the token is represented by this public unsigned integer variable. It has a zero initialization.

3.The public state variable balances, which maps addresses to unsigned integer, is declared on this line. We will use this mapping to monitor each address's token balance.

4. The mint function enables the production of fresh tokens. It requires the following two parameters:
_address: The address that will be used to receive the freshly created tokens.
_value: The quantity of tokens to be struck.
Within the operation:
totalSupply += _value; this adds _value to the total supply of tokens.
balances[_address] += _value; this adds _value to the balance of _address.

5. Using the burn function in this contract we can easily burn the tokens. It requires the following two parameters:
Tokens will be destroyed from the address indicated by _address.
_value: The number of tokens to be destroyed.
Within the operation:
If the value of balances[_address] >= _value, then the _address has insufficient tokens to burn.
TotalSupply -= _value; reduces the total supply of tokens by _value if the condition is true.
balances[_address] -= _value; this reduces _address's balance by _value.

## Getting Started

### Executing program

To run this program, you can use Remix. Create a new file in remix and paste the code and then find compile on the left hand side of online compiler.
This code is written in solidity version 0.8.26 [remember to check your version].

// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;
contract MyToken {

    string public Name = "Muskan Soni";
    string public Symbol = "Muski";
    uint public totalSupply = 0;

    mapping(address=> uint) public balances;

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }


    function burn(address _address, uint _value) public {
        if(balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
    }
    } 
}


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
