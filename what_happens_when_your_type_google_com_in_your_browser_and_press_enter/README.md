# What Happens When You Type https://www.google.com and Press Enter

> A comprehensive technical breakdown of the complete web request lifecycle

## 📖 Overview

This blog post explores the fascinating journey that occurs between typing a URL and seeing a webpage - answering one of the most classic software engineering interview questions. Understanding this process demonstrates knowledge of the complete web stack, from DNS resolution to database queries.

## 🎯 Topics Covered

### 1. **DNS Resolution**
- How domain names are translated to IP addresses
- DNS caching hierarchy (browser → OS → ISP → root servers)
- The global DNS infrastructure

### 2. **TCP/IP Connection**
- Three-way handshake establishment
- Port 443 for HTTPS traffic
- Reliable data transmission protocols

### 3. **Firewall Security**
- Network traffic inspection
- Malicious request filtering
- Multi-layer security architecture

### 4. **HTTPS/SSL Encryption**
- TLS handshake process
- Certificate validation and authentication
- Secure encrypted tunnel establishment

### 5. **Load Balancer**
- Traffic distribution across multiple servers
- Health monitoring and failover
- Geographic and algorithmic routing strategies

### 6. **Web Server**
- HTTP request handling (Nginx/Apache)
- Static content delivery
- Reverse proxy functionality

### 7. **Application Server**
- Business logic execution
- Dynamic content generation
- Search algorithm processing

### 8. **Database**
- Data retrieval and query processing
- Distributed database architecture
- Caching and optimization strategies

## 🚀 Key Takeaways

- A simple web request involves **dozens of technical components** working in coordination
- The entire journey typically completes in **200-1000 milliseconds**
- **Security layers** protect data at multiple points (firewalls, encryption, authentication)
- **Distributed systems** enable global scale and reliability
- Understanding this flow is essential for **system design, debugging, and optimization**

## 📊 Request Flow Summary

```
User → DNS Lookup → TCP Connection (Port 443) → TLS Encryption →
Firewall → Load Balancer → Web Server → Application Server →
Database → Response Path Back to User
```

## 🎓 Why This Matters

This question tests:
- **Networking fundamentals** - DNS, TCP/IP, routing
- **Security awareness** - Encryption, firewalls, certificates
- **System architecture** - Load balancing, server roles, databases
- **Scale understanding** - How global services handle billions of requests
- **Problem-solving** - Ability to explain complex systems clearly

## 💼 Interview Relevance

This is a **classic interview question** used by companies like Google, Amazon, Facebook, and Microsoft to assess:
- General web stack knowledge
- Ability to explain technical concepts
- Understanding of distributed systems
- Communication skills with technical depth

Different roles may focus on different aspects:
- **Frontend**: DOM rendering, browser caching
- **Backend**: Server processing, database queries
- **SRE/DevOps**: Load balancing, infrastructure, monitoring
- **Security**: Encryption, firewalls, certificate validation

## 📝 Blog Post

Read the full detailed explanation: [Link to your Medium/LinkedIn post]

## 🛠️ Technologies Mentioned

- **DNS Servers** - Domain name resolution
- **TCP/IP** - Network communication protocols
- **TLS/SSL** - Encryption and security
- **Firewalls** - Network security
- **Load Balancers** - Traffic distribution (HAProxy, AWS ELB)
- **Web Servers** - HTTP handling (Nginx, Apache)
- **Application Servers** - Business logic (Node.js, Tomcat)
- **Databases** - Data storage (MySQL, Bigtable, Spanner)

## 📚 Related Projects

- [Simple Web Stack](../0-simple_web_stack) - Single server architecture
- [Distributed Web Infrastructure](../1-distributed_web_infrastructure) - Multi-server setup
- [Secured Web Infrastructure](../2-secured_web_infrastructure) - Security & monitoring
- [Scale Up](../3-scale_up) - Component separation & optimization

## 🎯 Learning Objectives Achieved

- ✅ Explain the complete web request lifecycle
- ✅ Understand DNS resolution process
- ✅ Describe TCP/IP connection establishment
- ✅ Explain HTTPS/SSL encryption
- ✅ Understand load balancing strategies
- ✅ Differentiate web servers from application servers
- ✅ Describe database role in request processing
- ✅ Communicate complex technical concepts clearly

