# Codebase Structure

## Root Directory
```
all-weather-protocol/
├── all-weather-frontend/     # Next.js Web3 frontend application for Zap Pilot
├── backend/                  # Node.js/Express API server
├── rebalance_backend/        # Python/Flask intent execution and analysis service
├── intent-engine/           # Node.js/TypeScript intent processing service
├── CLAUDE.md               # Project instructions for Claude
├── INTENT_ENGINE_MIGRATION_PLAN.md
└── .gitignore
```

## Frontend Structure (all-weather-frontend/)
```
all-weather-frontend/
├── pages/                   # Next.js pages (routing)
├── components/             # React components
├── classes/               # Protocol and vault classes
│   ├── BaseProtocol.js    # Abstract base for DeFi protocols
│   └── Vaults/           # Vault strategy orchestrators
├── utils/                 # Utility functions and configurations
├── lib/                  # Smart contract ABIs and libraries
├── __tests__/            # Vitest test files
├── public/               # Static assets (images, logos)
├── styles/               # CSS and styling
└── hooks/                # Custom React hooks
```

## Backend Structure (backend/)
```
backend/
├── controllers/           # Business logic controllers
├── routes/               # API endpoint definitions
├── services/             # External service integrations
├── utils/                # Shared utilities and ABIs
├── __tests__/            # Jest test files
├── middleware/           # Express middleware
└── app.js               # Main application entry point
```

## Python Service Structure (rebalance_backend/)
```
rebalance_backend/
├── routes_dir/           # Flask route definitions
├── services/             # Core business logic services
├── handlers/             # Request handlers
├── adapters/             # External API adapters
├── connectors/           # Blockchain connectors
├── utils/                # Utility functions
├── tests/                # Python unit tests
├── config/               # Configuration files
└── main.py              # Flask application entry point
```

## Intent Engine Structure (intent-engine/)
```
intent-engine/
├── src/                  # TypeScript source code
├── tests/                # Jest test files
├── docs/                 # Documentation
├── docker/               # Docker configuration
└── logs/                 # Application logs
```

## Key Files
- **CLAUDE.md**: Project instructions and guidelines for Zap Pilot
- **package.json**: Dependencies and scripts for each component
- **pyproject.toml**: Python project configuration (rebalance_backend)
- **.env files**: Environment configuration (not committed)
- **Docker files**: Containerization setup
- **README.md**: Component-specific documentation