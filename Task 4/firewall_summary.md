# Firewall Summary and Traffic Filtering

## 🔒 What is a Firewall?
A firewall is a security system that monitors and controls incoming and outgoing network traffic based on pre-set rules.

## 🔍 How Does It Filter Traffic?

1. **Source and Destination IPs**
   - Allows or blocks traffic based on origin and destination addresses.

2. **Ports and Protocols**
   - Filters using port numbers and transport protocols like TCP/UDP.

3. **Traffic Direction**
   - **Inbound** rules manage data coming into the device.
   - **Outbound** rules manage data leaving the device.

4. **Applications**
   - Some firewalls can filter traffic by the software generating the traffic.

5. **Stateful Inspection**
   - Remembers allowed sessions and ensures only related responses are accepted.

---

## 💻 Commands Used in Command Prompt (Admin)

### 1. List All Firewall Rules
```cmd
netsh advfirewall firewall show rule name=all
```

### 2. Block Port 23 (Telnet)
```cmd
netsh advfirewall firewall add rule name="Block Telnet" protocol=TCP dir=in localport=23 action=block
```

### 3. Delete the Block Rule
```cmd
netsh advfirewall firewall delete rule name="Block Telnet"
```

---

## 📌 Outcome
Learned how to inspect and modify firewall rules using Windows Command Prompt to control traffic and improve system security.
