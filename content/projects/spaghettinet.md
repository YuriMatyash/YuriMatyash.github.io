---
title: "SpaghettiNet"
image: "/images/spaghettiNet/demo.gif"
badges: ["Computer Vision", "GRU", "CNN", "Transfer Learning", "Fine-Tuning"]
tags: ["AI", "3D Printing", "Computer Vision", "GRU", "CNN", "Transfer Learning", "Fine-Tuning"]
links:
  - icon: fab fa-github
    url: "https://github.com/YuriMatyash/SpaghettiNet"
  - icon: fas fa-globe
    url: "https://yurimatyash.github.io/project-demo"
summary: "Live mid-print 3D printing failure detection system\n\n designed detect and notify about failing prints, saving materials, time and money for the end user."

---
---
BigPrintProtector: Multi-Model Edge AI for 3D Printing Safety   
Full Documentation & Source Code on **[🔗 GitHub](https://github.com/YuriMatyash/SpaghettiNet_3D-printer-spaghetti-detection)**

---

### The Problem: Print detachment and mid print artifacts

3D printing is a high-latency process where a single bed adhesion failure can lead to hours of wasted material and potential hardware damage. I developed an automated monitoring system to act as a "digital eye," terminating prints the moment a failure is detected.

### Technical Architecture & Strategy

I engineered a hybrid pipeline to handle different failure modes, prioritizing Recall to ensure no hardware damage goes undetected.

* **Failure Classification** - A CNN-based classifier achieving 100% Recall on validation sets to identify tangled filament.
* **Temporal Anomaly Detection** - A hybrid CNN+RNN architecture that analyzes 16-second single frame videos windows to distinguish between normal printing behavior and the aftermath of a detached print.
* **Toolhead Tracking** - Developed a YOLO-based object detection model (90% mAP@50) for real-time spatial tracking of the extruder.

### Engineering Highlights
* **Custom Data Engineering** - Curated and annotated a proprietary dataset from hundreds of hours of failure footage, utilizing AnyLabeling for precision ground-truth data.
* **emporal Consistency Augmentation** - Developed a custom augmentation pipeline that applies identical transformations across frame sequences to prevent "strobe-light" artifacts in the GRU.
* **Edge Optimization** - Optimized models for low-latency inference on Raspberry Pis(Commonly used as the "brain" for 3D printers), although inference on the end users PC is also possible.