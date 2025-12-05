This section explains the complete workflow for compiling, deploying, and interacting with the ERC-20 token on the Remix virtual blockchain. Remix provides a convenient in-browser environment to compile Solidity code and test smart contract behavior without connecting to a real blockchain network.
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


Click **Deploy**.

After deployment, Remix will display an instance of your token under the **Deployed Contracts** section.  
This deployed object contains all the public methods and variables of the token contract that you can interact with.

---

### 🔍 4. Interacting With Token Functions

#### ✔ Check Token Metadata
Use the buttons to call:
- `name()` → returns the token's name  
- `symbol()` → returns MTK  
- `decimals()` → returns 18  
- `totalSupply()` → displays total units (in wei format)

These values confirm that the token was deployed with the correct configuration.

---

### 💰 5. Verify Balances
The deploying account automatically receives the entire token supply.  
Copy the address of the first account from the **ACCOUNT** dropdown and pass it to:


You should see the full supply displayed.

---

### 🔄 6. Test the Transfer Function
Select **Account 0** as the sender.  
Copy any other account address (e.g., Account 1) and use it as the recipient.

Now call:


This transfers **1 MTK** from the sender to the receiver.  
You will see a **Transfer event** appear in the Remix logs.  
Calling `balanceOf()` again for each user will confirm the updated balances.

---

### 🛂 7. Test Approvals (approve)
Switch back to the deployer account (Account 0).  
To approve another account (Account 1) to spend tokens on your behalf, call:


This approves **5 MTK** for that spender.  
A corresponding **Approval event** will be logged.

---

### 🔁 8. Test Delegated Transfers (transferFrom)
Now select **Account 1**, which is the approved spender.  
Choose any recipient (e.g., Account 2).  
Call:


This moves **1 MTK** from Owner to Recipient using the approved allowance.  
You should observe:

- Owner’s balance decreases  
- Recipient’s balance increases  
- Allowance reduces accordingly  
- A **Transfer event** is emitted  

---

### ⚠️ 9. Validate Failure Cases
To ensure full ERC-20 compliance, test invalid operations:

- **Transfer to zero address** → Must revert  
- **Transfer more tokens than available balance** → Must revert  
- **transferFrom without prior approval** → Must revert  
- **Allowance insufficient** → Must revert  

These tests ensure your contract correctly implements input validation and safety checks.

---

### 🎉 Step 8 Completed Successfully
By completing this step, you have:

- Compiled and deployed your token  
- Checked metadata and balances  
- Executed basic transfers  
- Approved a spender  
- Performed delegated transfers  
- Observed emitted events  
- Validated error-handling mechanisms  

This confirms your ERC-20 token behaves exactly as expected according to the standard.


