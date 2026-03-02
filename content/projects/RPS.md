---
title: "Human Final Hand Gesture Prediction"
image: "/images/RPS/rps_demo.gif"
badges: ["R&D / CV / CNN / GRU"]
tags: ["AI", "Computer Vision", "GRU", "CNN", "Transfer Learning", "Fine-Tuning"]
links:
  - icon: fab fa-github
    url: "https://github.com/YuriMatyash/Human-hand-gesture-prediction---RockPaperScissors"
  - icon: fas fa-globe
    url: "https://yurimatyash.github.io/project-demo"
summary: "Human Final Gesture Prediction, showcased through a game of Rock Paper Scissors.\n\n Researched and designed a model pipeline utilizing CV, keypoint extraction and GRU for temporal analysis to predict the final human hand gesture.\n\nShowcased at Holon's insititue of technology, and was presented to an Azerbaijan delegation visiting HIT"

---
---
Human Final Gesture Prediction, showcased through a game of Rock Paper Scissors.
Full Documentation & Source Code on **[🔗 GitHub](https://github.com/YuriMatyash/Human-hand-gesture-prediction---RockPaperScissors)**

---

### 🎯 The Problem: Input Latency in Human-Computer Interaction
In traditional gesture recognition, a system must wait for a human to finish moving before it can classify the pose, introducing a natural bottleneck. To create truly interactive and intuitive systems (such as assistive tech or human-robot collaboration), the computer must be able to infer intent *during* the motion.

### 🧠 Technical Architecture & Strategy
Researched & Developed from September 2024 to September 2025, this pipeline focuses on predictive recognition under incomplete input conditions. It captures temporal sequences and physical kinematics to predict the final gesture before the user completes it.

* **Keypoint Extraction:** A dedicated Computer Vision model identifies and tracks hand landmarks in real-time, stripping away environmental noise to focus purely on skeletal kinematics.
* **Early Prediction (GRU):** Instead of static classification, the system feeds the temporal sequence of landmarks into a Gated Recurrent Unit (GRU). This allows the model to learn the "evolution" of a gesture and predict the final state early.
* **Static Pose Verification:** A secondary static classifier runs post-movement to verify the final pose and reinforce system accuracy.

### 🛠️ Engineering Highlights
* **Hardware Integration & Edge Deployment:** The predictive model was deployed on a Raspberry Pi. It communicates via UDP to physically actuate a bionic hand based on the GRU's early predictions.
* **Latency Management:** Successfully balanced the software's early-prediction speed with the physical mechanical latency of the servo motors, ensuring the robotic counter-gesture lands naturally.
* **Resource-Efficient Learning:** Designed the architecture to achieve high accuracy without requiring massive GPU compute. The system was trained on an intentionally constrained, noisy dataset to force robust generalization over brute-force memorization.