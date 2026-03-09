# 🌿 Ecobond - Blockchain-Based Green Bond Investment Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Democratizing investment in environmental projects. Ecobond enables retail and institutional investors to fund, verify, and track real-world environmental sustainability initiatives on the blockchain.

## Our Mission

We believe in a transparent, measurable, and decentralized future for environmental impact investing. Our platform tokenizes environmental projects and uses a sophisticated ecosystem combining **smart contracts**, **IoT data simulators**, and **Chainlink Compute (CRE) workflows** to ensure every investment is backed by verified, real-world data.

## The Ecobond Ecosystem

Our organization is structured across several key repositories:

#### 1. 🌍 [EcoBond-Backend](https://github.com/Ecobond/EcoBond-Backend) (Main Repository)
The primary orchestrator and entry point for the decentralized backend. This repository ties together the entire ecosystem by linking the smart contracts, IoT data simulation, and Chainlink CRE workflow submodules.
* **Tech Stack**: Git Submodules, Foundry, Bun/Node.

#### 2. 📜 [contracts](https://github.com/Ecobond/contracts)
The core smart contracts layer powering the investment system. It features a unique dual-token architecture:
- `InvestmentMod` (ERC-4626 Vault) for managing USDC investments.
- `ProjectMod` (ERC-721 Registry) for representing singular environmental projects (e.g., Solar Farms, Reforestation efforts).
- `CREentrypoint` (Oracle Hook) for securely receiving impact scores from Chainlink CRE.
* **Tech Stack**: Solidity, Foundry, OpenZeppelin.

#### 3. 🖥️ [EcoBond-Backend-IOT-Simulation](https://github.com/Ecobond/EcoBond-Backend-IOT-Simulation)
The backend simulator providing real-time telemetry from off-chain sources. It simulates real-world environmental data to demonstrate the end-to-end functionality of the platform:
- Solar farm power generation and efficiency monitoring.
- Satellite imagery AI analysis for forest density, deforestation, and carbon stock estimation.
* **Tech Stack**: Node.js, Express.js.

#### 4. ⚡ [ecobond-cre](https://github.com/Ecobond/ecobond-cre)
The off-chain oracle computational layer. Specifically utilizing Chainlink CRE (Compute, Read, Execute), this workflow automates the reading of IoT simulation data, the calculation of project impact scores, and the reliable execution of on-chain operations via the entrypoint smart contract.
* **Tech Stack**: TypeScript, Chainlink CRE SDK.

#### 5. [Frontend](https://github.com/Ecobond/ecobond)
The frontend application providing a user-friendly interface for investors to interact with the platform. It features a modern, responsive design and provides a seamless experience for users to deposit USDC, view their investments, and track the performance of their projects.
* **Tech Stack**: Next.js, TypeScript, wagmi, shadcn/ui, tailwindcss.


## Data Flow Pipeline

Ecobond operates a unidirectional, trust-minimized data pipeline:
1. **Investment**: Investors deposit USDC into the vault and receive EBS (Ecobond Shares).
2. **Data Acquisition**: Chainlink CRE workflows read telemetry (e.g., solar output, forest density) from the IoT Simulation API.
3. **Off-Chain Computation**: The environmental impact and projected value are independently scored using Chainlink.
4. **On-Chain Execution**: The calculated score is written back to the `ProjectMod` contract via the trusted `CREentrypoint` oracle.

## Technology Stack

- **Smart Contracts Layer**: Solidity, Foundry, OpenZeppelin, Solady
- **Oracle / Off-Chain Compute**: Chainlink CRE, Chainlink Forwarder
- **Backend / Simulations**: Node.js, Express.js, TypeScript, Bun
- **Tokens**: USDC (Investments), ERC-4626 (EBS Shares), ERC-721 (Project Registry)

## Getting Started

To explore the entire ecosystem locally, we recommend cloning the primary `EcoBond-Backend` repository with all of its submodules:

```bash
git clone --recurse-submodules https://github.com/Ecobond/EcoBond-Backend.git
cd EcoBond-Backend
```

See the Quick Start guide in the [EcoBond-Backend repository](https://github.com/Ecobond/EcoBond-Backend/blob/main/README.md) to fire up the IoT backend, deploy the contracts to an Anvil node, and run the CRE workflows simultaneously.

---

### Contribute
We welcome external contributors! Please feel free to open Issues or Pull Requests on any of the repositories linked above. Before submitting a major change, please open an issue to discuss your proposed updates.

---

*Green Bonds, verified on-chain. Powered by Chainlink.*
