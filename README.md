# Zap Pilot

![Project Status](https://img.shields.io/badge/status-active-success)

Zap Pilot is a cutting-edge, general-purpose intent-based execution engine designed to simplify and optimize complex DeFi operations across multiple blockchain networks. It empowers users to define their desired financial outcomes (intents) without needing to navigate the intricate details of underlying protocols, smart contracts, or multi-step transaction sequences.

## ✨ Value Proposition

In the rapidly evolving and often complex DeFi landscape, managing assets, optimizing yields, and executing sophisticated strategies can be a significant challenge. Zap Pilot abstracts away this complexity, offering a streamlined and powerful solution:

*   **Effortless Strategy Execution**: Simply define your financial goals, and Zap Pilot intelligently identifies and executes the most efficient and secure path to achieve them.
*   **Multi-Protocol & Cross-Chain Reach**: Seamlessly interact with leading DeFi protocols like Aave, Convex, Moonwell, Camelot, and many others, across 20+ supported blockchain networks.
*   **Gasless Transactions**: Leverage advanced account abstraction techniques for a frictionless, gas-free user experience, removing a common barrier to DeFi adoption.
*   **Diversified Vault Strategies**: Access a range of pre-built and customizable vault strategies, including Stablecoin, Index500, BTC, and ETH vaults, to suit various risk appetites and financial objectives.
*   **Real-time Insights**: Gain comprehensive visibility into your portfolio and strategy performance with real-time tracking and detailed reporting.

## 💡 Intent-Based Execution Explained

At the core of Zap Pilot's innovation is its unique intent-based execution model. Unlike traditional DeFi interactions where users must specify every granular step of a transaction (e.g., "approve token A, swap A for B on Uniswap, deposit B into Aave"), Zap Pilot allows users to declare their high-level *intentions*.

For instance, an intent could be: "I want to earn the highest yield on my USDC, regardless of the network or protocol." The Zap Pilot engine then intelligently processes this intent by:

1.  **Interpreting the Intent**: Understanding the user's desired outcome and constraints.
2.  **Analyzing the Landscape**: Scanning across all integrated DeFi protocols, liquidity sources, and supported networks for optimal opportunities.
3.  **Generating Optimal Paths**: Identifying the most efficient, cost-effective, and secure sequence of operations to fulfill the intent, considering gas costs, slippage, and available liquidity.
4.  **Executing Atomically**: Orchestrating and executing the complex multi-step, multi-protocol, and potentially cross-chain transactions on behalf of the user, often leveraging account abstraction for gasless execution.

This paradigm shift significantly simplifies DeFi interactions, making advanced strategies accessible and efficient for both novice and experienced users.

## 🏛️ Architecture Overview

Zap Pilot employs a robust microservices architecture, ensuring scalability, maintainability, and clear separation of concerns. Each component is designed to be developed, deployed, and scaled independently.

The system comprises four primary services:

1.  **Frontend (`all-weather-frontend/`)**
    *   **Technology**: Next.js 13, React 18, TypeScript, Tailwind CSS, ThirdWeb SDK
    *   **Role**: The user-facing Web3 application. It handles user interactions, Web3 wallet connections, vault strategy visualization, and real-time portfolio tracking.
    *   **Port**: 3000

2.  **Backend (`backend/`)**
    *   **Technology**: Node.js, Express.js, Google Sheets API, DeBank API
    *   **Role**: Provides core API services for user management, data aggregation, reporting, and notification delivery via Discord/email.
    *   **Port**: 3002

3.  **Rebalance Engine (`rebalance_backend/`)**
    *   **Technology**: Python, Flask, Pandas, Web3.py, Poetry, Gunicorn
    *   **Role**: The core intent execution and vault rebalancing service. It uses sophisticated mathematical models to analyze market conditions and orchestrate complex DeFi operations.

4.  **Intent Engine (`intent-engine/`)**
    *   **Technology**: Node.js, TypeScript
    *   **Role**: Processes and interprets raw user intents, translating high-level goals into actionable execution plans.

## 💰 Supported Vault Strategies

Zap Pilot offers a variety of pre-configured and customizable vault strategies to cater to different investment goals and risk profiles:

*   **Stablecoin Vault**: Designed for low-risk yield generation by strategically deploying stablecoins across various DeFi protocols to maximize returns while minimizing volatility.
*   **Index500**: An S&P500-like index fund strategy tailored for the crypto markets, providing diversified exposure to a basket of top-performing digital assets.
*   **BTC Vault**: A specialized strategy focused on optimizing returns and managing Bitcoin holdings within the broader DeFi ecosystem.
*   **ETH Vault**: An Ethereum-centric investment strategy designed for yield generation and efficient asset management of ETH and related assets.
*   **Custom Vaults**: Advanced users can define and deploy their own unique strategies with granular control over parameters, asset allocation, and protocol selection.

## 🚀 Getting Started

To set up and run the Zap Pilot project locally, follow these steps. Each component is designed to run independently, allowing for focused development.

### Prerequisites

Ensure you have the following installed on your system:

*   **Node.js**: v18 or higher (includes `npm`)
*   **Yarn**: Install globally via npm: `npm install -g yarn`
*   **Python**: v3.9 or higher
*   **Poetry**: For Python dependency management (install via pip: `pip install poetry`)

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd all-weather-protocol
    ```

2.  **Environment Variables**:
    Each component requires specific environment variables (e.g., API keys for DeBank, RPC URLs for blockchain networks). Navigate into each component's directory and look for an `.env.example` or `.env.sample` file. Create a `.env` file in each component's root directory based on the example.

### Running Components

#### 1. Frontend (`all-weather-frontend/`)

```bash
cd all-weather-frontend
yarn install       # Install dependencies
yarn dev           # Start development server
```
Access the frontend at `http://localhost:3000`

#### 2. Backend (`backend/`)

```bash
cd backend
yarn install       # Install dependencies
yarn dev           # Start API server with hot reload
```
The backend API runs on `http://localhost:3002`

#### 3. Rebalance Engine (`rebalance_backend/`)

```bash
cd rebalance_backend
# Copy environment template
cp sample.env .env
# Install dependencies
poetry install
npm install
# Run the service
GOOGLE_APPLICATION_CREDENTIALS=service-account.json gunicorn -b 0.0.0.0:3001 --workers 2 --threads 20 --timeout 150 --log-level debug --access-logfile - --error-logfile - rebalance_backend:app
```

#### 4. Intent Engine (`intent-engine/`)

```bash
cd intent-engine
npm install        # Install dependencies
npm run dev        # Start development server
```

## ⚙️ Development Workflow

### Frontend (`all-weather-frontend/`)

```bash
yarn dev          # Start development server
yarn build        # Create production build
yarn test         # Run Vitest tests (140s timeout)
yarn test-ui      # Start Vitest UI at http://localhost:51204/__vitest__/
yarn coverage     # Generate test coverage report
yarn lint         # Run ESLint with auto-fix
yarn format       # Format code with Prettier and Black
```

### Backend (`backend/`)

```bash
yarn dev          # Start development server with hot reload
yarn start        # Production start
yarn test         # Run Jest tests
yarn test:watch   # Run tests in watch mode
yarn test:coverage # Run tests with coverage report
yarn lint         # Run ESLint checks
yarn format       # Apply code formatting
```

### Python Components (`rebalance_backend/`)

```bash
npm run test      # Run pytest tests with coverage (88% minimum)
black .           # Apply Black code formatting
isort .           # Sort Python imports
flake8            # Run linting checks (max-line-length = 88)
bandit -r .       # Perform security scanning
```

## 🧪 Testing

Comprehensive testing is maintained across all components:

*   **Frontend**: Vitest with React Testing Library for UI and application logic testing
*   **Backend**: Jest with supertest for API endpoint testing
*   **Python Components**: Pytest with fixtures and mocking for unit and integration testing

All components maintain high test coverage requirements to ensure code quality.

## 🔑 Key Technologies

*   **Frontend**: Next.js 13, React 18, TypeScript, Tailwind CSS, ThirdWeb SDK, Ethers.js, Viem
*   **Backend**: Node.js, Express.js, Google Sheets API, DeBank API, Discord webhooks
*   **Python**: Flask, Pandas, Web3.py, Poetry, Gunicorn
*   **Testing**: Vitest, Jest, Pytest with comprehensive coverage requirements

## 🌐 Web3 Integration

The frontend uses ThirdWeb SDK for wallet connections and supports 20+ blockchain networks. Account abstraction is implemented using smart wallets for gasless transactions. The intent-based execution engine interprets user intents and routes transactions across optimal DeFi protocols automatically.

## 📊 Performance Considerations

*   Frontend optimized to use <350MB RAM (reduced from >500MB)
*   Backend implements connection pooling and batch operations
*   Rate limiting configured for external API calls
*   Async/await patterns used throughout for non-blocking operations

## 🚀 Deployment

Each component can be deployed independently. The Python services use Gunicorn for production deployment. Docker configurations are available for containerized deployments.

## 📄 Documentation

For detailed development guidelines, architecture information, and component-specific documentation, see [CLAUDE.md](./CLAUDE.md).

## 🤝 Contributing

We welcome contributions to the Zap Pilot project! Please ensure you follow the code quality standards:

*   Run linting and formatting tools before committing
*   Maintain test coverage requirements
*   Follow the established coding conventions for each component

---

*Built with ❤️ for the DeFi community*