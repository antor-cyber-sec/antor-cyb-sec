# Day 4: Ports and Protocols

## What I learned
- A port identifies a specific service on a computer. IP is the building, port is the flat number.
- A protocol is a set of rules that computers follow to communicate.

## Common ports
| Port | Protocol | Purpose |
|---|---|---|
| 80 | HTTP | Web traffic (not encrypted) |
| 443 | HTTPS | Secure web traffic (encrypted) |
| 22 | SSH | Secure remote login |
| 53 | DNS | Domain name lookups |
| 21 | FTP | File transfer (old, insecure) |

## Hands-on practice
- Checked the padlock icon on https://github.com (HTTPS, port 443).
- Ran `netstat -an` on my own computer.
- Observed: ESTABLISHED means an active connection, LISTENING means my computer is waiting for incoming connections.
-  With 4 websites open, I counted 14 connections on port 443, because each website opens many connections for images, scripts and ads.

## Quiz self-check
Score: 4/4
