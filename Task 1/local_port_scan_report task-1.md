# 🔍 Task 1 – Local Network Port Scan

## 🧾 Objective
Perform a TCP SYN scan using **Nmap** to discover open ports on devices within the local network, and analyze the security implications of the discovered services.

---

## 🛠 Tools Used

- **Nmap** – For port scanning
- **Wireshark** (optional) – For packet capture and analysis
- **Operating System** – Windows

---

## 📡 Scan Command Used

```bash
nmap -sS 192.168.199.0/24
```

This scanned all devices in the subnet `192.168.199.x` for open TCP ports using a SYN (stealth) scan.

---

## 📋 Scan Results (Summary)

| IP Address        | Open Port(s)       | Service(s) Detected                               |
|-------------------|--------------------|---------------------------------------------------|
| 192.168.199.X     | 135, 139, 445, 903 | msrpc, netbios-ssn, microsoft-ds, iss-console-mgr |

---

## 🔐 Open Ports and Risk Analysis

| **Port(s)** | **Protocol**  | **Service**         | **Details**                     | **Risk Summary**                                                                 |
|-------------|---------------|----------------------|----------------------------------|----------------------------------------------------------------------------------|
| **135**     | TCP/UDP       | `msrpc`              | Microsoft RPC services           | Often targeted by malware; can allow remote execution if improperly secured.     |
| **139**     | TCP/UDP       | `netbios-ssn`        | NETBIOS Session Service         | Used for file/printer sharing on Windows; can expose sensitive internal systems. |
| **445**     | TCP           | `microsoft-ds`       | SMB over TCP                    | Major target for ransomware (e.g., WannaCry); avoid exposing this to the internet. |
| **903**     | TCP           | `iss-console-mgr`    | ISS Console Manager             | Not widely used; may be tied to legacy tools. Disable if not explicitly required. |

---

## ✅ Recommendations

- **Disable** unused Windows services like NetBIOS and SMB if not needed.
- Ensure these ports are **firewalled** and not exposed to public internet.
- Regularly **update system patches** to prevent exploitation.
- If port 903 is not understood or needed, **block or investigate it** further.
- Use **strong passwords**, restrict remote access, and implement **least privilege** principles.

## 📦 Repository Contents

- `nmap_scan_results.txt` – Raw Nmap output
- `scan_capture.pcapng` – (Optional) Wireshark capture file
- `screenshots/` – (Optional) Screenshots of Wireshark or scan
- `Task-1` – This documentation
