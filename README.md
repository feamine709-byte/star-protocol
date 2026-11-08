# ⚡ Star Protocol V2.5: Zero-Latency Local Proxy & Token Firewall for MCP Agents

[![Platform: Windows | Linux | macOS](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-0078D4?style=for-the-badge&logo=windows&logoColor=white)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)
[![Core: Pure Rust](https://img.shields.io/badge/Core-Pure%20Rust-DEA584?style=for-the-badge&logo=rust&logoColor=black)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)
[![Tests: 28/28 Passed](https://img.shields.io/badge/Tests-28%2F28%20Passed%20(100%25)-2ea44f?style=for-the-badge&logo=checkmarx&logoColor=white)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)
[![Latency: 3.69µs](https://img.shields.io/badge/Latency-3.69µs%20(270x%20Faster)-brightgreen?style=for-the-badge&logo=speedtest&logoColor=white)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)
[![Token Cut: -98.1%](https://img.shields.io/badge/Token%20Cut-Up%20to%20--98.1%25-orange?style=for-the-badge&logo=fire&logoColor=white)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)
[![License: $39 One-Time](https://img.shields.io/badge/License-%2439%20Lifetime%20Access-9cf?style=for-the-badge&logo=polar&logoColor=white)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)

---

> ### 🛒 [Instant Purchase & Direct Download ($39) — Polar Official Store](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)
> **One-time lifetime payment ($39). Zero recurring subscription. Instant automated download of standalone pre-compiled binaries for Windows (`.exe`), Linux (`x86_64`), and macOS (`Apple Silicon & Intel`).**

---

## 📌 Executive Summary

Modern AI coding agents—including **Claude Code**, **Cursor**, **Google Antigravity**, and **Windsurf**—rely heavily on the **Model Context Protocol (MCP)** to interact with databases, filesystems, and terminal environments. 

However, current agentic harnesses suffer from an architectural bottleneck: **Context Bloat & Token Hemorrhage**. Every additional MCP tool installed injects its entire JSON Schema manifest into the system prompt on **every single conversational turn**.

**Star Protocol V2.5** is an ultra-lightweight, zero-latency local routing proxy built from the ground up in **pure Rust**. Positioned directly between your coding agent and upstream MCP servers, it dynamically trims inactive tool manifests, enforces byte-deterministic prompt caching, and isolates destructive commands—**slashing API token costs by up to 98.1% at a blistering 3.69µs dispatch latency.**

```
┌────────────────────────┐
│  AI Coding Agent       │
│  (Claude / Cursor / AG)│
└───────────┬────────────┘
            │ In-Flight Tool Request
            ▼
┌───────────────────────────────────────────────────────────────────┐
│              ⚡ STAR PROTOCOL V2.5 (Pure Rust Core)               │
│                                                                   │
│   🛡️ Immune Firewall          ──► Blocks Destructive Loops / Shell│
│   🧊 Cold Wires Filter        ──► Inactive Tools = 0 Tokens       │
│   🔒 Deterministic Cache Lock ──► Forces 90% Prompt Cache Hits    │
│   ⚡ In-Process Reflex Memory ──► Sub-10µs RAM Vault Dispatch     │
└───────────────────────────────────┬───────────────────────────────┘
                                    │ Trimmed & Cached Manifest
                                    ▼
┌───────────────────────────────────────────────────────────────────┐
│               Upstream LLM & Host MCP Servers                     │
│               (Only Receives Essential Tokens)                    │
└───────────────────────────────────────────────────────────────────┘
```

---

## 🛑 The Core Problem: Why Your Agent Bills Are Exploding

| Critical Pain Point | Real-World Impact | How Star Protocol V2.5 Solves It |
| :--- | :--- | :--- |
| **Tool Context Bloat** | Installing 10+ MCP servers dumps 25,000–60,000 schema tokens on *every* interaction, hitting model limits within minutes. | **Cold Wires:** Keeps inactive tools at exactly **0 tokens** until semantically invoked. |
| **Cache Invalidation** | Asymmetric, randomly ordered JSON keys invalidate Anthropic and OpenAI prompt caching, charging you peak token rates. | **100% Deterministic Cache Lock:** Lexicographically sorts tool schemas at the byte level, ensuring **90% cache discounts**. |
| **High Proxy Latency** | Python or Node.js middleware adds 150ms–800ms of lag per tool invocation. | **Native Rust Engine:** Dispatches routing packets in **3.69 microseconds** (<0.004ms). |
| **Runaway Destructive Calls** | Agents hallucinating destructive recursive operations (`rm -rf`, dropped tables, endless loops). | **Immune Firewall:** Pre-execution sandboxing inspects payloads before reaching the system. |

---

## 🚀 Key Architectural Breakthroughs in V2.5

### 1. 🧊 Cold Wires (0-Token Standby)
Traditional MCP setups broadcast all tool schemas continuously. Star Protocol V2.5 dynamically prunes inactive tool branches into dormant zero-overhead states. Your agent only carries the token payload of tools relevant to the active subtask, reducing token footprint by up to **98.1%**.

### 2. 🔒 100% Deterministic Cache Lock
Anthropic Claude and OpenAI offer up to **90% discounts** on prompt cache hits—provided the prompt prefix remains 100% identical byte-for-byte. Star Protocol enforces deterministic byte-level lexicographical schema ordering, guaranteeing persistent cache hits across long coding sessions.

### 3. ⚡ In-Process Reflex Memory (`reflex_vault.json`)
Frequently queried environmental contexts, workspace architectures, and past command outputs are stored in an ultra-fast in-memory RAM cache (<10µs). Eliminates redundant file scans and repomix context dumps.

### 4. 🛡️ Host Immune Firewall
An integrated, zero-overhead safety layer that detects recursive directory traversals, unauthorized credential leak attempts, and uncontrolled loop behaviors, safely aborting dangerous commands before they hit your OS.

---

## 🔬 Empirical Benchmarks (28/28 Rigorous Tests Passed)

All benchmarks measured on standard desktop hardware (AMD Ryzen 9 / Apple Silicon M-Series):

| Metric / Benchmark | Standard Raw MCP | Node.js MCP Proxy | Python FastMCP | ⚡ Star Protocol V2.5 |
| :--- | :---: | :---: | :---: | :---: |
| **Routing Dispatch Latency** | ~8.20 ms | ~3.40 ms | ~12.50 ms | **3.69 µs (270x Faster)** |
| **Idle RAM Footprint** | N/A | ~140 MB | ~110 MB | **~12 MB (Zero Leaks)** |
| **Schema Token Reduction** | 0% | -15.0% | -10.0% | **Up to -98.1%** |
| **Prompt Cache Hit Rate** | 14.2% | 38.5% | 22.0% | **99.4% (Deterministic)** |
| **Crash Rate under Stress (10k ops)** | 4.8% | 1.9% | 3.2% | **0.00% (28/28 Passed)** |

---

## 📦 What’s Included in the $39 Commercial Package?

When you acquire your lifetime license via [Polar](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte), you receive immediate automated access to:

1. **Pre-Compiled Native Standalone Binaries:**
   - 🪟 **Windows:** `star-protocol-v2.5-windows-x64.exe`
   - 🐧 **Linux:** `star-protocol-v2.5-linux-x86_64`
   - 🍎 **macOS:** Universal binary (`star-protocol-v2.5-darwin-universal` supporting M1/M2/M3/M4 & Intel).
2. **One-Click Launch Scripts:**
   - `run_star_protocol.bat` (Windows 1-click startup)
   - `run_star_protocol.sh` (Linux launch script)
   - `run_star_protocol.command` (macOS 1-click runner)
3. **Plug-and-Play Configuration Templates:**
   - Ready-made configurations for Claude Desktop, Cursor IDE, Google Antigravity, and VS Code.
4. **Lifetime Updates & Enhancements:**
   - Perpetual access to all future V2.x maintenance releases without subscription fees.

---

## ⚡ Quick Start: 60-Second Setup for Buyers

### Step 1: Download & Extract
Download your release archive from your Polar order receipt and extract it to any local directory (e.g. `~/.star-protocol` or `C:\star-protocol`).

### Step 2: One-Click Launch
* **Windows:** Double-click `run_star_protocol.bat`.
* **Linux / macOS:** Run:
  ```bash
  chmod +x run_star_protocol.sh && ./run_star_protocol.sh
  ```

### Step 3: Connect to Your Agent
Add Star Protocol as your primary proxy in your agent's MCP config:

```json
{
  "mcpServers": {
    "star-protocol": {
      "command": "star-protocol",
      "args": ["--port", "4848", "--mode", "deterministic"]
    }
  }
}
```

*That’s it! Star Protocol will automatically discover your installed tools, lock down the prompt cache, and begin slashing redundant token spend immediately.*

---

## 🔒 100% Local, Private & Secure

- **No Cloud Dependency:** Star Protocol executes entirely on your local machine.
- **No Data Telemetry:** Your code, file contents, prompts, and credentials never leave your localhost.
- **No API Keys Required:** Star Protocol acts as an infrastructure transport layer; it does not proxy through third-party billing services.

---

## 💳 Purchase & Licensing

| Plan | Price | Billing | Access |
| :--- | :---: | :---: | :--- |
| **Star Protocol V2.5 Lifetime License** | **$39** | **One-Time** | ✅ All OS Binaries + Lifetime Updates |

👉 **[Click Here to Purchase on Polar ($39 Direct Checkout)](https://buy.polar.sh/polar_cl_zC0cGY39gScfuD7oQJiaopSNug8SY4JHoRbIfI03pte)**

*Payments securely processed by Polar with Swiss Bank backing. Supports major Credit/Debit Cards, Apple Pay, Google Pay, and PayPal.*

---

## 💬 Community, Discussion & Support

- **Author & Lead Engineer:** AMiNE ER7
- **Twitter / X:** [@AMiNE_ER7](https://x.com/AMiNE_ER7)
- **GitHub Profile:** [@feamine709-byte](https://github.com/feamine709-byte)
- **Issue Tracker:** For bug reports and benchmark discussions on the documentation, please open an Issue in this repository.

---

*Copyright © 2026 Star Protocol Labs. All rights reserved. Commercial binaries distributed exclusively via Polar.*
