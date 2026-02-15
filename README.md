# On-Chain DAO Governance Platform

A fully decentralized governance system developed using Solidity, Hardhat, and OpenZeppelin.

This project implements a complete DAO lifecycle including proposal creation, token-weighted voting, timelocked execution, and treasury management — all executed entirely on-chain.

## Key Highlights

ERC20 governance token with snapshot-based voting power

Fully on-chain proposal and voting mechanism

Timelock contract for delayed execution

Secure treasury controlled only through governance

Support for off-chain vote verification

End-to-end tested governance workflow

Solidity IR optimization enabled for large contracts

# System Architecture
## Smart Contracts Overview
Contract Name	Purpose
GovernanceToken.sol	ERC20 token with delegated voting (ERC20Votes)
GovernorCore.sol	Handles proposal lifecycle, voting & quorum
TimelockController.sol	Enforces execution delay for approved proposals
DAOTreasury.sol	Stores ETH and executes transfers via governance
## Governance Lifecycle

Token holders delegate voting power to themselves or others

A proposal is submitted

Voting period begins

Votes are counted and quorum is validated

Off-chain vote attestations are verified

Successful proposals are queued in the Timelock

After delay period, proposal execution is allowed

Treasury or contract action is executed

# Core Design Choices
## Timelock Integration

Prevents immediate execution after approval

Allows community reaction time

Adds security layer against governance attacks

## ERC20Votes Mechanism

Uses historical snapshots for vote counting

Prevents flash-loan governance manipulation

Industry-standard governance model

## Solidity viaIR Compilation

Reduces contract bytecode size

Necessary for complex Governor contracts

Improves deployment feasibility

## Technology Stack

Solidity 0.8.20

Hardhat

OpenZeppelin Contracts v4.9.5

Ethers.js v6

Mocha & Chai (Testing Framework)

## Project Setup
git clone <your-repository-url>
cd dao-governance-platform
npm install

### Compile Smart Contracts
npx hardhat compile

### Local Deployment
npx hardhat run scripts/deploy.js


Expected output:

GovernanceToken deployed at: ...
TimelockController deployed at: ...
GovernorCore deployed at: ...
DAOTreasury deployed at: ...
Deployment completed successfully.

## Run Tests
npx hardhat test


Test coverage includes:

Token delegation

Proposal submission

Voting process

Timelock queue & execution

Treasury ETH transfer

Expected result:

1 passing

## Security Architecture

Treasury ownership assigned to Timelock

Only Governor contract can propose actions

Admin privileges revoked post-deployment

Snapshot voting prevents governance exploits

## Future Enhancements

React-based frontend governance dashboard

DAO analytics panel

Multisig vote validation

Quadratic voting mechanism

On-chain proposal metadata storage

Token staking integration

📚 Learning Outcome

This project demonstrates:

Advanced smart contract architecture

Secure governance design patterns

Timelock-based execution security

Real-world DAO implementation principles