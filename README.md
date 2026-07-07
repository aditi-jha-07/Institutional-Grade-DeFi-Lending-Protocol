# Institutional-Grade-DeFi-Lending-Protocol
Institutional lenders needed a permissioned pool with dynamic interest rate curves, strict collateralisation, and automated liquidation without sacrificing composability.
Institutional‑Grade DeFi Lending Protocol
====================================

NDA Statement: All company names, exact financial figures, and proprietary strategy details have been omitted or generalised due to a binding Non‑Disclosure Agreement. The architecture and contributions described are accurate representations of my work.

Client – A top‑tier DeFi protocol (anonymised)
Role – Lead Smart Contract Engineer
Duration – 9 months

Problem Statement
Institutional lenders needed a permissioned pool with dynamic interest rate curves, strict collateralisation, and automated liquidation without sacrificing composability.

Solution
Designed a modular protocol of 12+ Solidity smart contracts using the diamond proxy pattern. The system supports isolated lending pools, each with its own risk parameters, interest rate model, and price oracle.

Key Features

Isolated lending pools with supply/borrow caps

Dynamic interest rate curves modelled as PID controllers

Chainlink Price Feeds + TWAP fallback for asset pricing

Dutch‑auction liquidation engine with MEV protection

Role‑based access control (RBAC) for admin functions

Architecture
[Frontend dApp] → [Subgraph (The Graph)] ← Indexed events
↕
[Lending Pool Factory] → [Pool Contracts (Diamond)] → [Liquidator Bot]
↕
[Price Oracle Aggregator] → Chainlink / Uniswap TWAP

Tech Stack

Smart Contracts: Solidity 0.8, Hardhat, Foundry (fuzz testing)

Oracle: Chainlink, custom TWAP adapter

Indexing: The Graph (AssemblyScript mappings)

DevOps: GitHub Actions, Slither, Echidna, Mythril

Testing & Security

98% branch coverage with unit, integration, and invariant tests

Formal verification of interest rate model using Certora Prover

Two independent audit firms engaged; all critical findings resolved

Outcome

TVL grew to $380M within 3 months post‑launch

Zero liquidation failures under high‑volatility market conditions
