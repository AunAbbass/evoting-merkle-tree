# Blockchain-Based E-Voting System

A secure, digital voting application that leverages blockchain concepts to ensure the integrity and immutability of voter data. This project implements a Merkle Tree data structure combined with cryptographic hashing to securely record, verify, and manage votes.

## Features
* **Secure Voter Registry**: Manages voter identities and ensures each participant can only cast a single, verifiable vote.
* **Merkle Tree Integration**: Utilizes a Merkle Tree to structure the vote data, allowing for highly efficient and secure verification of individual votes without exposing the entire dataset.
* **Cryptographic Security**: Employs SHA-256 hashing to generate unique signatures for each node in the tree, ensuring that any tampering with a single vote invalidates the root hash.
* **Vote Verification**: Includes built-in functions to traverse the tree and mathematically prove that a specific vote is accurately recorded in the final tally.

## Tech Stack
* **Language**: C++
* **Concepts**: Blockchain Architecture, Cryptography (SHA-256), Advanced Data Structures (Merkle Trees), Data Integrity

## Core Logic
The application relies on the Merkle Root as the single source of truth for the election. When a vote is cast, it is hashed and paired with neighboring hashes until a single root hash is formed. If any previous vote is altered, the underlying hashes change, immediately flagging the system to potential tampering. 

