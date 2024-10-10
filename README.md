# Solidity Token
This Solidity program demonstrates a simple implementation of a token on the Ethereum blockchain. It highlights basic concepts such as public variables, mapping, and functions for minting and burning tokens. The program serves as an excellent starting point for those who are new to Solidity and want to understand how token creation and management work in smart contracts.

## Description
This program is a basic token contract written in Solidity, used for creating and managing a token named "APPLE" with the abbreviation "APL". The contract allows users to mint new tokens, adding them to an address's balance and the total supply. It also provides a burn function to destroy tokens, reducing both the total supply and the balance of the specified address. This contract introduces core functionality commonly found in token contracts, including state variables, mappings, and simple token management.

## Getting Started
### Executing Program
To run this program, you can use Remix, an online IDE for Solidity development. Follow the steps below to execute the program:

Visit the Remix IDE website at Remix Ethereum.
Create a new file by clicking on the "+" icon in the left-hand sidebar, and save the file with a .sol extension (e.g., myToken.sol).
Copy and paste the following code into your new file:
```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract myToken {

    // public variables here
    string public tokenName = "APPLE";
    string public tokenAbbrv = "APL";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```
To compile the code, go to the "Solidity Compiler" tab in the left-hand sidebar. Set the "Compiler" version to 0.8.18, then click on the "Compile myToken.sol" button.
Once the code is compiled, navigate to the "Deploy & Run Transactions" tab. Select the myToken contract from the dropdown menu, and click on the "Deploy" button.
After deployment, you can mint and burn tokens by interacting with the mint and burn functions:
To mint tokens, enter the recipient's address and the amount to mint.
To burn tokens, input the address and the amount of tokens to burn (ensuring the address has enough tokens).
## Authors
Metacrafter Charles_shiro


## License
This project is licensed under the MIT License - see the LICENSE.md file for details.
