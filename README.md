# EVOCLAW: Self-Evolving Multi-Agent Framework

**EVOCLAW** is a lightweight, high-performance framework for autonomous, self-evolving agents designed to run on resource-constrained Edge devices. 

By treating agent capabilities as a hot-swappable **Genome**, EVOCLAW allows agents to modify their behavior at runtime with zero downtime and a minimal footprint.

## 🚀 Key Features

- **Runtime Evolution**: Agents modify their own behavior via a declarative `genome.toml`.
- **Lightweight Footprint**: 3.0 MB static binary, requiring as little as 3.2 MB RAM.
- **Edge Optimized**: Designed to run on legacy hardware like the Raspberry Pi 1 (512MB RAM).
- **Autonomous Recovery**: Built-in resilience with exponential backoff and state persistence.
- **Multi-Tier Architecture**: Seamless orchestration across Edge, Server, and Cloud environments.

## 🏗️ Architecture

The framework consists of three primary layers:

1.  **Layer 1: Orchestrator (Go)**: Manages agent fleets, validates genome mutations, and enforces system constraints.
2.  **Layer 2: Message Bus (MQTT)**: Asynchronous communication using QoS 2 for reliable genome delivery and status reporting.
3.  **Layer 3: Edge Agent (Rust)**: The high-performance runtime engine that executes skills and handles hot-reloading.

## 📊 Performance

| Metric | Edge (Pi 1) | Server | Cloud (E2B) |
| :--- | :--- | :--- | :--- |
| **Binary Size** | 3.0 MB | 7.2 MB | N/A |
| **RSS Memory** | 3.2 MB | 12.4 MB | 45 MB |
| **Hot-Reload Time**| 108 ms | 35 ms | 60 ms |
| **CPU Usage** | 2.1% | 0.3% | 0.1% |

## 🛠️ Usage

The agent's behavior is defined in `genome.toml`:

```toml
[genome]
id = "pi1-edge-agent"
generation = 42
mutation_rate = 0.05

[skills.system_monitor]
enabled = true
interval_sec = 30

[skills.price_monitor]
enabled = true
symbols = ["BTC", "ETH"]
```

## 📝 Authors

- **Alex Chen** - Independent Researcher
- **Bowen Li** - Independent Researcher

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
