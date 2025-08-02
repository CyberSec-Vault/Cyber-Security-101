# 🔧 TCP Tools for Scanning, Analyzing, and Diagnostics

This document outlines essential tools used to scan, analyze, test, and troubleshoot TCP connections across various environments.

---

## 📡 1. Port Scanning Tools

These tools identify open TCP ports and detect services running on a host.

| Tool         | Description |
|--------------|-------------|
| **Nmap**     | Powerful scanner that detects open ports, services, OS, and more. <br> 🧪 Example: `nmap -sT example.com` |
| **Masscan**  | High-speed scanner capable of scanning the entire internet. <br> ⚡ Example: `masscan -p1-65535 example.com` |
| **Unicornscan** | Asynchronous TCP/UDP scanner used for advanced network recon. |
| **ZMap**     | Efficient scanner for large-scale internet measurement research. |

---

## 📈 2. Packet Sniffing & Traffic Analysis

These tools capture and analyze TCP traffic for visibility into packet flows, retransmissions, and connection issues.

| Tool         | Description |
|--------------|-------------|
| **Wireshark** | GUI-based packet analyzer with powerful filters and visualization tools. |
| **tcpdump**   | CLI packet capture tool. <br> 📄 Example: `tcpdump tcp` |
| **Tshark**    | CLI version of Wireshark; great for scripting and automation. |
| **Netcat (`nc`)** | Lightweight utility for reading/writing TCP data. <br> 📡 Example: `nc -lvp 4444` (listen) |

---

## 🚀 3. TCP Performance & Load Testing

Tools to test bandwidth, latency, and simulate load using TCP connections.

| Tool         | Description |
|--------------|-------------|
| **iperf / iperf3** | Measures TCP/UDP bandwidth, latency, jitter, and packet loss. <br> 🔄 Example: `iperf3 -s` (server) and `iperf3 -c host` (client) |
| **hping3**    | TCP packet crafter for testing firewalls, scanning ports, and simulating TCP flags. |
| **Netstat / ss** | Shows active TCP/UDP connections and socket statistics. <br> 🔍 Example: `ss -tuln` |

---

## 🌐 4. TCP Traceroute (Route Diagnostics over TCP)

Traceroute over TCP is helpful when ICMP or UDP traffic is blocked by firewalls.

### 🔹 Tool: `tcptraceroute`

**Purpose:** Traces the path to a host using TCP SYN packets (e.g., to port 80/443), useful in firewall-restricted environments.

#### ✅ Benefits:
- Works when ICMP is filtered but TCP is allowed.
- Traces TCP routes through stateful firewalls.
- Ideal for application-level diagnostics.

#### 🔧 Installation:
```bash
# Debian/Ubuntu
sudo apt install tcptraceroute
