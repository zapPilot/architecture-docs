# Technology Stack

## Frontend (all-weather-frontend/)
- **Framework**: Next.js 13 with React 18
- **Language**: TypeScript (strict configuration)
- **Styling**: Tailwind CSS
- **Web3**: ThirdWeb SDK, Ethers.js, Viem
- **Testing**: Vitest with React Testing Library
- **Build Tool**: Next.js built-in webpack
- **Package Manager**: Yarn

## Backend (backend/)
- **Runtime**: Node.js
- **Framework**: Express.js
- **Language**: JavaScript (ES6+)
- **Testing**: Jest with supertest
- **Package Manager**: Yarn
- **Database**: Google Sheets API (primary), Google Cloud Storage (caching)

## Python Services (rebalance_backend/)
- **Runtime**: Python 3.x
- **Framework**: Flask
- **Package Manager**: npm (scripts) + Python pip/poetry
- **Web3**: Web3.py
- **Data Processing**: Pandas
- **Testing**: Python unittest with coverage
- **Production Server**: Gunicorn

## Intent Engine (intent-engine/)
- **Runtime**: Node.js
- **Language**: TypeScript
- **Testing**: Jest
- **Package Manager**: npm

## External Services
- **APIs**: DeBank API, DeFiLlama API, Google Sheets API, QuickChart API
- **Notifications**: Discord webhooks, Gmail SMTP
- **Storage**: Google Cloud Storage
- **Deployment**: Docker, Google Cloud Run