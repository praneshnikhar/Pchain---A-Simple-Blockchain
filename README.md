# Pchain

A beginner-friendly, proof-of-concept blockchain implementation written in Java. This project serves as a hands-on introduction to the principles that power blockchains and cryptocurrencies, making complex technology accessible for learners and developers exploring distributed ledger concepts.

## About

Pchain is a **basic blockchain** implementation—not a production-ready cryptocurrency or platform, but an educational, minimal codebase designed to illuminate the fundamental mechanics behind blockchains. By building and experimenting with Pchain, you'll discover how digital ledgers, cryptographic hashing, and mining work under the hood.

This project is perfect for:
- Students learning blockchain technology
- Developers new to distributed ledger concepts
- Anyone curious about how cryptocurrencies work at a fundamental level

## Key Features

### Block Structure
Each block contains:
- Data payload
- Hash of the previous block
- Its own hash (digital fingerprint)
- Timestamp
- `nonce` variable used in the mining process

### Cryptographic Hashing
- Utilizes SHA-256 hashing algorithm
- Ensures data integrity throughout the blockchain
- Provides the security foundation for blockchain technology

### Proof-of-Work Mining
- Each new block must be "mined" before being added to the chain
- Block hash must start with a configurable number of leading zeros
- Demonstrates computational difficulty concept used in real-world cryptocurrencies
- Adjustable difficulty levels for experimentation

### Chain Validation
- Built-in blockchain verification system
- Ensures no data has been tampered with
- Demonstrates tamper-resistance properties of blockchain technology

### JSON Output
- Optional GSON library integration
- Export blockchain data as JSON for readability
- Useful for debugging and future network/peer-to-peer experiments

## How It Works

### 1. Block Creation
Each block's hash is calculated from its contents, including:
```java
blockHash = SHA256(previousHash + timestamp + data + nonce)
```

Changing any block's data changes its hash, which invalidates the entire chain from that point forward.

### 2. Genesis Block
The first block in the chain (genesis block) uses `"0"` as its previous hash reference since no block exists before it.

### 3. Proof of Work Mining Process
When adding new blocks:
```java
// Mining loop
while (!hash.startsWith("0".repeat(difficulty))) {
    nonce++;
    hash = calculateHash();
}
```

The system performs "mining" by incrementing the nonce until the resulting hash meets the difficulty requirement.

### 4. Chain Verification
The validation method ensures:
- Each block's stored hash matches its calculated hash
- Each block properly links to the previous block
- The chain maintains integrity from genesis to current block

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 8 or higher
- Preferred IDE (Eclipse, IntelliJ IDEA, or VS Code)
- Git for version control
- GSON library (optional, for JSON output)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/pchain.git
cd pchain
```

2. Open the project in your preferred IDE

3. If using GSON for JSON output, add the dependency:
```xml
<!-- For Maven projects -->
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.8.9</version>
</dependency>
```

### Usage

1. Compile and run the main class:
```bash
javac *.java
java Main
```

2. Basic usage example:
```java
// Create a new blockchain
Blockchain blockchain = new Blockchain();

// Add blocks with data
blockchain.addBlock(new Block("First block data", blockchain.getLatestBlock().hash));
blockchain.addBlock(new Block("Second block data", blockchain.getLatestBlock().hash));

// Validate the blockchain
System.out.println("Is blockchain valid? " + blockchain.isChainValid());

// Print blockchain as JSON (if GSON is included)
System.out.println(blockchain.toJSON());
```

## Learning Outcomes

After working with Pchain, you will understand:

- **Blockchain Fundamentals**: The essential building blocks of blockchain technology
- **Cryptographic Hashing**: How SHA-256 ensures data integrity and security
- **Mining Process**: How proof-of-work secures the network through computational difficulty
- **Chain Integrity**: How tampering with any block breaks the entire chain's validity
- **Distributed Ledger Concepts**: The principles underlying major cryptocurrencies
- **Real-world Limitations**: Design decisions and trade-offs in blockchain systems

## Project Structure

```
pchain/
├── src/
│   ├── Block.java          # Block class definition
│   ├── Blockchain.java     # Blockchain implementation
│   ├── Main.java          # Main application entry point
│   └── StringUtil.java    # Utility functions for hashing
├── lib/                   # External libraries (GSON)
├── README.md
└── LICENSE
```

## Configuration

You can experiment with various blockchain parameters:

### Mining Difficulty
```java
// Adjust the number of leading zeros required
public static int difficulty = 4; // Requires 4 leading zeros
```

### Block Data
```java
// Add different types of data to blocks
blockchain.addBlock(new Block("Transaction: Alice pays Bob 10 coins", previousHash));
blockchain.addBlock(new Block("Transaction: Bob pays Charlie 5 coins", previousHash));
```

### Genesis Block
```java
// Customize the genesis block
Block genesisBlock = new Block("Genesis Block", "0");
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Ready to explore blockchain technology?** Clone the repository, experiment with different settings, and discover how blockchains really work!
