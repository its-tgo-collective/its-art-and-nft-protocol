# ITS Art & NFT Protocol
**True Digital Ownership for Artists and Creators**

> **NEW:** Read the [STRATEGIC_IMPACT.md](STRATEGIC_IMPACT.md) to understand the economic and regulatory leverage of this framework.

[![DOI](https://zenodo.org/badge/1450365249.svg)](https://doi.org/10.5281/zenodo.24055640) *(Optional: Hier kannst du später den DOI des Art-Repos einfügen)*

**Status:** Release v1.1.0
**License for this Text:** CC0 1.0 Universal (Public Domain)
**License for Protected Works:** ITS Public License v1.1 (See LICENSE file)

---

## The Problem with current NFTs
Current NFTs are fundamentally broken. They are merely links to external servers (often centralized). 
*   The artwork itself is not on the blockchain.
*   Anyone can copy the image and use it for AI training.
*   If the server goes down, the NFT becomes an empty token.
*   The artist loses control over their creation.

## The Solution: The ITS Art Protocol
The ITS (Individual Tech Seal) revolutionizes digital art by creating an **encrypted, on-chain artifact**. 
When an artist mints an ITS-NFT, the artwork itself is encrypted using the artist's **Biography Fragment** (a unique cryptographic key) and stored directly on the blockchain.

*   **True Scarcity:** Only the owner of the NFT holds the decryption key (View Key). The artwork cannot be copied or viewed by unauthorized parties.
*   **Anti-AI Protection:** AI scrapers see only encrypted data (cryptographic noise). The Z6 Hardware Vector blocks any attempt to process the image without the key.
*   **Forensic Theft Tracing:** If someone attempts to steal the key or brute-force the encryption, the Z6 Vector triggers a lockdown and logs the attacker's hardware ID on the Storage Chain.

## How it works
1.  **Minting:** The artist encrypts the work with their Biography Fragment. The encrypted payload is uploaded to the Storage Chain.
2.  **Ownership Transfer:** When the NFT is sold, a unique `View Key` is transferred to the buyer, allowing them to decrypt and view the artwork.
3.  **Provenance:** Every view, transfer, and attempted theft is permanently logged in the ITS Audit Trail.

*This is not just a speculative link. It is the artwork itself.*
