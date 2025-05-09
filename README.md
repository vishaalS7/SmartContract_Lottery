# 🏆 Raffle Smart Contract

## Overview

This is a decentralized Raffle (lottery) smart contract built on Solidity, leveraging [Chainlink VRF v2.5](https://docs.chain.link/vrf/v2-5/introduction) for randomness and [Chainlink Automation](https://docs.chain.link/chainlink-automation/introduction) for periodic execution.

> **Author:** [@0xVishh](https://github.com/0xvishh)  
> **Inspired by:** [Cyfrin's Foundry Course (Patrick Collins)](https://github.com/Cyfrin/foundry-full-course-f23)  
> **Purpose:** Learning & Experimentation

---

## 🔧 Features

- 🎟 Enter a raffle by sending ETH
- ⏱ Automated upkeep using Chainlink Automation
- 🎲 Random winner selection via Chainlink VRF v2.5
- 🔒 Uses `enum` to manage state (`OPEN`, `CALCULATING`)
- 🧪 Fully tested with Foundry

---

## 🧠 Architecture

- `enterRaffle()` — Players enter the raffle
- `checkUpkeep()` — Chainlink Automation determines if it's time to pick a winner
- `performUpkeep()` — Triggers Chainlink VRF request
- `fulfillRandomWords()` — Chainlink VRF returns randomness to select winner

---

## 🧱 Tech Stack

- **Solidity:** ^0.8.19
- **Foundry:** Forge, Anvil
- **Chainlink:**
  - VRF v2.5 (randomness)
  - Automation (timed execution)
- **Test Framework:** Forge standard tests (`.t.sol`)
- **Scripting:** Deploy, interaction, and helper config scripts

---

## 📂 Project Structure

```
.
├── contracts
│   └── Raffle.sol
├── script
│   ├── DeployRaffle.s.sol
│   ├── interactions.s.sol
│   └── HelperConfig.s.sol
├── test
│   └── RaffleTest.t.sol
├── lib
│   └── (Chainlink libraries & foundry-devops)
└── foundry.toml
```

---

## 🚀 How to Deploy

1. Configure your `.env` with your Chainlink subscription ID, VRF details, etc.
2. Deploy:
```bash
forge script script/DeployRaffle.s.sol --rpc-url <your_rpc_url> --private-key <your_key> --broadcast
```

---

## 🧪 Run Tests

```bash
forge test
```

---

## 🔍 Learnings & Insights

- How Chainlink VRF v2.5 differs from older versions.
- Using Foundry for unit testing, mocking, and scripting.
- Automation-compatible contracts and the importance of `checkUpkeep` vs `performUpkeep`.
- Managing state machines in smart contracts.

---

## 📜 License

MIT – Free for learning and educational purposes.
