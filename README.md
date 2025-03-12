# State-aware dynamic circuits with recursive proofs

flowchart TD
    A["Blockchain Network (State Sources)\n(Ethereum, Solana, Cosmos, Oracle Feeds\n(Chainlink/Pyth))"]
    B["State Tracking & Proof Generation Layer\n(Off-Chain)"]
    B1["State Listeners\n(Monitors events, Fetches Merkle proofs)"]
    B2["Cross-Chain Adapters\n(Converts state proofs across chains)"]
    B3["Light Clients\n(Validates state via zk-SNARKs)"]
    C["Dynamic Constraint Engine (AC⁴ Core)"]
    C1["Parametric Polynomial Generator\n(Inputs: state data\nOutputs: updated constraints)"]
    C2["Hot-Swappable Modules\n(Plug-in constraints, e.g., AMM curves,\nliquidation logic)"]
    D["Incremental Proof Aggregation Layer"]
    D1["Folding Schemes\n(Nova/SuperNova)\n(Aggregates proofs over state transitions)"]
    D2["GPU-Accelerated Prover\n(Parallelizes proof generation)"]
    E["Verification Layer (On-Chain)"]
    E1["zkEVM / Smart Contracts\n(Verifies folded proofs,\nUpdates state)"]
    E2["Gas-Optimized Verifier\n(Uses Yul/Huff for low-cost verification)"]
    
    A --> B
    B --> C
    C --> D
    D --> E
    
    subgraph "Off-Chain Layer"
      B1
      B2
      B3
    end
    
    subgraph "Dynamic Constraint Engine"
      C1
      C2
    end
    
    subgraph "Proof Aggregation Layer"
      D1
      D2
    end
    
    subgraph "On-Chain Verification"
      E1
      E2
    end
