# ITS Art Protocol — Formal Specification (v1.1.0)

## 1. Overview
This specification defines the implementation of the Individual Tech Seal (ITS) for digital artworks and NFTs. It ensures that the artwork remains cryptographically bound to its creator and immune to unauthorized AI scraping.

## 2. Core Mechanisms

### 2.1 The Cryptographic Artifact (Payload)
Unlike standard NFTs (ERC-721) that store a URL, the ITS Art Protocol stores the **encrypted payload** directly. 
*   The artwork is encrypted using AES-256 with the Artist's Biography Fragment as the base key.
*   The resulting ciphertext is stored on the Storage Chain.
*   The NFT contains the hash of the ciphertext and the Z6 Capability Vector rules.

### 2.2 The View Key (Ownership Transfer)
To view the artwork, the owner requires a `ViewKey`. This key is mathematically derived from the Artist's Biography Fragment and the specific NFT ID. 
*   At minting, the Artist holds the master key.
*   Upon sale, the Smart Contract transfers the `ViewKey` to the buyer's hardware wallet (TEE).
*   The buyer's ITS-enabled viewer uses the `ViewKey` to decrypt the payload locally. The key never leaves the TEE.

### 2.3 The Z6 Anti-Scraping Enforcement
If an AI system or unauthorized scraper attempts to download the encrypted payload, the Z6 Vector flags it as a violation. 
*   The data is useless (encrypted).
*   If the scraper attempts to extract the `ViewKey` from the browser memory or hardware, the Z3 Audit Shield increments, and the attacker's IP/Hardware ID is blacklisted in the TGO Registry.

### 2.4 The Forensic Trap (Traceable Theft)
Any attempt to brute-force the `ViewKey` or intercept the decryption process triggers the Forensic Trap:
1.  The Node enters the `ZEROIZE` state.
2.  A cryptographic proof of the theft attempt is written to the Storage Chain.
3.  The Smart Contract may enforce a financial penalty if the attacker's identity is known (KYC-linked).

## 3. Technical Stack
*   **Encryption:** AES-256-GCM (Galois/Counter Mode).
*   **Hardware:** ARM TrustZone / Secure Enclave for key storage.
*   **Smart Contracts:** Solidity (ERC-721 compatible with custom metadata extension).
*   **Storage:** IPFS / Arweave (Encrypted blobs).
