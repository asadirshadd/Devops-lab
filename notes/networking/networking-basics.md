# 🌐 Networking Basics

## Network
A group of connected devices that share data.
> Example: Ghar ka WiFi — phone, laptop, TV sab connected hain.

---

## IP Address
Har device ka unique address on a network.
> Example: Tumhara PC = `192.168.100.32`, Router = `192.168.100.1`

| Type    | Range           | Example         |
|---------|-----------------|-----------------|
| Private | 192.168.x.x     | Ghar ka network |
| Public  | Everything else | Stripe ka server|

```bash
ipconfig        # Windows par apna IP dekho
```

---

## DNS
Converts domain names to IP addresses.
> Example: `google.com` → `192.178.174.100` (phone book of internet)

```bash
nslookup google.com     # DNS query karo
nslookup stripe.com     # Stripe ka IP dekho
```

---

## Ping
Tests if a device is reachable + how fast.
> Example: `ping google.com` → time=355ms (Pakistan se Google tak)

```bash
ping 192.168.100.1      # Router check karo (should be ~3ms)
ping google.com         # Internet check karo
```

---

## Ports
Every service runs on a specific port — like doors of a building.
> Example: Stripe ka payment server = IP:443, Database = IP:5432

| Port | Service    | Example                     |
|------|------------|-----------------------------|
| 80   | HTTP       | Old websites                |
| 443  | HTTPS      | Amazon, N26, Stripe         |
| 22   | SSH        | EC2 server remote access    |
| 5432 | PostgreSQL | Klarna ka database          |
| 6379 | Redis      | Revolut session cache       |

---

## TCP vs UDP
Two ways to send data over a network.

| Feature  | TCP                        | UDP                      |
|----------|----------------------------|--------------------------|
| Delivery | Guaranteed ✅              | Not guaranteed ❌        |
| Speed    | Slower                     | Faster                   |
| Use      | Bank transfer, Email       | Video call, Gaming, DNS  |

> Example: N26 bank transfer = TCP (ek packet miss = wrong amount 😱)
> Example: WhatsApp video call = UDP (thoda blur OK, delay nahi)

---

## HTTP vs HTTPS

| HTTP                        | HTTPS                       |
|-----------------------------|-----------------------------|
| Plain text — visible to all | Encrypted — TLS/SSL         |
| Port 80                     | Port 443                    |
| ❌ Unsafe                   | ✅ Safe                     |

> Example: HTTP pe password dalo → hacker dekh sakta hai: `password=12345`
> HTTPS pe → hacker dekha: `x9#mK$2@...` (kuch nahi samjha)

```bash
curl -I https://stripe.com      # HTTPS headers dekho
```

---

## OSI Model
7 layers jo define karte hain how data travels over a network.
> Trick: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing

| Layer | Name         | Example                    | AWS              |
|-------|--------------|----------------------------|------------------|
| L7    | Application  | Chrome, WhatsApp, Zoom     | API Gateway      |
| L6    | Presentation | SSL/TLS encryption         | ACM Certificates |
| L5    | Session      | Login session active rakho | —                |
| L4    | Transport    | TCP/UDP, Port numbers      | NLB              |
| L3    | Network      | IP address, Router         | VPC, Route Table |
| L2    | Data Link    | MAC address, Switch        | —                |
| L1    | Physical     | Cable, WiFi, Fiber         | AWS Data Center  |

> Interview Q: "Which layer does a firewall work on?"
> Answer: L3 (IP block) + L4 (Port block). WAF = L7.

---

## Subnetting
Dividing a big network into smaller ones.
> Example: N26 AWS VPC `10.0.0.0/16` → Public subnet `/24` (web), Private subnet `/24` (DB)

| CIDR | Total IPs | Use Case              |
|------|-----------|-----------------------|
| /32  | 1         | Single host           |
| /24  | 256       | Standard AWS subnet   |
| /16  | 65,536    | AWS VPC size          |

```bash
# AWS VPC design (N26 style):
VPC:     10.0.0.0/16
Public:  10.0.1.0/24  → Web servers (internet access)
Private: 10.0.2.0/24  → Database (NO internet access)
```

---

## Key Commands Cheatsheet

```bash
ipconfig                    # IP info (Windows)
ping google.com             # Connectivity test
nslookup stripe.com         # DNS query
tracert n26.com             # Route trace (hop by hop)
netstat -an                 # Open ports dekho
```
