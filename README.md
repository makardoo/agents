# Polymarket Agents

A fork of [Polymarket/agents](https://github.com/Polymarket/agents) — autonomous trading agents for Polymarket prediction markets.

## Overview

This project provides a framework for building and deploying autonomous agents that interact with Polymarket prediction markets. Agents can:

- Monitor active markets
- Analyze market conditions using LLMs
- Execute trades based on configurable strategies
- Manage positions and track performance

## Requirements

- Python 3.10+
- Docker (optional, for containerized deployment)
- Polymarket API credentials
- OpenAI API key (or compatible LLM provider)

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-org/agents.git
cd agents
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure environment

Copy the example environment file and fill in your credentials:

```bash
cp .env.example .env
```

Edit `.env` with your API keys and configuration.

### 4. Run an agent

```bash
python -m scripts.run_agent
```

## Docker

Build and run using Docker:

```bash
docker build -t polymarket-agents .
docker run --env-file .env polymarket-agents
```

Or use the GitHub Actions workflow which automatically builds and pushes images.

## Project Structure

```
agents/
├── scripts/          # Entry point scripts
├── agents/           # Core agent implementations
├── polymarket/       # Polymarket API client
├── llm/              # LLM integrations
├── utils/            # Shared utilities
└── tests/            # Test suite
```

## Configuration

| Variable | Description | Required |
|---|---|---|
| `POLYMARKET_API_KEY` | Your Polymarket API key | Yes |
| `OPENAI_API_KEY` | OpenAI API key for LLM reasoning | Yes |
| `WALLET_PRIVATE_KEY` | Wallet private key for signing transactions | Yes |
| `RPC_URL` | Ethereum RPC endpoint | Yes |
| `DRY_RUN` | Set to `true` to simulate trades without executing them (recommended for testing) | No |

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/my-feature`)
3. Commit your changes using [Conventional Commits](https://www.conventionalcommits.org/)
4. Open a Pull Request

Please use the provided issue templates for bug reports and feature requests.

## License

MIT License — see [LICENSE](LICENSE) for details.
