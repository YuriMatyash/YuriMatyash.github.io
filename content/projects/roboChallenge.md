---
title: "RoboChallenge - Line follower"
image: "/images/roboChallenge/demo.gif"
badges: ["Algorithms / Robotics"]
tags: ["Computer Vision", "GRU", "CNN", "Transfer Learning", "Fine-Tuning"]
links:
  - icon: fab fa-github
    url: "https://github.com/YuriMatyash/RoboChallenge"
  - icon: fas fa-globe
    url: "https://yurimatyash.github.io/project-demo"
summary: "Lead software development in the Israeli's RoboChallenge line following team.\n\nHandled software and algorithms development as part of a 7 man team.\n\nCompeting in the 2025 Line follower annual competition"

---
---
RoboChallenge: High-Speed Autonomous Navigation & Control

Full Documentation & Source Code on **[🔗 GitHub](https://github.com/goodlancer-org/hetz)**

---

### The Problem: Stability at the Physical Limit

In competitive line following, the challenge is maintaining maximum velocity without losing track adhesion or inducing oscillations. Navigating sharp curves, 90-degree turns, and gaps requires a control system capable of sub-millisecond reaction times and high-precision error correction.

### Technical Architecture & Strategy

I Led the development of a deterministic software stack designed to handle high-frequency sensor data and translate it into smooth, high-torque motor responses.

* **Adaptive PID Control** - Engineered a dynamic control loop that scales proportional and derivative gains based on current velocity, ensuring stability in straights and aggressive turning in corners.
* **Weighted Sensor Fusion** - Implemented a high-speed polling routine for an 8-sensor IR array, using weighted average algorithms to interpolate the line's center with sub-millimeter precision.
* **State-Machine Logic** - Developed a robust finite state machine (FSM) to manage complex race scenarios, including start-line detection, intersection handling, and emergency braking.

### Engineering Highlights
* **Low-Latency Firmware** - Optimized the control loop for bare-metal execution in Embedded C++, minimizing interrupt latency and ensuring consistent PWM delivery to the drive train.
* **Hardware-Software Co-Design** - Collaborated on motor driver selection and sensor placement geometry to maximize the effectiveness of the derivative control and reduce physical "hunting" on the track.
* **Technical Ownership** - Directed the complete software and algorithmic roadmap, selecting the microcontroller platform and defining the architectural approach to ensure system reliability under competitive stress.