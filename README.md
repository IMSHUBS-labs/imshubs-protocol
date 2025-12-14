# IMSHUBS Protocol

![Status](https://img.shields.io/badge/Status-Orange_DAO_Applied-blue)
![Version](https://img.shields.io/badge/Version-Architecture_%2B_Prototype-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

**🚀 Status: Applied to Orange DAO Fellowship (Winter 2026)**

A decentralized, non-custodial protocol for sovereign commerce. IMSHUBS provides the foundational smart contracts for escrow, reputation, and identity, enabling anyone to build trustless, peer-to-peer marketplaces.


## 🎯 Vision: Two-Phase Trust Infrastructure

### Phase 1: The On-Chain Foundation (MVP)
- **Gas-Optimized Portable Reputation** - User-owned reputation scores that travel across all dApps
- **Non-Custodial Escrow** - Secure, trustless payment handling with automated dispute resolution
- **Sovereign Identity** - User-controlled profiles with censorship-resistant data storage

### Phase 2: The Sovereign Reputation Graph (Our Moat)
- **Arweave-Powered History** - Rich, verifiable transaction logs stored permanently off-chain
- **Context-Aware Trust** - Understand *why* a user is trustworthy, not just their score
- **Zero Additional Gas Cost** - Event-driven architecture for rich data without user burden

## 🚧 Current Status: Active Development
**Latest Update:** Architecture refinement with hybrid on-chain/off-chain design
**GitHub Activity:** 100+ commits with 80%+ test coverage on core modules
**Live Prototype:** [imshubs.vercel.app](https://imshubs.vercel.app)
**Next Milestone:** Testnet deployment pending team formation

## 🏗️ Core Architecture

### Smart Contracts
- **`Profile.sol`** - User identity and sovereign profile management
- **`Reputation.sol`** - Portable reputation with V2 event hooks for Arweave integration
- **`Escrow.sol`** - Non-custodial escrow with trust-minimized dispute resolution

### Hybrid Design Pattern
[User] → [dApp/Marketplace] → [IMSHUBS Contracts] --(Emits Event)--> [Arweave Indexer]
| | |
V1: Cheap & Fast V1: Secure & Portable V2: Rich & Verifiable

**V2 Ready:** Contracts emit `contextHash` events designed for seamless Arweave integration, enabling detailed transaction history without increasing gas costs.

## 🛠️ For Developers

### Getting Started
This repository contains:
- Core smart contract interfaces and specifications
- Comprehensive architecture documentation
- Test suites with 80%+ coverage
- Reference implementation patterns

### Integration
1. Review our [Architecture Documentation](/docs/architecture.md)
2. Explore the contract interfaces
3. Join our [Discord](https://discord.gg/UQkSV7xhTT) for technical discussions
4. Check open issues for contribution opportunities

### Tech Stack
- **Smart Contracts:** Solidity (0.8.x+), Hardhat/Foundry
- **Frontend:** React/TypeScript, ethers.js/wagmi
- **Storage:** IPFS/Arweave for censorship-resistant data
- **Testing:** 80%+ coverage, security-first development

## 📚 Resources

- **Website & Demo:** [imshubs.vercel.app](https://imshubs.vercel.app)
- **Litepaper v2.0:** [Read our updated vision](Link to your Google Doc or PDF)
- **Discord Community:** [Join the Discussion](https://discord.gg/UQkSV7xhTT)
- **Twitter:** [Follow for announcements](your-twitter-link)

## 👥 Contributing

We're building in public and welcome contributors at all levels:

### For Solidity Developers
We're actively recruiting a **Lead Solidity Developer** to join our core team. If you're passionate about decentralized commerce, portable reputation systems, and architecting from the ground up, reach out on Discord!

### For All Contributors
- Review and comment on architecture decisions
- Test our prototype and provide feedback
- Help improve documentation
- Share with builders who care about Web3 commerce

### Current Focus Areas
1. Finalizing smart contract architecture
2. Building our core development team
3. Preparing for testnet deployment
4. Growing our builder community

## 🎯 Roadmap

**PHASE 1 – Core team formation & architecture finalization**
- Testnet MVP with reputation and escrow functionality

**PHASE 2 – Mainnet launch on L2 with security audits**
- First marketplace integrations  
- Begin Arweave integration (Phase 2)  
- Reputation system live with early users

**PHASE 3 – Cross-chain expansion and ecosystem growth**
- Arweave-powered reputation graph (V2)  
- DAO governance implementation  
- Token economics and distribution

**PHASE 4 – Scale & Expansion**
- Multi-chain deployment  
- Advanced dispute resolution systems  
- Enterprise-grade features  
- Full decentralization transition


## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

**Building the trust layer for the decentralized economy. Join us.**
