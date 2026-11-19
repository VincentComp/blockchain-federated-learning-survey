# Decentralized Federated Learning via Blockchain: A Technical Survey

> A literature review of how blockchain changes coordination, accountability, and incentives in federated learning, and what those changes cost.

[![Paper](https://img.shields.io/badge/Paper-PDF-B31B1B?style=flat-square&logo=adobeacrobatreader&logoColor=white)](./Paper.pdf)
![Type](https://img.shields.io/badge/Type-Technical_Survey-6A5ACD?style=flat-square)
![Topic](https://img.shields.io/badge/Topic-Federated_Learning-3776AB?style=flat-square)
![Topic](https://img.shields.io/badge/Topic-Blockchain-2E8B57?style=flat-square)

📄 **Read the full paper:** [Decentralized Federated Learning via Blockchain: A Technical Survey](./Paper.pdf)

## Overview

Federated learning enables participants to train a shared model without pooling their raw data. Conventional designs often still rely on a central coordinator to manage training rounds and aggregate updates. This survey examines three challenges that arise in collaborative settings: dependence on that coordinator, limited visibility into the training history, and difficulty rewarding meaningful contributions.

The paper compares blockchain-based approaches to these problems and examines when their benefits justify the added costs. It synthesizes published work rather than presenting a new implementation or experimental benchmark.

## Key Findings

| Federated learning challenge | Blockchain-based approach | Potential benefit | Remaining trade-off |
|---|---|---|---|
| Dependence on a central coordinator | Peer-to-peer coordination and distributed consensus | Distributes responsibility for coordinating training rounds | Additional communication, confirmation latency, and validator overhead |
| Weak incentives and participant attrition | Smart contracts linked to contribution scoring | Makes reward rules and distributions auditable | Scoring can be costly, and frequent on-chain payments can accumulate fees |
| Limited visibility into update provenance | On-chain records of update commitments and training-round metadata | Supports verification of the recorded training history | Ledger growth and potential exposure of participation patterns |

A central distinction is that **auditability is not the same as update quality**. A ledger can help verify that an update was recorded, but it does not establish that the update is useful, benign, or private. Likewise, a smart contract can apply reward rules consistently without establishing whether the underlying contribution score is fair.

## Survey Scope

1. **Foundations:** Federated learning workflows, blockchain consensus, smart contracts, and public, private, and consortium networks.
2. **Limitations of conventional federated learning:** Centralized coordination, weak incentives, and insufficient auditability.
3. **Blockchain mechanisms:** Distributed coordination, programmable rewards, and verifiable records of training activity.
4. **Deployment trade-offs:** How performance costs, access control, and accountability requirements affect the choice of architecture.

## Applications Discussed

| Domain | Example considered in the literature | Design consideration |
|---|---|---|
| Healthcare | Collaborative model training across institutions | Record each institution’s contribution without exposing sensitive data or unnecessary metadata |
| Finance | Cross-institutional fraud or anti-money-laundering modelling | Balance auditability and access control across independently governed participants |
| Internet of Things | Collaborative learning across connected devices and vehicular networks | Account for limited compute, bandwidth, and the cost of participating in consensus |

## Limitations and Future Work

- **Scaling:** Evaluate Layer-2 and off-chain coordination approaches against the latency and communication costs of recording interactions directly on-chain.
- **Privacy-preserving verification:** Explore zero-knowledge proofs for checking specific claims without exposing the underlying information, while accounting for proof-generation and verification costs.
- **Contribution evaluation:** Compare efficient scoring methods, including Shapley-value approximations, on computational cost and how well they reflect the usefulness of participant updates.

The survey’s conclusion is that blockchain is a selective design choice rather than a default replacement for centralized aggregation. Its strongest case is in settings where several organizations need independently verifiable coordination and where that requirement justifies the overhead.

## Repository Structure

```text
.
├── README.md    # Survey overview and key findings
└── Paper.pdf    # Full technical survey, including references
```

## Author

Wai-Shing Ng  
School of Computing and Data Science  
The University of Hong Kong

## Academic Context

This repository shares an academic literature review. It does not contain training code, datasets, smart contracts, or a deployable system. The full bibliography is included in the paper.
