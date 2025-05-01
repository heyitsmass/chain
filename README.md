## Chain - Blockchain-Based Secure Communication Experiment

_why not_

- [Chain - Blockchain-Based Secure Communication Experiment](#chain---blockchain-based-secure-communication-experiment)
  - [Goal/Vision](#goalvision)
  - [Core Features](#core-features)
  - [Key Components / Architecture (Highly Dependent on Focus)](#key-components--architecture-highly-dependent-on-focus)
  - [Tech Stack](#tech-stack)
  - [Potential Challenges](#potential-challenges)

### Goal/Vision

To explore the feasibility and potential benefits/drawbacks of using blockchain concepts to establish or enhance secure communication channels between a frontend and backend, focusing on aspects like identity, message integrity, or non-repudiation. Highly experimental.

### Core Features

-   **Message Integrity/Non-Repudiation:**
    -   Client signs messages (or message hashes) using their private key before sending.
    -   Backend verifies the signature using the client's public key.
    -   Optionally, message hashes (or encrypted messages) could be anchored/logged on a blockchain (testnet) as immutable proof of communication (high cost/latency).

### Key Components / Architecture (Highly Dependent on Focus)

-   **Frontend (Web Application):**
    -   **Web3 Integration:** Library like `ethers.js` or `web3.js` to interact with blockchain nodes and user wallets (MetaMask).
    -   **Wallet Connection:** Logic to connect to user's wallet and get their address/public key.
    -   **Message Signing:** Use wallet provider (`window.ethereum`) to sign messages or data payloads.
    -   **Smart Contract Interaction (if applicable):** Call functions on deployed contracts.
-   **Backend (Server Application):**
    -   **Signature Verification:** Logic to recover the signer's address from a signed message and signature. Compare against known/expected addresses.
    -   **Blockchain Interaction (Optional):** May need its own connection to a blockchain node (e.g., via Infura, Alchemy, or a local node) to query contract state or verify on-chain data.
    -   **Smart Contract Interaction (if applicable):** May need to interact with deployed contracts.
-   **Blockchain / Smart Contracts (Testnet like Sepolia, Goerli, or local like Ganache):**
    -   **Smart Contract (if applicable):** Written in Solidity, defining data structures and functions relevant to the chosen focus (e.g., identity registry, message log).

### Tech Stack

-   Frontend: Any framework (React, Vue, etc.), `ethers.js` / `web3.js`.
-   Backend: Any language (Node.js, Go, Python), relevant crypto libraries for signature verification (e.g., `ethers.js` utils, Python `eth_account`).
-   Blockchain: Ethereum testnet (Sepolia) or local development network (Ganache, Hardhat Network).
-   Smart Contracts: Solidity.
-   Development Tools: Hardhat, Truffle.

### Potential Challenges

-   **Complexity:** Blockchain interactions add significant complexity compared to traditional methods.
-   **Latency & Cost:** On-chain transactions are slow and cost gas (even on testnets). Relying heavily on them for real-time communication is impractical.
-   **User Experience:** Requires users to have blockchain wallets and understand signing prompts.
-   **Scalability:** Most public blockchains have limited transaction throughput.
-   **Defining a Clear Benefit:** Identifying a problem where blockchain _truly_ offers a superior solution compared to established cryptographic techniques (like TLS, standard digital signatures) is the main challenge. Often, traditional methods are more efficient and suitable.
-   **Security:** Smart contract vulnerabilities, private key management risks.
