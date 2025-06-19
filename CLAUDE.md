# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

All Weather Protocol is a DeFi portfolio management platform implementing Ray Dalio's All Weather Portfolio strategy. The system consists of four main components:

1. **Frontend** (`all-weather-frontend/`) - Next.js/React Web3 application
2. **Backend** (`backend/`) - Node.js/Express API for user management and reporting
3. **Rebalance Engine** (`rebalance_backend/`) - Python/Flask portfolio analysis service
4. **Analytics Engine** (`index500/`) - Python-based index fund strategy analysis

## Architecture

The system follows a microservices architecture with clear separation of concerns:

- **Frontend**: Handles user interactions, Web3 wallet connections, and portfolio visualization
- **Backend**: Manages user data, generates reports, sends notifications via Discord/email
- **Rebalance Engine**: Analyzes portfolios and provides rebalancing recommendations using mathematical models
- **Analytics Engine**: Performs backtesting and strategy analysis for index fund approaches

Each component has its own package.json/pyproject.toml with independent dependencies and can be developed/deployed separately.

## Development Commands

### Frontend (all-weather-frontend/)
```bash
yarn dev          # Start development server
yarn build        # Production build
yarn test         # Run Vitest tests
yarn test-ui      # Run tests with UI
yarn coverage     # Generate test coverage
yarn lint         # ESLint check
yarn format       # Prettier formatting
```

### Backend (backend/)
```bash
yarn dev          # Start with nodemon
yarn test         # Run Jest tests
yarn test:coverage # Test coverage report
yarn lint         # ESLint check
yarn format       # Prettier formatting
```

### Python Components (rebalance_backend/, index500/)
```bash
npm run test      # Run pytest tests
black .           # Code formatting
isort .           # Import sorting
flake8            # Linting
bandit -r .       # Security scanning
```

## Key Technologies

- **Frontend**: Next.js 13, React 18, TypeScript, Tailwind CSS, ThirdWeb SDK, Ethers.js, Viem
- **Backend**: Node.js, Express.js, Google Sheets API, DeBank API, Discord webhooks
- **Python**: Flask, Pandas, Web3.py, Poetry, Gunicorn
- **Testing**: Vitest, Jest, Pytest with comprehensive coverage requirements

## Web3 Integration

The frontend uses ThirdWeb SDK for wallet connections and supports 20+ blockchain networks. Account abstraction is implemented using smart wallets for gasless transactions.

## Performance Considerations

- Frontend optimized to use <350MB RAM (reduced from >500MB)
- Backend implements connection pooling and batch operations
- Rate limiting configured for external API calls
- Async/await patterns used throughout for non-blocking operations

## Testing Requirements

All components require comprehensive testing:
- Frontend: Vitest with React Testing Library
- Backend: Jest with supertest for API testing
- Python: Pytest with fixtures and mocking

## Code Quality

- Strict TypeScript configuration with no implicit any
- ESLint + Prettier for consistent formatting
- Python: Black, isort, flake8, bandit for code quality and security
- Pre-commit hooks enforce formatting and linting

## External APIs

- DeBank API for portfolio data aggregation
- Google Sheets API for data storage and reporting
- Discord webhooks for notifications
- Gmail SMTP for email notifications

## Deployment

Each component can be deployed independently. The Python services use Gunicorn for production deployment.