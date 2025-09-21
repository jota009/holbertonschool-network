# 🌐 Networking Basics - Part 0

Welcome to your first networking project! This directory covers the fundamental concepts that make the internet work.

## 📚 What You'll Learn

- **OSI Model**: The 7-layer framework that organizes how networks communicate
- **Network Types**: LAN, WAN, and the Internet
- **Addressing**: MAC addresses vs IP addresses
- **Protocols**: TCP vs UDP - the two ways data travels
- **Ports**: How computers know which application to send data to
- **Network Tools**: Essential commands for troubleshooting

---

## 🎯 Tasks Overview

### Task 0: OSI Model
**File:** `0-OSI_model`

**What it does:** Tests your understanding of the OSI model concept

**Key concepts:**
- OSI model is a **thinking framework** (not physical)
- Organized from **lowest (Layer 1) to highest (Layer 7)**
- Helps us understand complex networking step by step

**Real-world example:** Like having a recipe - it breaks down cooking into organized steps instead of doing everything at once.

---

### Task 1: Types of Networks
**File:** `1-types_of_network`

**What it does:** Tests knowledge of LAN, WAN, and Internet scope

**Key concepts:**
- **LAN (Local Area Network)**: Your house, office floor, coffee shop WiFi
- **WAN (Wide Area Network)**: Connecting different buildings/cities
- **Internet**: The global network connecting everything

**Memory trick:**
- LAN = **L**ocal (same building)
- WAN = **W**ide (between cities)
- Internet = **I**nternational (worldwide)

---

### Task 2: MAC and IP Addresses
**File:** `2-MAC_and_IP_address`

**What it does:** Explains the difference between MAC and IP addresses

**Key concepts:**
- **MAC Address**: Hardware fingerprint (never changes)
- **IP Address**: Network location (changes when you move networks)

**Easy analogy:**
- MAC = Your driver's license number (stays with you forever)
- IP = Your home address (changes when you move)

---

### Task 3: TCP vs UDP
**File:** `3-UDP_and_TCP`

**What it does:** Shows how different protocols handle data delivery

**Key concepts:**
- **TCP**: Slow but reliable (like registered mail)
- **UDP**: Fast but might lose data (like shouting across a room)

**When to use:**
- **TCP**: Web browsing, email, file downloads (need ALL the data)
- **UDP**: Video streaming, online gaming (speed matters more)

---

### Task 4: Ports and Network Monitoring
**File:** `4-TCP_and_UDP_ports`

**What it does:** Creates a script to see what's running on your computer

**Key concepts:**
- **Ports**: Like apartment numbers (IP gets you to the building, port gets you to the right door)
- **Essential ports to remember:**
  - **22**: SSH (secure remote access)
  - **80**: HTTP (websites)
  - **443**: HTTPS (secure websites)

**Script does:** Shows all listening ports with program names
```bash
sudo ./4-TCP_and_UDP_ports
```

---

### Task 5: Network Connectivity Testing
**File:** `5-is_the_host_on_the_network`

**What it does:** Creates a script to test if other computers are reachable

**Key concepts:**
- **PING**: Sends "hello, are you there?" messages using ICMP
- **Network troubleshooting**: First thing to try when something doesn't work

**Script usage:**
```bash
./5-is_the_host_on_the_network 8.8.8.8
./5-is_the_host_on_the_network 127.0.0.1
```

**What happens:** Sends 5 ping packets and shows response times

---

## 🔧 Essential Commands Learned

| Command | What it does | Example |
|---------|-------------|---------|
| `ping -c 5 [IP]` | Test connectivity | `ping -c 5 google.com` |
| `netstat -lp` | Show listening ports | `netstat -lp` |
| `localhost` | Your own computer | Always `127.0.0.1` |

---

## 🧠 Key Takeaways

### OSI Model
- **Layer 1 (Physical)**: Cables, WiFi signals
- **Layer 3 (Network)**: IP addresses, routing
- **Layer 4 (Transport)**: TCP/UDP protocols
- **Layer 7 (Application)**: Web browsers, email

### Network Hierarchy
```
Internet (Global)
    ↓
WAN (Cities/Countries)
    ↓
LAN (Building/Campus)
    ↓
Your Device
```

### Address Types
- **MAC**: Hardware identity (permanent)
- **IP**: Network location (temporary)

### Data Delivery
- **TCP**: "Did you get that? Let me check..."
- **UDP**: "Here's the data, hope you got it!"

---

## 🎮 Quick Self-Test

1. What type of network connects your laptop to your home printer?
2. Which is faster: TCP or UDP?
3. What port does HTTPS use?
4. What's the difference between a MAC and IP address?
5. What command tests if google.com is reachable?

<details>
<summary>Click for answers</summary>

1. LAN (Local Area Network)
2. UDP (but less reliable)
3. Port 443
4. MAC = hardware ID (permanent), IP = network location (changes)
5. `ping google.com`
</details>

---

## 🚀 What's Next?

You now understand the basics of how networks work! In the next project, you'll learn more practical tools and dive deeper into network configuration.

**Skills unlocked:** ✅ Network fundamentals ✅ Basic troubleshooting ✅ Protocol understanding