# Smart Water Security with AI and Blockchain-Enhanced Digital Twins

This repository contains the implementation of a secure, intelligent digital twin (DT) platform for rural water distribution networks. The system integrates **LoRaWAN-based data acquisition**, an **AI-powered Intrusion Detection System (IDS)** using **LSTM Autoencoder and Isolation Forest**, and a **private Ethereum blockchain** with **Proof of Authority (PoA)** to ensure tamper-proof and transparent water management.

---

## 🌐 Project Description

Water systems in under-connected rural areas are vulnerable to data tampering, inefficiencies, and delayed responses. This project proposes a modular framework combining:

- Digital Twins for real-time monitoring and forecasting.
- Blockchain for secure data storage and billing automation.
- AI for early leak detection and cyberattack prevention.

![Digital Twin Platform](./results/Digital_Twins.png)

*Figure 1: Digital Twin Architecture Overview*

---

## 🔧 Technologies Used

| Component        | Technology        |
|------------------|-------------------|
| Sensor Layer     | LoRaWAN (Simulated) |
| IDS              | LSTM Autoencoder + Isolation Forest |
| Blockchain       | Ethereum (Private, PoA) |
| Smart Contracts  | Solidity (Water Meter Logging) |
| Visualization    | Grafana, Prometheus |
| Deployment       | Docker, Python, Web3.py |

---

## 📦 Key Features

- 🔐 **Hybrid IDS** filters spoofed, replayed, and anomalous records.
- 🧠 **LSTM Autoencoder** detects time-based anomalies.
- 🌲 **Isolation Forest** flags statistical outliers.
- ⛓️ **Smart Contracts** manage meter registration and payments.
- 🚿 **Leak Detection** through night-time pattern analysis.
- ⚡ **Real-Time Monitoring** with Web3 + Digital Twin UI.
- 💶 **Cost-Efficient** with < €50/month PoA infrastructure.

---

## 📁 Directory Structure

.
├── algorithms/ # AI IDS implementation
├── contracts/ # Smart contract (Solidity)
├── data/ # Sample water consumption datasets
├── docker/ # Private Ethereum network setup
├── notebooks/ # IDS training and visualization
├── results/ # Figures and evaluation results
└── README.md



---

## 📜 Smart Contract Overview

The Solidity smart contract handles:

- `registerMeter()` for adding new meters
- `logWaterData()` for secure logging
- `calculatePayment()` for auto billing
- `getWaterLogs()` for auditing

```solidity
struct WaterData {
    uint256 timestamp;
    uint256 waterUsage;
    uint256 errorCode;
    string meterId;
}
mapping(string => WaterData[]) public waterLogs;
function logWaterData(string memory id, uint256 usage, uint256 errCode) public { ... }

Figure 2: Blockchain Smart Contract Flow

🧪 IDS Evaluation Results
Anomaly detection was tested on 400 real/simulated meters with synthetic attack injections.


Figure 3: Precision, Recall, and F1 per Attack Type

🚿 Leak Detection Example
Water meters showing non-zero consumption between 00:00–06:00 are flagged.


Figure 4: Night Consumption of Leaking Meter

## ⚙️ Performance & Scalability

### Transaction Latency and Throughput

| **Batch Size** | **TPS** | **Mean Latency (s)** | **Max Latency (s)** |
|----------------|---------|----------------------|----------------------|
| 1              | 110     | 1.2                  | 2.1                  |
| 5              | 96      | 1.5                  | 2.4                  |
| 10             | 89      | 1.7                  | 2.8                  |
| 20             | 81      | 2.1                  | 3.5                  |



## 💰 Cost Estimation (6-Month Pilot)

| **Component**     | **Cost (EUR)** | **Notes**                                 |
|-------------------|----------------|-------------------------------------------|
| Hetzner VPS       | €120–300       | Server hosting for validator nodes        |
| Maintenance       | ~€50           | Occasional updates                        |
| Energy            | Included       | Covered by provider                       |
| Smart Contracts   | Near-zero      | Custom PoA with gas price = 0             |





🤝 Acknowledgments
This project is part of the Spanish C107/23 initiative:
"Artificial Intelligence Applied to Cybersecurity in Critical Water and Sanitation Infrastructures"
Funded by the European Union – Next Generation EU, coordinated by INCIBE.




📚 Citation
If you use this work, please cite:

@inproceedings{Homaei2025WaterDT,
  title={Smart Water Security with AI and Blockchain-Enhanced Digital Twins},
  author={Mohammadhossein Homaei and Víctor González Morales and Óscar Mogollón Gutiérrez and Rubén Molano Gómez and Andrés Caro},
  booktitle={IEEE Conference},
  year={2025}
}

