# web3-starter

Jump into web3 development with ease!  
This starter kit provides Python scripts and Solidity contract scaffolding to help you quickly compile, deploy, and interact with smart contracts on Arbitrum Sepolia using Infura.

## Features

- Generate Ethereum-compatible wallet keys
- Compile Solidity smart contracts
- Deploy contracts to Arbitrum Sepolia via Infura (HTTP or WebSocket)
- Store and manage contract ABIs, bytecode, and deployment data

## Project Structure

```
.
├── compile.py            # Compile Solidity contracts and extract ABI/bytecode
├── contracts/
│   └── HelloWorld.sol    # Example Solidity contract
├── data/
│   ├── account_data.json # Generated wallet keys
│   ├── compiled_contract.json
│   ├── contract_abi.json
│   ├── contract_bytecode.txt
│   └── contract.json     # Deployed contract address
├── deploy.py             # Deploy contract to Arbitrum Sepolia
├── generateKeys.py       # Generate wallet keys
├── init.py               # Web3 and contract initialization
└── README.md
```

## Prerequisites

- Python 3.8+
- [pip](https://pip.pypa.io/en/stable/)
- [Infura](https://infura.io/) account (for Arbitrum Sepolia access)

### Python Dependencies

Install requirements with:

```bash
pip install web3 py-solc-x eth-account
```

## Getting Started

1. **Clone the repository:**

    ```bash
    git clone git@github.com:cgaspart/web3-starter.git
    cd web3-starter
    ```

2. **Generate wallet keys:**

    ```bash
    python generateKeys.py
    ```
    This creates `data/account_data.json` containing your new Ethereum wallet.

3. **Compile the Solidity contract:**

    ```bash
    python compile.py
    ```
    This reads `contracts/HelloWorld.sol` and outputs ABI/bytecode to the `data/` directory.

4. **Deploy the contract:**

    Update your Infura Project ID in the scripts if needed.

    ```bash
    python deploy.py
    ```
    This deploys the contract to Arbitrum Sepolia and saves the contract address in `data/contract.json`.

## Configuration

- **Infura Project ID:**  
  Update the `INFURA_KEY` parameter in `deploy.py` and `init.py` with your Infura Project ID.

- **Solidity Version:**  
  The default version is set to `0.8.21` in `compile.py`. Adjust if your contract requires a different version.

## Scripts Overview

- `generateKeys.py`: Generates a new wallet and saves private/public keys.
- `compile.py`: Compiles the Solidity contract, outputs ABI and bytecode.
- `deploy.py`: Deploys the compiled contract to Arbitrum Sepolia via Infura.
- `init.py`: Initializes web3, loads contract and wallet data, and connects to the network.

## Notes

- All sensitive data (private keys) are stored locally in the `data/` directory. Keep this directory secure!
- The project uses Arbitrum Sepolia testnet. For mainnet deployment, update the network URLs in `init.py`.

## License

MIT
