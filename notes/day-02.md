# Day 2: IP Addresses (Private vs Public)

## What I learned
- An IP address is the "home address" of a device on a network.
- A public IP is how the internet sees me (given by my ISP).
- A private IP is used only inside my local network.

## Private IP ranges
- 10.0.0.0 – 10.255.255.255
- 172.16.0.0 – 172.31.255.255
- 192.168.0.0 – 192.168.255.255

## Why many devices share one public IP
Because all devices connect to the internet through one router, which has a single public IP.
The router translates private IPs to the public IP .this is called NAT.

## Hands-on practice
- My private IP range: 192.168.x.x (write only the range, not the full address)
- Command used: `ipconfig` / `ip a`
- Ping test: `ping 8.8.8.8` → latency was 35 ms
- What latency means: The time it takes for data to travel to a server and back.

## Quiz self-check
Score: 4/4
