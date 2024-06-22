# MyToken Smart Contract

## Overview
`MyToken` is a simple token contract deployed on the Ethereum blockchain. It allows the contract owner to mint and burn tokens and provides functionality for transferring tokens between users.

## Features
- **Minting Tokens:** Only the contract owner can mint new tokens.
- **Burning Tokens:** Only the contract owner can burn tokens.
- **Transferring Tokens:** Any user can transfer tokens to another address.
- **Event Emission:** Emits events for minting, burning, and transferring tokens.

## Contract Details

### Variables
- `name`: The name of the token (default: "simple").
- `symbol`: The symbol of the token (default: "simp").
- `totalSupply`: The total supply of tokens.
- `owner`: The address of the contract owner.
- `balances`: A mapping that stores the balance of each address.

### Events
- `Mint(address indexed to, uint amount)`: Emitted when new tokens are minted.
- `Burn(address indexed from, uint amount)`: Emitted when tokens are burned.
- `Transfer(address indexed from, address indexed to, uint amount)`: Emitted when tokens are transferred.

### Errors
- `InsufficientBalance(uint balance, uint withdrawAmount)`: Thrown when attempting to burn more tokens than available.

### Modifiers
- `onlyOwner()`: Ensures that the function can only be called by the contract owner.

### Functions
- `constructor()`: Initializes the contract and sets the deployer as the owner.
- `mint(address _address, uint _value)`: Mints `_value` amount of tokens to the `_address`. Only callable by the owner.
- `burn(address _address, uint _value)`: Burns `_value` amount of tokens from the `_address`. Only callable by the owner.
- `transfer(address _receiver, uint _value)`: Transfers `_value` amount of tokens from the caller's address to the `_receiver` address.

## Usage

### Deployment
1. Deploy the contract on the Ethereum blockchain.
2. The deployer address will be set as the owner.

### Minting Tokens
The owner can mint new tokens using:
```solidity
mint(address _address, uint _value)
```

### Burning Tokens
The owner can burn tokens from any address using:
```solidity
burn(address _address, uint _value)
```

### Transferring Tokens
Any user can transfer tokens to another address using:
```solidity
transfer(address _receiver, uint _value)
```

## License
This project is licensed under the MIT License.
