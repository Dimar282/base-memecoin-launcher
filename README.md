# Base Token Deployer 🚀

Simple, fast and gas-optimized toolset for deploying ERC-20 / ERC-721 tokens on **Base** chain.

Currently includes:
- Foundry project structure
- Deployment scripts (including verification on Basescan)
- Basic tests
- Optional Next.js frontend starter (in `/frontend` folder)

## Features

- Ultra-low gas deployment scripts (optimized for Base L2)
- Support for both standard ERC20 and mintable/burnable variants
- Easy verification on Basescan
- Ready-to-use environment variables setup
- Basic security checklist in docs

## Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/base-token-deployer.git
cd base-token-deployer

# 2. Install dependencies
forge install

# 3. Copy and configure .env
cp .env.example .env
# ← edit .env with your PRIVATE_KEY and BASE_RPC_URL

# 4. Deploy example token
forge script script/DeploySimpleToken.s.sol:DeploySimpleToken --rpc-url $BASE_RPC_URL --broadcast --verify -vvvv

├── script/              # Deployment scripts
├── src/                 # Smart contracts
├── test/                # Foundry tests
├── frontend/            # (optional) Next.js + wagmi frontend
├── .env.example         # Example environment variables
└── foundry.toml         # Foundry configuration

# .env
PRIVATE_KEY=0x...
BASE_RPC_URL=https://mainnet.base.org
ETHERSCAN_API_KEY=your_basescan_api_key   # for --verify

# Run all tests
forge test

# Run specific test
forge test --match-test testTokenMint

# Deploy & verify in one command
forge script script/DeploySimpleToken.s.sol --rpc-url $BASE_RPC_URL --broadcast --verify

# Format code
forge fmt

# Update dependencies
forge update
ok
