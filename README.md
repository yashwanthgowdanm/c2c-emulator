# 🛡️ C2 Traffic Emulator & Anomaly Detection Framework

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Status](https://img.shields.io/badge/Status-Educational-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📖 Overview
This project is a cybersecurity simulation framework designed to generate, capture, and analyze network traffic patterns. It simulates a **Red Team vs. Blue Team** scenario:

1.  **Red Team (Malware):** A C2 implant that "phones home" using randomized jitter (obfuscation) to evade detection.
2.  **Blue Team (Defense):** An automated analysis engine that uses **Machine Learning (Isolation Forest)** and **Statistical Variance** to distinguish mechanical beaconing from human noise.

The goal is to prove that even obfuscated malware retains a "statistical heartbeat" that differs from the chaotic variance of legitimate human web browsing.

## ✨ Key Features
* **Closed-Loop Simulation:** Runs the C2 Server, Malicious Implant, Benign User, and Packet Sniffer simultaneously in a multi-threaded environment.
* **Smart Jitter:** Malware uses randomized sleep intervals ($\pm$ 0.5s) to mimic human behavior.
* **Chaos Generator:** "Benign User" bot generates unpredictable, bursty HTTP traffic to create realistic noise.
* **ML Detection:** Uses `sklearn.ensemble.IsolationForest` to cluster traffic based on Inter-Arrival Time (IAT).
* **Variance Metrics:** Automatically calculates traffic variance to mathematically prove the presence of C2 channels.

## 🛠️ Installation

### Prerequisites
Ensure you have Python 3.x installed. The project relies on the following libraries:

```bash
pip install scapy flask pandas matplotlib scikit-learn
