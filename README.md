
# ⚡ EV Charging Station Cyberattack Detection Framework 🔐

This project implements a **two-phase machine learning framework** to **detect and classify cyberattacks** on Electric Vehicle Charging Infrastructure (EVCS). The system is designed for **real-time responsiveness**, combining lightweight binary detection with multi-class attack identification.

---

## 🚦 Framework Architecture

```
            ┌────────────────────┐
            │  Incoming EV Data  │
            └─────────┬──────────┘
                      │
              ┌───────▼────────┐
              │  Phase 1:      │
              │  Monitoring    │
              │  (Binary Class)│
              └───────┬────────┘
         Normal (0)   │   Attack (1)
                      ▼
              ┌───────────────┐
              │ Phase 2:      │
              │ Identification│
              │ (Multi-Class) │
              └─────┬─────────┘
                    ▼
     ┌──────────────┼──────────────────────┐
     │              │                      │
   DoS           Recon              Host-Attack
```

---

## 🧠 Phase 1: Monitoring (Binary Classification)

- **Purpose**: Detect whether an incoming data stream is normal or malicious.
- **Input Feature Vector**:
  ```
  Θ_i = {V_i, I_i, P_i = V_i * I_i, S_i}
  ```
- **Function**:
  ```
  f1: ℝⁿ → {0, 1}
  ```
- **Output**:
  - 0 → Normal
  - 1 → Suspicious (Proceed to Phase 2)

---

## 🔍 Phase 2: Identification (Multi-Class Classification)

- **Purpose**: Classify the detected anomaly into specific attack types.
- **Classes**:
  ```
  𝒯 = {DoS, Recon, Host-Attack, ...}
  ```
- **Function**:
  ```
  f2: ℝⁿ → 𝒯
  ```
- **Output**: Specific attack label (e.g., DoS)

---

## ✅ Features

- Real-time detection from voltage/current/state inputs
- Lightweight binary classification for fast reaction
- Detailed multi-class classification for deeper analysis
- Modular and extensible design

---


---
