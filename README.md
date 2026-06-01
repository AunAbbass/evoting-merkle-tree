# E-VoteVerify+

This project is a DSII voting verification system built around hashed ballots and tamper-evident data structures[cite: 7]. A vote is turned into a SHA-256 leaf, stored in a Merkle-based structure, and later verified by recomputing the path back to the published root[cite: 7].

## Project Idea
The goal of the project is to show how data structures can be used to protect vote integrity[cite: 7].

* **Merkle Tree Integration:** The main voting flow uses a Merkle Tree to store ballot hashes, generate inclusion proofs, and detect tampering when any ballot changes[cite: 7].
* **MMR Simulation:** The live simulation uses an MMR (Merkle Mountain Range) to support append-heavy voting activity while still producing verifiable roots and proof paths[cite: 7].
* **Sparse Merkle Tree (SSR):** The voter-status side uses a Sparse Merkle Tree to track voter verification state in a sparse key space and allows proof-based checks before voting[cite: 7].

## Core Functionality
* Register voters and prevent duplicate voting[cite: 7]
* Cast votes and hash each ballot[cite: 7]
* Build and display the Merkle Tree[cite: 7]
* Generate and verify Merkle proofs for a receipt[cite: 7]
* Simulate tampering and show how verification fails[cite: 7]
* Run a live browser visualization for the Merkle Tree, MMR, and Sparse Merkle Tree views[cite: 7]

## System Architecture
* **Backend:** Written in C++17[cite: 7]. It handles voter registration, ballot hashing, Merkle Tree logic, MMR simulation, Sparse Merkle Tree checks, proof generation, verification, and the local HTTP server used for visualization[cite: 7].
* **Frontend:** The browser-based visualization layer served locally by the C++ backend[cite: 7]. It displays the Merkle Tree, MMR simulation, proof paths, and live verification state through interactive web pages[cite: 7].

## Setup & Compilation

### Option 1: Quick Start (Recommended)
To compile and run everything more quickly, use the provided batch script[cite: 7]:
`.\run_dashboard.bat`[cite: 7]

This launches `run_dashboard.ps1`, which automatically[cite: 7]:
* Rebuilds `mmr_sim.exe` if its source files changed[cite: 7]
* Rebuilds `evoteverify_web.exe` if its source files changed[cite: 7]
* Starts the MMR simulator on `http://127.0.0.1:9090/`[cite: 7]
* Starts the visualization homepage on `http://127.0.0.1:8080/`[cite: 7]
* Opens the browser automatically[cite: 7]

### Option 2: Manual Compilation
**Main Voting System:**
`g++ -std=c++17 -O2 -I. -o evoteverify.exe src/main.cpp src/ballot.cpp src/voter_registry.cpp src/merkle_tree.cpp src/live_visualization_server.cpp src/sha256.cpp -lws2_32`[cite: 7]

*Run:* `.\evoteverify.exe`[cite: 7]

**MMR Simulation:**
`g++ -std=c++17 -O2 -I. -Isim -o mmr_sim.exe src/main_sim.cpp src/mmr_simulation.cpp src/merkle_mountain_range.cpp src/sparse_merkle_tree.cpp src/sha256.cpp -lws2_32`[cite: 7]

*Run:* `.\mmr_sim.exe`[cite: 7]

