# Flash Loan Arbitrage Core 💸

![Solidity](https://img.shields.io/badge/Solidity-%5E0.8.10-363636) ![Hardhat](https://img.shields.io/badge/Built%20With-Hardhat-yellow) ![Aave](https://img.shields.io/badge/Protocol-Aave%20V3-purple)

## Introduction
This repository contains the smart contracts and execution scripts required to perform **Atomic Flash Loan Arbitrage**. 

The logic borrows assets from the Aave Liquidity Pool without collateral, executes a trade on a decentralized exchange (DEX) where the price is lower, sells on a DEX where the price is higher, repays the loan + premium, and keeps the profit—all within a single transaction block.

## Key Features
- **Zero Risk Execution:** If the trade is not profitable, the transaction reverts (fails), costing only gas fees.
- **Aave V3 Integration:** Uses the latest `flashLoanSimple` interface.
- **Mainnet Forking:** Test strategies on real mainnet state without spending real ETH.

## Architecture
1. **FlashLoanReceiver.sol**: The contract that receives the loaned funds.
2. **Arbitrage Logic**: Swaps tokens on Uniswap/SushiSwap.
3. **Bot**: Node.js script to trigger the contract when an opportunity is found.

## Setup & Deployment

1. **Install Dependencies**
   ```bash
   npm install
