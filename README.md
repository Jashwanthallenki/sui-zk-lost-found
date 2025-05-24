````markdown
# 🧳 ZK Lost and Found – Built on Sui

**ZK Lost and Found** is a decentralized application (dApp) built on the **Sui blockchain** that helps users anonymously report and recover lost items using **zero-knowledge proofs**. This ensures user **privacy**, **authenticity**, and **transparency** in an immutable and tamper-proof system.

🚀 Try the live app here: [sui-zk-lost-found.vercel.app](<a>https://sui-zk-lost-found.vercel.app/</a>)

---

## 💡 Problem It Solves

In the real world, recovering lost items is inefficient and often relies on centralized platforms or unverified social networks. Common issues include:

- False claims or theft during recovery.
- Lack of anonymity when reporting or claiming items.
- Difficulty verifying the authenticity of a found item.

---

## 🔐 Innovation

**ZK Lost and Found** introduces a **zero-knowledge (ZK) privacy layer** to the recovery process:

- 🔒 **Anonymity**: Both finders and owners stay anonymous using ZK proofs.
- ✅ **Verification Without Exposure**: Users prove ownership of an item without revealing private details.
- 📜 **Immutable Proof**: All interactions are logged on-chain and cannot be altered or faked.
- 🌐 **Trustless Coordination**: No third-party needed to mediate or verify claims.

---

## 🧱 Architecture

### Smart Contracts

- Written in **Move** and deployed to the **Sui devnet**.
- Handles:
  - Lost item submissions.
  - Claim requests and ZK verification.
  - Item recovery lifecycle management.

> 🧪 View the smart contract in the `move/` directory  
> 🔎 Devnet Deployment:  
> Transaction Digest: `kJQ5DLq1JuZELTPneemsg2Zvxx78umHoRhih5pDkpNM`  
> Use the transaction digest to explore the shared object on the [Sui Explorer](https://explorer.devnet.sui.io/).

---

## 🌐 Frontend dApp

The dApp is built using modern web3 stack:

- [React](https://react.dev/) – UI Framework
- [TypeScript](https://www.typescriptlang.org/) – Type Safety
- [Vite](https://vitejs.dev/) – Fast Build Tool
- [Radix UI](https://www.radix-ui.com/) – UI Components
- [`@mysten/dapp-kit`](https://sdk.mystenlabs.com/dapp-kit) – Sui Wallet Integration
- [pnpm](https://pnpm.io/) – Package Manager

---

## 🧪 Test the Smart Contract

```bash
cd ./move/my_first_package
sui move build
sui move test
```

---

## ⚙️ Deploying on Sui Devnet

### 1. Install Sui CLI

Follow the [official Sui CLI install guide](https://docs.sui.io/build/install).

### 2. Set up Devnet Environment

```bash
sui client new-env --alias devnet --rpc https://fullnode.devnet.sui.io:443
sui client switch --env devnet
```

### 3. Create New Wallet

```bash
sui client new-address secp256k1
sui client switch --address 0xYOUR_ADDRESS
```

### 4. Get Devnet SUI

```bash
curl --location --request POST 'https://faucet.devnet.sui.io/gas' \
--header 'Content-Type: application/json' \
--data-raw '{
  "FixedAmountRequest": {
    "recipient": "<YOUR_ADDRESS>"
  }
}'
```

### 5. Publish the Move Package

```bash
cd move
sui client publish --gas-budget 100000000
```

After publishing, copy the `"packageId"` from the output and set it in `src/constants.ts`:

```ts
export const DEVNET_COUNTER_PACKAGE_ID = "<YOUR_PACKAGE_ID>";
```

---

## 🧩 Running the dApp

### Install dependencies:

```bash
pnpm install
```

### Run in development mode:

```bash
pnpm dev
```

---

## 📦 Build for Production

```bash
pnpm build
```

---

## 🔍 How It's Different

| Feature                | Traditional Lost & Found | ZK Lost and Found         |
| ---------------------- | ------------------------ | ------------------------- |
| **Ownership Proof**    | Weak or none             | Verified via ZK proof     |
| **User Privacy**       | Often public             | Fully anonymous           |
| **Trust Layer**        | Centralized              | Trustless smart contracts |
| **Data Tampering**     | Possible                 | Immutable on-chain        |
| **Third-Party Needed** | Yes                      | No intermediary required  |
````
