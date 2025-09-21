# 🔧 Networking Basics - Part 1

Building on the fundamentals, this project teaches you practical networking skills and tools that network engineers use every day.

## 📚 What You'll Learn

- **localhost & Special IPs**: Understanding 127.0.0.1 and 0.0.0.0
- **hosts file**: Your computer's personal phone book for websites
- **Network interfaces**: How to see your computer's network connections
- **netcat**: The Swiss Army knife of networking tools
- **Real troubleshooting**: Practical tools for debugging network issues

---

## 🎯 Tasks Overview

### Task 0: Hosts File Configuration
**File:** `0-change_your_home_IP`

**What it does:** Changes how your computer resolves localhost and facebook.com

**Key concepts:**
- **hosts file (`/etc/hosts`)**: Your computer's personal directory
- **Name resolution**: How computers turn names into IP addresses
- **Local DNS override**: Making your computer ignore the internet's answers

**What the script does:**
- Changes `localhost` from `127.0.0.1` → `127.0.0.2`
- Redirects `facebook.com` → `8.8.8.8` (Google's DNS)

**Real-world uses:**
- **Development**: Test websites locally before going live
- **Security**: Block malicious websites
- **Testing**: Redirect traffic for debugging

**⚠️ Important:** This breaks things! Restore with:
```bash
sudo sed -i 's/127.0.0.2/127.0.0.1/' /etc/hosts
sudo sed -i '/facebook.com/d' /etc/hosts
```

---

### Task 1: Show Network Interfaces
**File:** `1-show_attached_IPs`

**What it does:** Lists all IPv4 addresses on your computer

**Key concepts:**
- **Network interfaces**: Different ways your computer connects to networks
- **Multiple IPs**: Your computer can have several network connections
- **Interface types:**
  - **Loopback (lo)**: localhost (127.0.0.1)
  - **Ethernet**: Wired connection
  - **WiFi**: Wireless connection

**Script output example:**
```
127.0.0.1
192.168.1.100
10.0.0.5
```

**What each IP means:**
- `127.0.0.1`: Your computer talking to itself
- `192.168.x.x`: Usually your home/office network
- `10.x.x.x`: Could be corporate network or VPN

---

### Task 2: Network Listening with netcat
**File:** `2-port_listening_on_localhost`

**What it does:** Creates a simple server that listens for connections

**Key concepts:**
- **netcat (nc)**: Multi-purpose networking tool
- **Server mode**: Listen for incoming connections
- **Port binding**: "Open a door" on a specific port number

**How to test:**
1. **Terminal 1** (Start the server):
   ```bash
   sudo ./2-port_listening_on_localhost
   ```

2. **Terminal 2** (Connect as client):
   ```bash
   telnet localhost 98
   ```

3. **Type messages** in Terminal 2, see them appear in Terminal 1!

**Real-world applications:**
- **Quick file transfers**: Send files between computers
- **Network debugging**: Test if ports are blocked
- **Simple chat**: Create instant messaging
- **Protocol testing**: See raw network communication

---

## 🌟 Special IP Addresses Explained

### 127.0.0.1 (localhost)
- **What it is**: Your computer's address for talking to itself
- **Always the same**: Every computer uses this address internally
- **Uses**: Local development, testing, internal services

### 0.0.0.0 (Wildcard address)
- **What it is**: "Listen on ALL available network interfaces"
- **Server usage**: Makes services accessible from any network connection
- **Security note**: Be careful - this exposes services to the network!

### The hosts file (/etc/hosts)
```bash
# Format: IP_ADDRESS    HOSTNAME
127.0.0.1    localhost
192.168.1.50 printer.office
8.8.8.8      test-facebook.com
```

**How name resolution works:**
```
1. Check /etc/hosts file first ← We control this!
2. If not found, ask DNS servers
3. If still not found, show error
```

---

## 🔧 Essential Commands Learned

| Command | What it does | Example |
|---------|-------------|---------|
| `ifconfig` | Show network interfaces | `ifconfig` |
| `nc -l [host] [port]` | Listen for connections | `nc -l localhost 98` |
| `telnet [host] [port]` | Connect to a port | `telnet localhost 98` |
| `cat /etc/hosts` | View hosts file | `cat /etc/hosts` |

---

## 🛠️ Practical Networking Tools

### netcat (nc) - The Swiss Army Knife

**As a server (listener):**
```bash
nc -l localhost 1234
```

**As a client (connector):**
```bash
nc localhost 1234
```

**File transfer example:**
```bash
# Receiver
nc -l localhost 1234 > received_file.txt

# Sender
cat myfile.txt | nc localhost 1234
```

**Port testing:**
```bash
nc -v google.com 80
```

### Text Processing Tools

**Extract IPs from ifconfig:**
```bash
ifconfig | grep "inet " | awk '{print $2}'
```

**Components:**
- `ifconfig`: Show interfaces
- `grep "inet "`: Find IPv4 lines
- `awk '{print $2}'`: Extract 2nd column (the IP)

---

## 🧠 Key Takeaways

### Name Resolution Priority
```
/etc/hosts → Local DNS → ISP DNS → Root DNS
     ↑
We control this!
```

### Network Interface Types
- **lo (loopback)**: Internal communication (127.0.0.1)
- **eth0/enp0s3**: Ethernet (wired connection)
- **wlan0/wlp2s0**: WiFi (wireless connection)
- **docker0/tun0**: Virtual interfaces (containers, VPNs)

### netcat Capabilities
- ✅ Simple file transfers
- ✅ Port scanning
- ✅ Chat systems
- ✅ Network debugging
- ✅ Protocol testing
- ✅ Firewall testing

---

## 🎮 Quick Self-Test

1. What file controls local name resolution?
2. What does `127.0.0.1` always point to?
3. How do you make netcat listen on port 8080?
4. What's the difference between `0.0.0.0` and `127.0.0.1`?
5. Name three uses for netcat.

<details>
<summary>Click for answers</summary>

1. `/etc/hosts`
2. localhost (your own computer)
3. `nc -l localhost 8080`
4. `0.0.0.0` = all interfaces, `127.0.0.1` = localhost only
5. File transfer, port testing, network debugging, chat, protocol analysis
</details>

---

## ⚠️ Important Notes

### Security Considerations
- **hosts file changes**: Can break system services
- **Listening on 0.0.0.0**: Exposes services to network
- **Always test changes**: In safe environments first

### Troubleshooting Tips
- **Permission denied**: Use `sudo` for privileged ports (< 1024)
- **Port already in use**: Check with `netstat -lp`
- **Can't connect**: Verify firewall isn't blocking

---

## 🚀 What's Next?

You now have practical networking tools! You can:
- ✅ Modify local DNS resolution
- ✅ Inspect network interfaces
- ✅ Create simple network services
- ✅ Debug network connectivity
- ✅ Transfer data between systems
**Author**
Josniel Ramos