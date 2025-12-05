
---

### 🔧 1. Open Remix and Prepare the Workspace
Begin by visiting the Remix IDE at:  
**https://remix.ethereum.org**

In the file explorer panel, create a new Solidity file named **MyToken.sol**.  
Paste your entire ERC-20 contract code into this file.

---

### 🧩 2. Compile the Smart Contract
Navigate to the **Solidity Compiler** tab.  
Choose any compiler version from the **0.8.x** series (for example, 0.8.20 or 0.8.18).  
Make sure the selected file is **MyToken.sol**, then click:

**Compile MyToken.sol**

A successful compilation will show no errors and indicate that the code has been built correctly.

---

### 🚀 3. Deploy the Token Contract
Open the **Deploy & Run Transactions** tab.  
Configure the following options:

- **Environment:** Select **JavaScript VM** (Prague/London/Cancún).  
  This provides a local blockchain simulation with several test accounts.
- **Account:** Any default account will work — Remix will automatically provide ETH to these accounts for gas.
- **Gas Limit:** Leave the default setting unless otherwise required.
- **Contract:** Ensure **MyToken** is selected.

The constructor of this token requires the **initial total supply**.  
For a token supply of **1,000,000 MTK**, and considering **18 decimals**, you must enter:

