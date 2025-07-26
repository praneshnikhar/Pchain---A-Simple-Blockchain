# Pchain-A-Simple-Blockchain
A beginner-friendly Java blockchain tutorial demonstrating block creation, SHA-256 hashing, proof-of-work mining, and chain validation.


Pchain is a beginner-friendly, proof-of-concept blockchain implementation written in Java. This project serves as a hands-on introduction to the principles that power blockchains and cryptocurrencies, making complex technology accessible for learners and developers exploring distributed ledger concepts.

What is Pchain?
Pchain is a basic blockchain—not a production-ready cryptocurrency or platform, but an educational, minimal codebase designed to illuminate the fundamental mechanics behind blockchains. By building and experimenting with Pchain, you’ll discover how digital ledgers, cryptographic hashing, and mining work under the hood.

Key Features
Block Structure: Each block contains data, the hash of the previous block, its own hash (digital fingerprint), a timestamp, and a nonce variable for mining.

Cryptographic Hashing: SHA-256 hashing ensures data integrity and enables blockchain security.

Proof-of-Work Mining: Each new block must be "mined"—its hash must start with a configurable number of leading zeros. This demonstrates the concept of computational difficulty in real-world cryptocurrencies.

Chain Validation: Pchain can verify the entire blockchain to ensure that no data has been altered—demonstrating tamper-resistance.

JSON Output: Optional integration with the GSON library allows you to print and view the blockchain data as JSON for readability and later network/p2p experiments.

How Does It Work?
Block Creation: Each block’s hash is calculated from its contents, including previous hash and timestamp. Changing any block’s data changes its hash, invalidating the chain.

Genesis Block: The very first block (the genesis block) uses "0" as its previous hash.

Proof of Work: When adding new blocks, the code performs "mining" by altering the nonce until the hash has the required zeros (difficulty).

Chain Verification: A built-in method checks that the chain is valid—ensuring each block’s data matches its hash and links properly to the previous block.

Why Pchain?
Educational Focus: Pchain demystifies blockchain technology, making learning fun and practical.

Tinker-Friendly: Change variables like mining difficulty and block data to see immediate effects.

Java First: Ideal for those with OOP (Object-Oriented Programming) experience, especially in Java.

Open Source: Fork, modify, or extend it for personal learning or as a starting point for deeper experiments.

Getting Started
Make sure you have Java, JDK, and your preferred IDE (e.g., Eclipse) installed.

Clone the repository and run the main class.

Modify, experiment, and learn!

(Optional) Use the GSON library to output your blockchain as JSON.

What You’ll Learn
The essential building blocks of blockchain technology.

How tampering breaks chain integrity and how proof of work secures the system.

The real-world limitations and design decisions underlying major cryptocurrencies.

Disclaimer
Pchain is for learning purposes only—it is not designed for production use, handling real value, or public blockchain deployment.

Explore the code, experiment with different settings, and—most importantly—have fun learning how blockchains really work!
