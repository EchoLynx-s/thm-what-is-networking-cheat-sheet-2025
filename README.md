# TryHackMe: What is Networking? — 2025 Newcomer Cheat Sheet (EchoLynx)

A fast, practical companion for the **What is Networking?** room (Pre‑Security → Network Fundamentals). Exact Q&A, step‑by‑step flow, labs, and beginner‑friendly terms — updated for **2025**.

---

## TL;DR — What you’ll do
- **Task 1:** What a *network* is (things connected). Answer the key term.
- **Task 2:** What the *Internet* is (networks of networks), private vs public networks, WWW origin.
- **Task 3:** Identify devices (IP & MAC), do a MAC‑spoof lab and grab the flag.
- **Task 4:** Use **ping** (ICMP) and grab another flag.
- **Task 5:** Continue to **Intro to LAN** (next room).

---

## Room Q&A (exact answers)
- **Task 1:** *What is the key term for devices that are connected together?* → **Network**
- **Task 2:** *Who invented the World Wide Web?* → **Tim Berners‑Lee**
- **Task 3:**
  - *What does “IP” stand for?* → **Internet Protocol**
  - *What is each section of an IP address called?* → **Octet**
  - *How many sections (in digits) does an IPv4 address have?* → **4**
  - *What does “MAC” stand for?* → **Media Access Control**
  - *MAC‑spoof lab flag:* → **THM{YOU_GOT_ON_TRYHACKME}**
- **Task 4:**
  - *What protocol does ping use?* → **ICMP**
  - *Syntax to ping 10.10.10.10?* → **ping 10.10.10.10**
  - *Ping 8.8.8.8 flag:* → **THM{I_PINGED_THE_SERVER}**
- **Task 5:** *Join the Intro to LAN room* → **No answer needed**

---

## Step‑by‑step walkthrough
### Task 1 — What is Networking?
- A **network** is simply **things connected** (people, buses, power grid; in computing: devices).
- In computing, a network can be **2 → billions** of devices (phones, laptops, cameras, sensors).
- **Action:** Answer with **Network** → **Submit** → **Complete**.

### Task 2 — What is the Internet?
- The **Internet** = **many small private networks** interconnected over **public networks** → one huge network.
- Quick history: **ARPANET** (late 1960s) → **WWW** invented by **Tim Berners‑Lee (1989)**.
- **Action:** Answer **Tim Berners‑Lee** → **Submit** → **Complete**.

### Task 3 — Identifying devices on a network
- Two identifiers (analogy: name vs fingerprints):
  - **IP address** (changeable *name*) — defines where a device is on a network **for now**.
    - **IPv4**: four **octets** (`x.x.x.x`, each 0–255). One address per device per network at a time.
    - **Private vs Public**: devices on your LAN use **private** IPs (e.g., `192.168.1.74`), and share a **public** IP on the Internet via your **router/ISP**.
    - **IPv6**: much larger address space (`2^128`); you’ll see both IPv4 and IPv6 in 2025.
  - **MAC address** (hardware *fingerprints*) — 12 hex chars in pairs, e.g., `a4:c3:f0:85:ac:2d`.
    - First 6 = vendor; last 6 = unique interface ID. Burned into NIC, but **can be spoofed** in software.
- **Lab (hotel Wi‑Fi MAC filtering):**
  1) Click **View Site**. Copy **Alice’s MAC**: `00:12:32:2F:33:39`.
  2) **Spoof** Bob’s MAC to Alice’s in the sim.
  3) Re‑try the site → flag appears: **THM{YOU_GOT_ON_TRYHACKME}**.
- **Answers to submit:** IP → *Internet Protocol*; octet; 4; MAC → *Media Access Control*; lab flag.

### Task 4 — Ping (ICMP)
- **ping** sends **ICMP echo** packets and expects **echo reply** — quick reachability/latency test.
- Syntax wanted: just the basic command, no options.
- **Answers to submit:**
  - Protocol: **ICMP**
  - Syntax: **ping 10.10.10.10**
  - Run ping to **8.8.8.8** in the sim → flag **THM{I_PINGED_THE_SERVER}**

### Task 5 — Continue your learning: Intro to LAN
- Join the **Intro to LAN** room next.
- **Action:** Click **Complete**.

---

## Acronyms & terms — plain English (2025)
- **IP (Internet Protocol):** Addressing & routing rules so devices can talk on a network.
- **IPv4 / IPv6:** Two IP versions in use; IPv6 solves IPv4 exhaustion and adds improvements.
- **Octet:** One of the four IPv4 number blocks (8 bits each).
- **MAC (Media Access Control) address:** Hardware identifier for a network interface (12 hex chars).
- **NIC (Network Interface Card):** Hardware that connects a device to a network.
- **ISP (Internet Service Provider):** Gives you Internet access (and your **public IP**).
- **NAT (Network Address Translation):** Lets many private devices share one public IP.
- **CGNAT (Carrier‑Grade NAT):** Your ISP’s large‑scale NAT (common on mobile/ISP networks).
- **ICMP (Internet Control Message Protocol):** Network messaging used by **ping**.
- **ARPANET / WWW:** Early Internet project / the modern Web invented by **Tim Berners‑Lee**.

---

## 2025 notes & good practice
- **Private MAC address randomization** is default on iOS/Android — great for privacy; know it when testing.
- **IPv6** is common alongside IPv4 (dual‑stack). Expect both in traceroutes, logs, and labs.
- **Ping may be blocked** by firewalls; reachability ≠ open ports.
- **MAC filtering is weak** security — spoofing demonstrates why identity needs stronger controls (e.g., WPA2‑Enterprise).

---

## Quick reference (copy‑paste)
```bash
# Basic ping (Linux/macOS)
ping 10.10.10.10

# Windows basic ping
ping 10.10.10.10

# See local IPs
ip addr        # Linux
ipconfig       # Windows

# See ARP cache (who’s at which MAC on LAN)
arp -a
```

---

## Momentum plan (after this room)
1) Do **Intro to LAN**, then **OSI Model**, **Packets & Frames**.
2) Build a one‑page **notes repo**: key terms (Network, IP, MAC, ICMP), lab flags, a couple of diagrams.
3) Practice **ping** and **IP/MAC basics** on a home lab VM (don’t spoof on real public networks).
