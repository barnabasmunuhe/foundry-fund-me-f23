# 🏦 FundMe Smart Contract (Foundry Edition)

This is a minimalist crowdfunding smart contract built with [Foundry](https://book.getfoundry.sh/). It allows users to send ETH to the contract, tracks contributions, and lets the owner withdraw the funds.

Built to practice:
- Smart contract fundamentals
- Price feeds using Chainlink oracles
- Deployment scripts and Foundry testing

## 📁 Project Structure

├── contracts/ # Core smart contracts
├── script/ # Deployment & interaction scripts
├── test/ # Unit & integration tests
├── lib/ # External dependencies
└── foundry.toml # Foundry config file


## ⚙️ Getting Started

### Requirements

- [Git](https://git-scm.com/)
- [Foundry](https://book.getfoundry.sh/getting-started/installation)
- [Node.js & NPM](https://nodejs.org/)
- Optional: [Docker](https://docs.docker.com/get-docker/) if testing zkSync

### Clone & Build

```bash
git clone https://github.com/barnabasmunuhe/fund-me
cd fund-me
forge install
forge build
```

# 🚀 Deploying Contracts

## Local Deployment

```bash
forge script script/DeployFundMe.s.sol --fork-url http://127.0.0.1:8545 --broadcast --private-key <PRIVATE_KEY>
```
Replace <PRIVATE_KEY> with a test key (do not use real accounts).


## Testnet Deployment
```bash
forge script script/DeployFundMe.s.sol \
  --rpc-url $SEPOLIA_RPC_URL \
  --private-key $PRIVATE_KEY \
  --broadcast \
  --verify \
  --etherscan-api-key $ETHERSCAN_API_KEY
```

# 🧪 Running Tests
```bash
forge test
```
## Forked Tests (e.g. Sepolia)
```bash
forge test --fork-url $SEPOLIA_RPC_URL
```
# Coverage Report
```bash
forge coverage
```

# 🔗 Chainlink Integration
This contract uses Chainlink Price Feeds to convert ETH to USD in real time.

## 📜 Example Interactions
Send ETH to the contract:

```bash
cast send <FUNDME_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

Withdraw funds (only owner):

```bash
cast send <FUNDME_ADDRESS> "withdraw()" --private-key <PRIVATE_KEY>
```

# 🧠 Concepts Covered
Fallback functions & receive

Access control via onlyOwner

msg.value, msg.sender

External price feeds (Chainlink)

Environment configs via .env

Gas estimates with forge snapshot

# 🔍 Upcoming Enhancements
This is an evolving project. Here’s what I plan to add next:

 Enums for withdrawal states

 Events for fund and withdraw actions

 Try/Catch error handling

 Function selectors

 abi.encode, abi.decode

 Hashing with keccak256

 Inline Yul/Assembly optimization

# Formatting

``` bash
forge fmt
```

# 📌 Notes
This is a personal sandbox for Solidity, Foundry, and contract architecture experiments. Contributions welcome — PRs or feedback are appreciated.

# 🧠 License
MIT License

Made with ❤️ and plenty of debugging logs by @barnabasmunuhe

# THANK YOU😃