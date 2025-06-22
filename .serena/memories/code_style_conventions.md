# Code Style and Conventions

## Frontend (TypeScript/React)
- **ESLint**: Extends "next/core-web-vitals"
- **TypeScript**: Strict configuration with no implicit any
- **Formatting**: Prettier (automatic formatting)
- **File Structure**: Pages in `pages/`, components in `components/`, utilities in `utils/`
- **Testing**: Vitest with React Testing Library, tests in `__tests__/` directory

## Backend (Node.js/JavaScript)
- **ESLint**: Extends "eslint:recommended" and "plugin:prettier/recommended"
- **Formatting**: Prettier with single quote configuration
- **Style**: ES6+ syntax, async/await patterns
- **File Structure**: Controllers in `controllers/`, routes in `routes/`, services in `services/`
- **Testing**: Jest with supertest for API testing

## Python Services
- **Formatting**: Black (automatic code formatting)
- **Import Sorting**: isort
- **Linting**: flake8 with max-line-length = 88
- **Security**: bandit for security scanning
- **Testing**: Python unittest with fixtures and mocking
- **Coverage**: 88% minimum test coverage requirement

## General Guidelines
- **Documentation**: Comprehensive inline documentation required
- **Error Handling**: Proper error handling with logging
- **Security**: No secrets in code, proper input validation
- **Performance**: Async/await patterns, connection pooling
- **Git**: Conventional commit messages
- **Pre-commit**: Format and lint checks enforced

## Architecture Patterns
- **Frontend**: Protocol-based architecture with BaseProtocol inheritance
- **Backend**: RESTful API design with controller/service separation
- **Python**: Flask application with modular service structure
- **Web3**: Standardized operations (zapIn, zapOut, stake, unstake, transfer)