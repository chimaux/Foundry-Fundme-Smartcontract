# About

FundMe is a decentralized crowdfunding smart contract built with Solidity and the Foundry framework.
It enables users to fund the contract with ETH while enforcing a minimum USD value using Chainlink price feeds.
The contract owner can securely withdraw funds, and the project includes a full suite of unit tests, mocks, and deployment scripts following the standard Foundry structure.

# Getting started
Clone the Repository
git@github.com:chimaux/Foundry-Fundme-Smartcontract.git
cd foundry-fundme-f25

Install Foundry
curl -L https://foundry.paradigm.xyz | bash
foundryup

Install Dependencies
forge install

# Requirements

Foundry (forge, cast, anvil)

Solidity ^0.8.18

Node provider (Alchemy) for testnet deployment

Git

(Optional) VSCode with Solidity extensions

Verify Foundry installation:

forge --version

# Quickstart
Run a Local Node (Anvil)
anvil

# Deploy the Contract
forge script script/DeployFundMe.s.sol --rpc-url http://127.0.0.1:8545 --broadcast -vvvv

# Interact With the Contract

Fund:

cast send <contract-address> --value 0.1ether

NB: funding restricted to a minimum of $5


Withdraw (owner only):

cast send <contract-address> "withdraw()" --private-key <your-private-key>

Running the Tests

# Running the test

forge test


Run with detailed logs:

forge test -vvv


Generate gas report:

forge test --gas-report