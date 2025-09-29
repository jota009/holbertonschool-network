```mermaid
graph TD
    A["👤 User types<br/>https://www.google.com<br/>and presses Enter"] --> B["🔍 DNS Resolution<br/>Browser → DNS Server<br/>www.google.com → 142.250.80.46"]

    B --> C["🤝 TCP Connection<br/>Three-way handshake<br/>to IP: 142.250.80.46<br/>Port: 443 HTTPS"]

    C --> D["🔒 TLS Handshake<br/>Encrypted Connection<br/>Certificate Verification<br/>Secure Tunnel Established"]

    D --> E["🛡️ Firewall<br/>Traffic Inspection<br/>Security Rules Applied<br/>Malicious Traffic Blocked"]

    E --> F["⚖️ Load Balancer<br/>Distributes Request<br/>Selects Healthy Server<br/>Geographic Routing"]

    F --> G["🌐 Web Server<br/>Nginx/Apache<br/>Receives HTTPS Request<br/>Serves Static Content"]

    G --> H["🔧 Application Server<br/>Executes Business Logic<br/>Processes Search Query<br/>Generates Dynamic Content"]

    H --> I["🗄️ Database Server<br/>MySQL/Bigtable<br/>Retrieves Search Results<br/>User Data & Preferences"]

    I --> H
    H --> G
    G --> F
    F --> E
    E --> J["📤 Encrypted Response<br/>Travels Back Through<br/>Same Secure Path"]

    J --> K["✅ Browser Renders<br/>Google Search Page<br/>Total Time: ~500ms"]

   