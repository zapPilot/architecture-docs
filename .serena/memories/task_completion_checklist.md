# Task Completion Checklist

## Before Committing Code
Always run these commands after completing development tasks:

### Frontend (all-weather-frontend/)
1. **Format Code**: `yarn format` - Run Prettier and Black formatting
2. **Lint Code**: `yarn lint` - Run ESLint with auto-fix
3. **Run Tests**: `yarn test` - Execute Vitest test suite
4. **Build Check**: `yarn build` - Verify production build works

### Backend (backend/)
1. **Format Code**: `yarn format` - Apply code formatting
2. **Lint Code**: `yarn lint` - Run ESLint checks
3. **Run Tests**: `yarn test:coverage` - Execute Jest tests with coverage
4. **Verify API**: Test endpoints manually or with automated tests

### Python Services (rebalance_backend/)
1. **Format Code**: `black .` - Apply Black formatting
2. **Sort Imports**: `isort .` - Organize imports
3. **Lint Code**: `flake8` - Check code quality
4. **Security Scan**: `bandit -r .` - Run security analysis
5. **Run Tests**: `npm run test` - Execute tests with 88% coverage requirement

### Intent Engine (intent-engine/)
1. **Format Code**: `npm run format` - Apply Prettier formatting  
2. **Lint Code**: `npm run lint` - Run ESLint checks
3. **Run Tests**: `npm test` - Execute Jest test suite

## Deployment Considerations
- **Environment Variables**: Ensure all required env vars are set
- **Docker Build**: Test Docker builds before deployment
- **Performance**: Verify no memory leaks or performance regressions
- **Error Handling**: Check error handling and logging

## Git Workflow
1. Check git status: `git status`
2. Stage changes: `git add .`
3. Commit with descriptive message: `git commit -m "descriptive message"`
4. Push to appropriate branch: `git push`

## Notes
- Never commit code that fails linting or tests
- Always verify builds work before deployment
- Use conventional commit message format
- Test across multiple environments when possible