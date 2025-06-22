# Zap Pilot - Project Overview

## Purpose
Zap Pilot is a general-purpose intent-based execution engine for DeFi operations. The platform enables users to create and manage various vault strategies including Stablecoin Vault, Index500 (S&P500-like index fund), BTC vault, ETH vault, with support for customizable vaults. The system interprets user intents and executes optimal paths across DeFi protocols automatically.

## Architecture
The system follows a microservices architecture with four main components:

### 1. Frontend (`all-weather-frontend/`)
- **Technology**: Next.js 13, React 18, TypeScript, Tailwind CSS
- **Web3 Integration**: ThirdWeb SDK, Ethers.js, Viem
- **Features**: Multi-chain support (20+ networks), smart wallet integration, vault strategy visualization
- **Port**: 3000

### 2. Backend (`backend/`)
- **Technology**: Node.js, Express.js
- **Purpose**: User management, reporting, notifications
- **Features**: Google Sheets integration, DeBank API, Discord/email notifications
- **Port**: 3002

### 3. Rebalance Engine (`rebalance_backend/`)
- **Technology**: Python/Flask
- **Purpose**: Intent-based execution and vault rebalancing using mathematical models
- **Features**: Web3.py integration, strategy analysis

### 4. Intent Engine (`intent-engine/`)
- **Technology**: Node.js/TypeScript
- **Purpose**: Core intent processing and execution orchestration

## Vault Strategies
- **Stablecoin Vault**: Low-risk yield generation with stablecoins
- **Index500**: S&P500-like index fund strategy for crypto markets  
- **BTC Vault**: Bitcoin-focused investment strategy
- **ETH Vault**: Ethereum-focused investment strategy
- **Custom Vaults**: User-defined strategies with customizable parameters

## Key Features
- Intent-based execution engine for DeFi operations
- Multi-protocol DeFi integration (Aave, Convex, Moonwell, Camelot, etc.)
- Account abstraction with gasless transactions
- Automated vault rebalancing and strategy optimization
- Cross-chain asset management
- Real-time portfolio tracking and reporting