---
title: "LLM agentic JailBreaking FrameWork"
image: "/images/LLMJailbreak/agents_flowchart.png"
badges: ["Agent Framework"]
tags: ["Agents", "Model Alignment", "Jailbreaking", "LLM"]
links:
  - icon: fab fa-github
    url: "https://github.com/YuriMatyash/ML-Guided-Cyber-Security"
  - icon: fas fa-globe
    url: "https://yurimatyash.github.io/project-demo"
summary: "An automated research framework utilizing a multi-agent 'judge-mutator' architecture to evaluate LLM robustness against adversarial injections."

---
---
Automated LLM Red-Teaming: Multi-Agent Evolutionary Jailbreaking   
Full Documentation & Source Code on **[🔗 GitHub](https://github.com/YuriMatyash/ML-Guided-Cyber-Security)**

---

### The Problem: The Alignment Gap

Large Language Models (LLMs) often face a conflict between "Helpfulness" and "Harmlessness". While they are trained with safety guardrails, sophisticated social engineering can bypass these filters. I developed an automated framework to systematically identify these safety boundary vulnerabilities using an evolutionary mutation approach.

### Technical Architecture & Strategy

The framework employs a specialized multi-agent pipeline, selecting specific models based on their architectural strengths to maximize red-teaming efficacy.

* **Reasoning-Based Mutation** – Leveraged DeepSeek-R1 (8B) for its Chain-of-Thought (CoT) capabilities, allowing it to "think" through complex social engineering strategies and linguistic obfuscation.
* **Adversarial Evaluation** – Utilized Qwen3 (14B) as the target model to test robust internal safety guardrails against industry-standard "Harmful Intent" prompts from the JailbreakBench dataset.
* **Structured Safety Scoring** – Implemented Llama 3.1 (8B) as an impartial judge to extract safety metrics and provide consistent JSON evaluations for the final database.

### Engineering Highlights
* **Evolutionary Mutation Logic** – Engineered a "Survival of the Fittest" algorithm where the "fitness" of a prompt is optimized based on a combined score of low harmlessness and high goal fulfillment.
* **Dynamic VRAM Management** – Overcame a 16GB VRAM hardware constraint by implementing a sequential loading and "Force Unload" strategy (sending keep_alive: 0 signals) to flush models from GPU memory between agent tasks.
* **Technical Ownership** – Defined the entire algorithmic roadmap, including the selection of the "Judge-Mutator" architecture and the implementation of robust regex-based extraction to handle quantization-induced JSON failures.
* **Lineage Tracking** – Developed a system to store mutation "family trees" (using parent_id), allowing for the reconstruction of exactly which social engineering tactic triggered a successful jailbreak.