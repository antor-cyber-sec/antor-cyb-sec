# Day 10: Networking Wrap-up and Cheat Sheet

My own summary of the networking basics from my first 10 days. All practice was done on my own computer using safe, legal commands.

## Core concepts
| Concept | One-line meaning |
|---|---|
| IP address | The address of a device on a network |
| Private IP | Used inside my local network (10.x, 172.16-31.x, 192.168.x) |
| Public IP | How the internet sees my network (given by my ISP) |
| NAT | The router translates private IPs to its public IP |
| DNS | Translates a domain name into an IP address |
| Port | Identifies a specific service on a computer |
| DHCP | Automatically gives devices an IP address (and the gateway and DNS server) |
| Default gateway | Where my computer sends traffic that leaves the LAN (usually the router) |
| LAN / WAN | A small local network / the large outside network (the internet is the biggest WAN) |
| Router / Switch | Connects the LAN to the WAN / connects devices inside a LAN |

## Common ports
| Port | Protocol | Purpose |
|---|---|---|
| 80 | HTTP | Web traffic (not encrypted) |
| 443 | HTTPS | Web traffic (encrypted) |
| 22 | SSH | Secure remote login (a locked room) |
| 21 | FTP | File transfer (insecure, like an open postcard) |
| 53 | DNS | Domain name lookups |

## TCP vs UDP
| | TCP | UDP |
|---|---|---|
| Idea | Like a phone call | Like a loudspeaker announcement |
| Reliability | Yes, lost data is resent | No guarantee |
| Speed | Slightly slower | Faster |
| Used by | HTTP/HTTPS, SSH, FTP | DNS, video calls, games |

TCP connects with a three-way handshake: SYN, SYN-ACK, ACK.

## HTTP and HTTPS
- Methods: GET (retrieve data), POST (send data).
- Status code families: 2xx success, 3xx redirect, 4xx client error, 5xx server error.

| Code | Meaning |
|---|---|
| 200 | OK |
| 301 | Moved permanently (redirect) |
| 304 | Not modified (use my cached copy) |
| 403 | Forbidden (the page exists, but I am not allowed in) |
| 404 | Not found (the page does not exist) |
| 500 | Server error |

- HTTPS = HTTP + TLS. TLS does two jobs: **encryption** (nobody on the path can read the data) and **identity check** (a certificate proves I am talking to the real site).

## My command toolbox (Windows)
| Command | What it shows |
|---|---|
| `ipconfig /all` | My own IP, gateway, DNS and DHCP |
| `ping` | Whether a host is reachable and how fast |
| `nslookup` | A website's IP (domain name to IP) |
| `tracert` | The hops from my computer to a destination |
| `netstat -an` | Active connections on my computer |
| `curl -I` / `curl -vI` | HTTP status and headers / plus connection and TLS details |

Note: `ipconfig` shows **my own** computer's details, while `nslookup` shows **a website's** IP.

## How I troubleshoot (nearest to farthest)
1. `ping` my default gateway: if it fails, the problem is on the LAN (Wi-Fi or router).
2. `ping 8.8.8.8`: if it fails, the problem is on the WAN (ISP or internet).
3. `nslookup google.com`: if it fails but step 2 works, the problem is DNS.
4. `curl -I https://google.com`: if it fails but DNS works, the problem is the web connection (HTTPS, firewall or the site).

### My test results
- Ping to my default gateway: average 2 ms
- `ping 8.8.8.8`: 0% loss, about 26 ms
- `ping google.com`: 0% loss, about 37 ms (the name resolved correctly)
- `curl -I https://google.com`: 301 Moved Permanently, redirecting to https://www.google.com/

Everything worked, so my network is healthy. The gateway is inside my home, so it replies much faster than far-away servers.

## Weak spots I found in my review quiz
I scored 2/4. What I got wrong or forgot:
- I confused `ipconfig` (my own details) with `nslookup` (a website's IP).
- I mentioned only one job of TLS (encryption). The second is identity verification.
- I forgot ports 21, 22 and 53, and the meanings of some status codes.
- I wrote `ping <Default Gateway>` literally. The angle brackets only mean "put the real value here".

My plan: rewrite these tables from memory after 1 day, 3 days and 1 week.

## Related work
- [What happens when I type github.com in my browser](../projects/how-a-website-loads.md)

> Practice was done only on my own computer using safe, legal commands.
