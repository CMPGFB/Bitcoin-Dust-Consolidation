# Bitcoin Dust Consolidation

A Python-based tool to consolidate dust UTXOs in a Bitcoin wallet using Bitcoin Core RPC. This script connects to a local Bitcoin Core node, fetches dust UTXOs, and consolidates them into a single output in a single transaction.

## Prerequisites

- Running Bitcoin Core node with RPC server enabled.
- Python 3 installed.
- Install `python-bitcoinlib` via pip:
  ```bash
  pip install python-bitcoinlib
  ```

## Setup
  
**Configuration**
Edit the consolidate_dust.py script to update the following configurations:

RPC_USER: Your RPC username.
RPC_PASSWORD: Your RPC password.
RPC_HOST: Your RPC host (default is 127.0.0.1).
RPC_PORT: Your RPC port (default is 8332).
CONSOLIDATION_ADDRESS: Your Bitcoin address to receive the consolidated dust.
DUST_THRESHOLD_SATS: Threshold for what constitutes dust (default is 10000 satoshis).
FEE_SATS: Fee for the consolidation transaction (default is 500 satoshis).

**Usage**
Run the script to consolidate dust UTXOs:

```bash
python consolidate_dust.py
```

**Clone the repository:**
```bash
git clone https://github.com/CMPGFB/Bitcoin-Dust-Consolidation.git
cd Bitcoin-Dust-Consolidation
```

**How It Works**
Connects to the Bitcoin Core node using RPC credentials.
Fetches UTXOs from the wallet with at least 1 confirmation.
Filters out UTXOs above the user-defined dust threshold.
Gathers dust UTXOs into a list of inputs.
Sums up the total amount of dust UTXOs.
Subtracts the configurable fee amount.
Creates a raw transaction that sends the remaining BTC to the consolidation address.
Signs the transaction with the wallet.
Broadcasts the transaction to the Bitcoin network.
Prints out the transaction ID.

**Best Practices & Warnings**
Privacy Concerns: Consolidating dust UTXOs can lead to linkability of addresses and reduce privacy. Consider using privacy-focused tools like CoinJoin.
Testing: Always test the script on Bitcoin testnet or regtest before using it on the mainnet to avoid potential loss of funds due to bugs or misconfigurations.
Scams: Be aware of scams that claim to double your BTC or offer unrealistic returns. Never share your private keys.

**Contributing**
Contributions are welcome! Please fork the repository and create a pull request with your changes.

**License**
This project is licensed under the MIT License
