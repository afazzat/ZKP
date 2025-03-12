# State-aware dynamic circuits with recursive proofs

+------------------------------------------------------------------------------+
|                            Blockchain Network (State Sources)                |
| [Ethereum]  [Solana]  [Cosmos]  [Oracle Feeds (Chainlink/Pyth)]              |
+------------------------------------------------------------------------------+
                              ▼
+---------------------+---------------------+---------------------+
|       State Tracking & Proof Generation Layer (Off-Chain)       |
+---------------------+---------------------+---------------------+
|  [State Listeners]  |  [Cross-Chain Adapters]  |  [Light Clients]  |
| - Monitors events   | - Converts state proofs  | - Validates state  |
| - Fetches Merkle    |   across chains (e.g.,   |   via zk-SNARKs    |
|   proofs            |   Solana → Ethereum)     |                    |
+---------------------+---------------------+---------------------+
                              ▼
+------------------------------------------------------------------------------+
|                        Dynamic Constraint Engine (AC⁴ Core)                  |
| [Parametric Polynomial Generator]                                            |
| - Input: State data (e.g., price, balance)                                   |
| - Output: Updated constraints (e.g., P(x, s) = 0, where s = state variable) |
|                                                                              |
| [Hot-Swappable Modules]                                                      |
| - Plug-in constraints (e.g., AMM curves, liquidation logic)                 |
+------------------------------------------------------------------------------+
                              ▼
+------------------------------------------------------------------------------+
|                     Incremental Proof Aggregation Layer                      |
| [Folding Schemes (Nova/SuperNova)]                                           |
| - Aggregates proofs over state transitions                                   |
| - Generates recursive proofs (Proof₁ ◊ Proof₂ → FoldedProof)                |
|                                                                              |
| [GPU-Accelerated Prover]                                                     |
| - Parallelizes proof generation                                              |
+------------------------------------------------------------------------------+
                              ▼
+------------------------------------------------------------------------------+
|                          Verification Layer (On-Chain)                       |
| [zkEVM / Smart Contracts]                                                    |
| - Verifies folded proofs                                                     |
| - Updates state (e.g., balances, NFT ownership)                              |
|                                                                              |
| [Gas-Optimized Verifier]                                                     |
| - Uses Yul/Huff for low-cost verification                                    |
+------------------------------------------------------------------------------+
