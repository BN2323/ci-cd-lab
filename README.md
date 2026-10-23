# ci-cd-lab

A small Node.js + Express application with a Continuous Integration (CI) pipeline
built using GitHub Actions. Built for Lab 1: Building a CI/CD Pipeline with GitHub Actions.

## Tech stack

- **Runtime:** Node.js 24+ (ES Modules)
- **Package manager:** Yarn 4
- **Web framework:** Express 5
- **Testing:** Mocha + Chai + Supertest
- **Linting:** ESLint (flat config)
- **Coverage:** c8

## Project structure

```text
ci-cd-lab/
├── .github/
│   └── workflows/
│       └── ci.yml
├── test/
│   └── test.js
├── .gitignore
├── .yarnrc.yml
├── app.js
├── eslint.config.js
├── package.json
├── README.md
└── server.js
```

## Getting started

```bash
# Activate Yarn 4 (requires corepack, bundled with Node)
corepack enable
corepack prepare yarn@4.18.1 --activate

# Install dependencies
yarn install

# Run the app (http://localhost:3000/)
yarn start
```

The root endpoint `GET /` returns `Hello, GitHub Actions!`.

## Scripts

| Command         | Description                                 |
| --------------- | ------------------------------------------- |
| `yarn start`    | Start the HTTP server (default port 3000).  |
| `yarn test`     | Run the Mocha test suite.                   |
| `yarn lint`     | Run ESLint over the project.                |
| `yarn coverage` | Run tests under c8 and generate a report.   |

## Continuous Integration

The workflow in `.github/workflows/ci.yml` runs on pushes and pull requests
targeting `main`. It installs dependencies, runs ESLint, runs the tests, and
generates a coverage report, which is uploaded as a build artifact named
`code-coverage-report`.
