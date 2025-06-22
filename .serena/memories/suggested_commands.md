# Development Commands

## Frontend (all-weather-frontend/)
```bash
# Development
yarn                        # Install dependencies
doppler run -- yarn dev    # Start development server (requires .env.local)
yarn build                  # Build for production

# Testing
yarn test                   # Run Vitest tests (140s timeout)
yarn test-ui               # Start Vitest UI at http://localhost:51204/__vitest__/
yarn coverage              # Run test coverage report

# Code Quality
yarn lint                  # Run ESLint with auto-fix
yarn format                # Format code with Prettier and Black
```

## Backend (backend/)
```bash
# Development
yarn install               # Install dependencies
yarn dev                   # Start development server with hot reload
yarn start                 # Production start

# Testing
yarn test                  # Run all tests
yarn test:watch            # Run tests in watch mode
yarn test:coverage         # Run tests with coverage report

# Code Quality
yarn format                # Code formatting
yarn lint                  # Linting
```

## Python Services (rebalance_backend/)
```bash
# Testing
npm run test               # Run pytest tests with coverage (88% minimum)

# Code Quality
black .                    # Code formatting
isort .                    # Import sorting
flake8                     # Linting (max-line-length = 88)
bandit -r .               # Security scanning
```

## Intent Engine (intent-engine/)
```bash
# Development
npm install                # Install dependencies
npm run dev               # Start development server

# Testing
npm test                  # Run Jest tests

# Code Quality
npm run lint              # ESLint check
npm run format            # Prettier formatting
```

## System Commands (Darwin/macOS)
```bash
# Git operations
git status
git add .
git commit -m "message"
git push

# File operations
ls -la                     # List files with details
find . -name "*.js"        # Find files
grep -r "pattern" .        # Search in files
```