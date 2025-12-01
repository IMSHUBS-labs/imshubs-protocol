# IMSHUBS Architecture Specification

## Overview

IMSHUBS uses a modular, event-driven architecture designed for gas efficiency on L2 networks while enabling rich off-chain data storage for comprehensive reputation history.

## Core Contracts

### 1. Profile Contract
Manages sovereign user identity with censorship-resistant data storage.

**Storage Model:**
- On-chain: Minimal mapping (address → profileURI)
- Off-chain: Profile data stored on IPFS/Arweave

**Key Functions:**
- `createProfile(string memory _username, string memory _profileURI)`
- `getProfile(address _user) returns (string memory)`
- `updateProfile(string memory _newProfileURI)`

### 2. Reputation Contract
Handles portable reputation with explicit V2 expansion design.

**Storage Strategy:**
- On-chain: uint256 reputation score (gas-optimized)
- Off-chain (V2): Full transaction history on Arweave via `contextHash`

**V2-Ready Event Structure:**
```solidity
event ReputationUpdated(
    address indexed user,
    int256 delta,
    bytes32 contextHash,  // IPFS/Arweave hash of transaction context
    uint256 timestamp,
    address indexed initiatedBy
);
Key Functions:

getReputation(address _user) public view returns (uint256)

_updateReputation(address _user, int256 _delta, bytes32 _contextHash) internal

getReputationHistory(address _user) public view returns (bytes32[] memory) (V2)

3. Escrow Contract
Implements non-custodial, trust-minimized escrow with dispute resolution.

States:

Created - Initial state

Funded - Buyer has deposited funds

Completed - Successful transaction

Disputed - In resolution

Resolved - Final outcome determined

Key Functions:

createEscrow(address _counterparty, uint256 _amount, bytes32 _termsHash)

fundEscrow(uint256 _escrowId) payable

release(uint256 _escrowId)

raiseDispute(uint256 _escrowId, string memory _reason)

resolveDispute(uint256 _escrowId, address _winner)

Gas Optimization Features
Minimal Storage: Only essential data on-chain

Event-Driven Logging: Expensive data emitted as events for off-chain processing

Batch Operations: Where applicable

L2 Native Design: Optimized for Polygon/Arweave/Arbitrum fee structures

V2 Integration Pathway
Arweave Indexer Service
A dedicated service will:

Listen for ReputationUpdated events

Fetch context data using contextHash

Structure into readable reputation entries

Upload to Arweave for permanent storage

Maintain queryable index for dApps

Context Data Structure
json
{
  "transactionId": "0x...",
  "dApp": "MarketplaceX",
  "action": "successful_escrow",
  "amount": "1.5 ETH",
  "counterparty": "0x...",
  "timestamp": 1234567890,
  "outcome": "completed"
}
Security Considerations
Time-locked dispute periods

Multi-sig governance for parameter updates

Gradual reputation decay for inactivity

Sybil resistance through stake requirements (future)

Deployment Strategy
Testnet: Full functionality with mock tokens

Mainnet L2: Production deployment on Polygon/Arbitrum

Cross-Chain: LayerZero/CCIP integration for multi-chain reputation

This architecture is designed to evolve. Join our Discord to contribute to its development.
