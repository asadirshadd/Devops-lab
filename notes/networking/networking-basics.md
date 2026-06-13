# Networking Notes 🌐

## What is a Network?
- 2+ computers jo data share karte hain
- Devices + Medium + Protocol

## IP Address
- Private: 192.168.x.x (ghar/office)
- Public: Internet par unique
- Tumhara IP: 192.168.100.32
- Router: 192.168.100.1

## DNS — Internet ka Phone Book
- google.com → 192.178.174.100
- Command: nslookup google.com
- Stripe example: api.stripe.com → AWS IP

## Ping
- Command: ping google.com
- Test karo connection hai ya nahi
- time=3ms (router) vs time=355ms (Google)

## Ports
| Port | Service |
|------|---------|
| 443  | HTTPS   |
| 80   | HTTP    |
| 22   | SSH     |
| 5432 | PostgreSQL |

## TCP vs UDP
- TCP: Guaranteed delivery (banking, email)
- UDP: Fast, no guarantee (video call, gaming)

## HTTP vs HTTPS
- HTTP: Plain text — hacker dekh sakta hai!
- HTTPS: Encrypted — TLS/SSL
- Port 80 vs 443

## OSI Model (All People Seem To Need Data Processing)
- L7 Application  → Chrome, WhatsApp
- L6 Presentation → SSL/TLS Encryption
- L5 Session      → Connection manage
- L4 Transport    → TCP/UDP
- L3 Network      → IP Address, Router
- L2 Data Link    → MAC Address, Switch
- L1 Physical     → Cable, WiFi

## Subnetting
- 192.168.1.0/24 = 256 addresses
- AWS VPC: 10.0.0.0/16 = 65,536 addresses