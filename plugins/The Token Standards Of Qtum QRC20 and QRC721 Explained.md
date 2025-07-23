# The Token Standards Of Qtum: QRC20 and QRC721 Explained  

Qtum’s unique blockchain architecture combines Bitcoin’s UTXO model with Ethereum’s EVM capabilities, enabling developers to create robust decentralized applications (dApps) and tokens. This article explores two foundational token standards on Qtum—**QRC20** and **QRC721**—and their parallels to Ethereum’s **ERC20** and **ERC721** standards. By understanding these frameworks, developers can build interoperable tokens that power Qtum’s ecosystem.  

## Why Token Standards Matter  

Token standards are essential for blockchain interoperability. Without universal protocols, dApps would operate in silos, unable to communicate or exchange assets. Ethereum’s adoption of **ERC20** and **ERC721** streamlined token creation and interaction, inspiring Qtum to adopt similar standards—**QRC20** for fungible tokens and **QRC721** for non-fungible tokens (NFTs). These standards ensure consistency across wallets, exchanges, and dApps.  

### Key Concepts  
- **Fungibility**: Assets that are interchangeable (e.g., fiat currency).  
- **Non-Fungibility**: Unique assets with distinct properties (e.g., digital art).  
- **Interoperability**: Seamless integration between blockchain networks and applications.  

---

## QRC20: Fungible Tokens on Qtum  

**QRC20** mirrors Ethereum’s **ERC20** standard, defining functions for creating and managing fungible tokens. These tokens are divisible, replicable, and ideal for currencies, stablecoins, or utility tokens.  

### Core Functions of QRC20  
| Function        | Purpose                          |  
|-----------------|----------------------------------|  
| `totalSupply`   | Returns total token supply       |  
| `balanceOf`     | Checks user token balance        |  
| `transfer`      | Sends tokens to another address  |  
| `approve`       | Authorizes third-party transfers |  

### Deploying QRC20 Tokens  
1. **Install Dependencies**: Use Qtum’s **Solar** tool and Solidity compiler.  
2. **Generate Deposit Address**: Use `qtum-cli getnewaddress`.  
3. **Interact with Contracts**:  
   - **Check Balance**:  
     ```bash  
     qtum-cli callcontract {CONTRACT_ADDRESS} 70a08231{userAddressHex}  
     ```  
   - **Withdraw Tokens**:  
     ```bash  
     qtum-cli sendtocontract {CONTRACT_ADDRESS} a9059cbb{userAddressHex}{amountHex}  
     ```  

👉 [Explore blockchain development tools on OKX](https://bit.ly/okx-bonus)  

---

## QRC721: Non-Fungible Tokens on Qtum  

**QRC721** aligns with Ethereum’s **ERC721** standard, enabling the creation of unique, indivisible tokens like NFTs. These tokens represent ownership of digital or physical assets, with metadata ensuring uniqueness.  

### Core Functions of QRC721  
| Function                | Purpose                          |  
|-------------------------|----------------------------------|  
| `ownerOf(tokenId)`      | Returns the owner of a token     |  
| `approve(to, tokenId)`  | Grants transfer rights           |  
| `transfer(from, to)`    | Moves ownership between addresses|  

### Deploying QRC721 Tokens  
1. **Set Up Environment**:  
   - Clone the QRC721 repository:  
     ```bash  
     git clone https://github.com/qtumproject/QRC721Token.git  
     ```  
   - Install dependencies: `npm install`.  
2. **Deploy with Solar**:  
   ```bash  
   solar deploy contracts/QRC721.sol '["name","symbol"]' --qtum_rpc=http://rpcuser:rpcpassword@localhost:port  
   ```  
3. **Verify Deployment**:  
   Check the `solar.development.json` file for contract details like address and transaction ID.  

---

## Frequently Asked Questions (FAQs)  

### 1. What’s the Difference Between QRC20 and QRC721?  
QRC20 tokens are **fungible** (interchangeable), while QRC721 tokens are **non-fungible** (unique). For example, QRC20 could represent USD coins, while QRC721 might represent a rare digital collectible.  

### 2. How Do I Check Token Balances?  
Use the `balanceOf` function with the `qtum-cli` command:  
```bash  
qtum-cli callcontract {CONTRACT_ADDRESS} 70a08231{userAddressHex}  
```  

### 3. Can I Transfer Ownership of an NFT?  
Yes, via the `transfer` function. The owner can send their NFT to another address, or use `approve` to authorize a third party.  

### 4. Are QRC Tokens Compatible with Ethereum?  
While QRC standards are inspired by Ethereum’s ERC20 and ERC721, they are tailored for Qtum’s UTXO+EVM architecture. Cross-chain interoperability requires bridges or sidechains.  

---

## Expanding Qtum’s Token Ecosystem  

Qtum’s hybrid model allows developers to leverage Ethereum’s EVM while benefiting from Bitcoin’s security. By adopting **QRC20** and **QRC721**, projects can create tokens that are:  
- **Scalable**: UTXO model enables faster transactions.  
- **Secure**: Bitcoin’s PoW consensus protects against attacks.  
- **Interoperable**: Standards ensure compatibility with wallets and dApps.  

👉 [Learn how OKX supports blockchain innovation](https://bit.ly/okx-bonus)  

### Real-World Applications  
- **QRC20**: Stablecoins, loyalty programs, governance tokens.  
- **QRC721**: NFT marketplaces, digital certificates, metaverse assets.  

---

## Conclusion  
