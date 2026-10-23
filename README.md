# Hands-on with Agent Sandbox on Kubernetes

Welcome to the repository for the **"Hands-on with Agent Sandbox on Kubernetes"** workshop, originally delivered at **[Cloud Native Days Norway 2026](https://2026.cloudnativedays.no/speaker/abdel-sghiouar)** by **Abdel Sghiouar** (Senior Cloud Developer Advocate @ Google & CNCF Ambassador).

---

## Overview

As AI agents evolve from simple chatbots into autonomous systems capable of generating and executing code and manipulating data, they introduce significant security and operational challenges. Running LLM-generated code directly inside standard containers exposes your cluster to kernel exploits, lateral movement, and cloud credential theft.

This hands-on workshop explores **[Agent Sandbox (`kubernetes-sigs/agent-sandbox`)](https://github.com/kubernetes-sigs/agent-sandbox)**—a Kubernetes-native solution designed to run non-deterministic, untrusted AI agent workloads safely and efficiently on Google Kubernetes Engine (GKE).

### What You Will Learn

* **Bridge VM Safety & Container Speed:** Understand how Agent Sandbox leverages **gVisor (`runsc`)** to provide a user-space guest kernel runtime, isolating untrusted code from the host Linux kernel.
* **Kubernetes-Native Sandbox CRDs:** Orchestrate ephemeral code-execution environments using `Sandbox`, `SandboxTemplate`, `SandboxClaim`, and `SandboxWarmPool`.
* **Sub-Second Scaling with Warm Pools:** Eliminate container cold-start latency by maintaining a pre-warmed standby pool of gVisor sandboxes that are adopted in `<1 second` and automatically replenished.
* **Build Autonomous Code-Executing Agents:** Connect a **Google Agent Development Kit (ADK)** agent powered by **Gemini 2.5 Flash** to execute dynamic Python (`pandas`) workloads inside GKE sandboxes via the **Sandbox Router**.
* **Secure Your Cluster "When Agents Go Rogue":** Simulate adversarial/prompt-injected agent attacks (host filesystem escape, GCP Metadata Server SSRF at `169.254.169.254`, and internal cluster reconnaissance) and lock them down with zero-trust Kubernetes `NetworkPolicy` boundaries.

---

## Prerequisites & Google Cloud Credits

> [!IMPORTANT]
> **Google Cloud Account & Billing Requirement**  
> To complete this workshop, you need a **Google Cloud Account with Billing enabled**.  
> 
> 💡 **Need free credits?** You can join the **[Google Developer Program](https://developers.google.com/program)** at no cost to receive free Google Cloud credits that you can apply directly to your account for this workshop!

* **Estimated Runtime Cost:** `~$0.40 – $0.60 USD` for the 2-hour session (when you run the cleanup steps at the end of the workshop).
* **Tools Required:** Only a modern web browser! All commands and code execution run directly inside **Google Cloud Shell** (which comes pre-installed with `gcloud`, `kubectl`, `docker`, and `python3`).

---

## Workshop Structure

| Module | Topic | Est. Time |
| :--- | :--- | :--- |
| **[Module 0](./WORKSHOP.md#module-0-environment--cluster-setup)** | **Environment & Cluster Setup** (Cloud Shell & GKE Autopilot) | 20 min |
| **[Module 1](./WORKSHOP.md#module-1-the-anatomy-of-agent-sandbox--gvisor-isolation)** | **The Anatomy of Agent Sandbox & gVisor Kernel Isolation** | 20 min |
| **[Module 2](./WORKSHOP.md#module-2-templates-claims-warm-pools--the-sandbox-router)** | **Templates, Claims, Warm Pools & the Sandbox Router** | 25 min |
| **[Module 3](./WORKSHOP.md#module-3-building-an-autonomous-code-executing-agent-with-google-adk)** | **Building an Autonomous Code-Executing Agent with Google ADK** | 30 min |
| **[Module 4](./WORKSHOP.md#module-4-when-agents-go-rogue--hardening--adversarial-testing)** | **"When Agents Go Rogue" — Hardening & Adversarial Testing** | 20 min |
| **[Module 5](./WORKSHOP.md#module-5-cleanup-preserving-your-gcp-credits)** | **Cleanup** (Preserving your GCP credits) | 5 min |

---

## Getting Started

👉 **Start the step-by-step hands-on guide here: [WORKSHOP.md](./WORKSHOP.md)**
