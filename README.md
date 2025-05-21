#  FundMe (Foundry Edition)

A decentralized crowdfunding smart contract built with Solidity and Foundry — because GoFundMe needs a Web3 glow-up.

## Features

- Accepts ETH donations from users
- Only the contract owner can withdraw funds
- Integration-tested with mocks & scripts
- Cross-chain configurable using `HelperConfig.sol`
- Built with gas optimization and clean architecture in mind

---

## 📦 Tech Stack

- 🧠 Solidity `^0.8.28`
- 🧪 [Foundry](https://github.com/foundry-rs/foundry) for testing/scripting
- 🔧 Chainlink Price Feeds (live + mocks)
- 📜 DevOpsTools for deployment automation

---

## ⚙️ Setup & Installation

```bash
git clone https://github.com/YOUR-USERNAME/FundMe.git
cd FundMe

---

 ##  INSTALL DEPENDANCIES
```
forge install
---

 2.Set up environment variables
 ``bash
  cp .env.example .env
# Fill in your private key, RPC URL, and API keys

3.Start a local chain (optional)
```bash
anvil

DEPLOYMENT
Deploy to Local Network (Anvil)
```bash
forge script script/DeployFundMe.s.sol --rpc-url http://localhost:8545 --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY

Deploy to Sepolia Testnet
```bash
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY

---

Testing

```bash
forge test -vv
Includes:
.Unit tests for core contract logic

.Integration test using Interactions.s.sol and InteractionsTests.t.sol

.Mock testing for Chainlink integration

.Test coverage for:

.ETH funding and withdrawal

.Owner access control

.Contract behavior on different networks
---

KEY CONCEPTS
NetworkConfig: Used to manage mock vs. live price feed addresses depending on the chain.

MockV3Aggregator: Provides test ETH/USD prices in local environments.

HelperConfig.sol: Dynamically returns the correct price feed address per network.

Integration Testing: Simulates real-world usage (funding/withdrawing), includes user behavior via vm.prank() and vm.deal().
---

SECURITY FEATURES
Only the contract owner can withdraw funds.

Ensures non-zero ETH amount is sent for funding.

Includes mock testing to prevent live token misuse.
---

PROJECT STRUCTURE
├── src/
│   └── FundMe.sol               # Main smart contract
├── script/
│   ├── DeployFundMe.s.sol      # Deployment logic
│   └── Interactions.s.sol      # Interaction scripts (fund/withdraw)
├── test/
│   ├── FundMeTest.t.sol        # Unit tests
│   └── InteractionsTests.t.sol # Integration tests
├── test/mocks/
│   └── MockV3Aggregator.sol    # Chainlink mock
└── HelperConfig.sol            # Network config logic
---

📄 LICENSE
This project is licensed under the MIT License.
---

🤝 ACKNOLEDGEMENTS
Built as part of the Cyfrin Updraft Foundry Course

Inspired by Chainlink’s decentralized data and the Foundry testing framework
---

 CONNECT
Feel free to open issues or pull requests. Contributions are welcome.

Smart contracts aren't just code—they're agreements in motion.
This one says: fund with trust, withdraw with authority.
---