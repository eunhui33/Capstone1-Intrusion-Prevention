# Capstone1 – Intrusion Prevention System for IoT Networks (Blockchain + AI)


## 📘 Overview
This project implements a **dual-layer IoT security application** that integrates:
1. **Blockchain-based Decentralized Identity (DID)** authentication for secure user access  
2. **AI-powered Intrusion Detection System (IDS)** that detects and blocks abnormal network traffic in real time  

The system ensures both **identity-level** and **network-level** security for IoT environments.  
It uses the **CIC-IDS2018 dataset** and an **MLP (Multilayer Perceptron)** model to classify traffic as *normal* or *abnormal*.
+ This dual-architecture enhances IoT resilience against spoofing, unauthorized access, and real-time intrusion attempts.

> 🏆 *Awarded “Best Undergraduate Research Paper” at KCSE 2025 (Korean Conference on Software Engineering)*

---

## ⚙️ Tech Stack
| Category | Tools / Libraries |
|-----------|------------------|
| **Language** | Python 3.10 |
| **AI / ML** | scikit-learn (MLP – my implementation), CatBoost (selected for deployment) |
| **Data Processing** | Pandas, NumPy, imbalanced-learn (SMOTE) |
| **Packet Capture & Flow Features** | tcpdump, tshark, CICFlowMeter |
| **Backend / API** | FastAPI |
| **Infrastructure / Deployment** | Linux, Naver Cloud Platform (NCP, AWS-equivalent) |
| **IoT Testbed** | Raspberry Pi |
| **Visualization & Evaluation** | Matplotlib, Seaborn |
| **Dataset** | CSE-CIC-IDS2018 (Canadian Institute for Cybersecurity) |

---

## 💻 My Contributions
- Develop an AI-based real-time intrusion prevention system for IoT.
- Developed MLP-based intrusion detection model (F1=0.937) trained on CIC-IDS2018 network traffic data
- Built automated detection pipeline (tshark → CICFlowMeter → FastAPI) for live traffic analysis and blocking
- Deployed system on Naver Cloud Platform (IaaS, comparable to AWS) and simulated DDoS and brute-force attacks using Raspberry Pi test environment.
- Led a 4-member team as project lead, coordinating AI model development, backend integration, milestone delivery, and weekly technical reporting to the faculty advisor.


---

## 📊 Results
| Model | Accuracy | AUC | MCC |
|--------|-----------|---------|-----|
| **MLP (my model)** | 0.9581 | 0.9714 | 0.8740 |
| CatBoost (team baseline) | 0.9370 | 0.9808 | 0.8240 |

> ✅ We trained both MLP and CatBoost models and selected CatBoost for deployment
> based on overall reliability and operational suitability for real-time inference.
---

## 🏅 Recognition & Documents
-  *Best Undergraduate Research Paper — KCSE 2025* **[View Award (PDF)](./paper/KCSE2025_Best_Undergraduate_Paper_Certificate.pdf)**
-  Paper (Korean): **[KCSE 2025 IoT IDS Paper (PDF)](./paper/KCSE2025_IoT_IDS_Paper_KR.pdf)**


---

## 🧩 Repository Structure
```
Capstone1-Intrusion-Detection/
├── README.md
├── src/
│ ├── training/
│ │ ├── model_train.py      # MLP training pipeline (main)
│ │ └── model_baseline.py   # initial experiment version
│ ├── inference/
│ │ └── app_fastapi.py      # real-time FastAPI backend
├── paper/
│   ├── KCSE2025_Best_Undergraduate_Paper_Certificate.pdf
│   └── KCSE2025_IoT_IDS_Paper_KR.pdf
├── images/                       # confusion matrix / training curves
└── requirements.txt
```
